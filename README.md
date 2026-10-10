# EggApps · Context Prompting Laboratuvarı

Context prompting formüllerini keşfetmek, örneklerle incelemek ve ihtiyacınıza uygun yaklaşımı seçmek için hazırlanmış Türkçe bir web laboratuvarı.

## Neler sunuyor?

- **R·B·G·F·K çekirdek formülü** ve context prompting yaklaşımı
- **24 prompt formülü** ve her formül için örnekler
- Formülleri karşılaştırmaya yardımcı **verimlilik skorları**
- Kullanılabilir bağlam miktarını planlamak için **bağlam bütçesi hesaplayıcısı**
- İhtiyaca göre uygun formülü bulmaya yardımcı **öneri aracı**

> Özellik listesi, sitenin `index.html` dosyasındaki başlık ve açıklama metnine göre hazırlanmıştır.

## Teknoloji

`index.html`, uygulamayı `/src/main.tsx` üzerinden başlatıyor. Bu yapı Vite ve React/TypeScript tabanlı bir proje olduğunu gösterir. Geliştirme ve derleme için projenin geri kalan kaynak dosyaları ile `package.json` dosyası da repoda bulunmalıdır.

## Yerelde çalıştırma

Node.js kurulu olmalıdır. Proje kök dizininde:

```bash
npm install
npm run dev
```

Üretim sürümünü derlemek ve yerelde önizlemek için:

```bash
npm run build
npm run preview
```

## GitHub Pages'te yayınlama

Bu proje Vite kullanıyorsa GitHub Actions ile yayınlamak için:

1. Projenin tamamını GitHub deposuna yükleyin (`src/`, `package.json` ve kilit dosyası dahil).
2. Depoda **Settings → Pages → Build and deployment → Source** bölümünden **GitHub Actions** seçin.
3. Depo bir proje sayfası olacaksa (`kullanici.github.io/REPO_ADI/`), `vite.config.ts` içindeki `base` değerini depo adına göre ayarlayın:

   ```ts
   import { defineConfig } from 'vite'
   import react from '@vitejs/plugin-react'

   export default defineConfig({
     plugins: [react()],
     base: '/REPO_ADI/',
   })
   ```

   `REPO_ADI` kısmını GitHub depo adınızla değiştirin. Site `kullanici.github.io` kök adresinde veya özel bir alan adında yayınlanıyorsa `base: '/'` kullanın.

4. Aşağıdaki iş akışını `.github/workflows/deploy.yml` konumunda ekleyin. `main` yerine varsayılan dalınızın adını yazın; proje `npm run build` komutuyla `dist` klasörüne çıktı üretmelidir.

   ```yaml
   name: Deploy to GitHub Pages

   on:
     push:
       branches: [main]
     workflow_dispatch:

   permissions:
     contents: read
     pages: write
     id-token: write

   concurrency:
     group: pages
     cancel-in-progress: true

   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Check out repository
           uses: actions/checkout@v4
         - name: Set up Node.js
           uses: actions/setup-node@v4
           with:
             node-version: 20
             cache: npm
         - name: Install dependencies
           run: npm ci
         - name: Build site
           run: npm run build
         - name: Upload Pages artifact
           uses: actions/upload-pages-artifact@v3
           with:
             path: dist

     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       needs: build
       steps:
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v4
   ```

5. `main` dalına gönderdiğinizde **Actions** sekmesindeki iş akışı derlemeyi ve yayını başlatır. Tamamlandığında site adresi **Settings → Pages** bölümünde görünür.

## Not

Yalnızca `index.html` dosyası tek başına yayınlanabilir bir Vite uygulaması oluşturmaz; `src/main.tsx`, bağımlılıklar ve proje ayarları da repoda bulunmalıdır.
