# Como Capturar Screenshots do Catálogo Digital

Este guia ajuda você a capturar screenshots profissionais do catálogo para o README.

## Opção 1: Usando DevTools do Chrome/Edge

### Desktop (1920x1080)
1. Abra https://tofariasti.github.io/catalogo-digital/ no Chrome/Edge
2. Pressione `F12` para abrir DevTools
3. Pressione `Ctrl+Shift+M` (ou `Cmd+Shift+M` no Mac) para modo responsivo
4. Configure a resolução: `1920 x 1080`
5. Pressione `Ctrl+Shift+P` (ou `Cmd+Shift+P` no Mac)
6. Digite "Capture full size screenshot"
7. Salve como `screenshots/desktop.png`

### Tablet (768x1024)
1. Com DevTools aberto, configure: `768 x 1024`
2. Capture full size screenshot
3. Salve como `screenshots/tablet.png`

### Mobile (375x812 - iPhone 12/13)
1. Com DevTools aberto, selecione preset "iPhone 12/13"
2. Capture full size screenshot
3. Salve como `screenshots/mobile.png`

## Opção 2: Usando Script Automatizado (Puppeteer)

Se você tem Node.js instalado e quer automatizar:

```bash
cd catalogo
npm init -y
npm install puppeteer

# Crie o arquivo capture-screenshots.js com o conteúdo abaixo
node capture-screenshots.js
```

### Script: `capture-screenshots.js`

```javascript
const puppeteer = require('puppeteer');
const path = require('path');

const url = 'https://tofariasti.github.io/catalogo-digital/';
const screenshotsDir = path.join(__dirname, 'screenshots');

const viewports = [
  { name: 'desktop', width: 1920, height: 1080 },
  { name: 'tablet', width: 768, height: 1024 },
  { name: 'mobile', width: 375, height: 812 },
];

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();

  for (const viewport of viewports) {
    console.log(`Capturando screenshot: ${viewport.name}...`);
    
    await page.setViewport({
      width: viewport.width,
      height: viewport.height,
      deviceScaleFactor: 2,
    });
    
    await page.goto(url, {
      waitUntil: 'networkidle2',
      timeout: 30000,
    });
    
    await page.waitForTimeout(2000);
    
    const screenshotPath = path.join(screenshotsDir, `${viewport.name}.png`);
    await page.screenshot({
      path: screenshotPath,
      fullPage: true,
    });
    
    console.log(`✓ Salvo: ${screenshotPath}`);
  }

  await browser.close();
  console.log('\n✨ Todos os screenshots foram capturados com sucesso!');
})();
```

## Opção 3: Online (Sem instalar nada)

Use serviços online gratuitos:

1. **Screely** (https://screely.com/)
   - Cole a URL
   - Escolha o template de navegador
   - Baixe a imagem

2. **Responsive Screenshot** (https://www.websiteplanet.com/webtools/responsive-checker/)
   - Cole a URL
   - Selecione os dispositivos
   - Capture e baixe

3. **GoFullPage** (Extensão Chrome)
   - Instale a extensão
   - Abra a página
   - Clique no ícone da extensão
   - Capture full page

## Dicas para Screenshots Profissionais

1. **Limpe o cache** antes de capturar para garantir carregamento completo
2. **Aguarde as animações** carregarem completamente
3. **Verifique a rolagem** para capturar toda a página
4. **Use alta resolução** (retina/2x) para imagens mais nítidas
5. **Capture em horário de boa luz** se for mostrar cores reais

## Após Capturar

Coloque os arquivos em:
```
catalogo/screenshots/
├── desktop.png
├── tablet.png
└── mobile.png
```

Os arquivos já estão referenciados no README.md!

## Otimização (Opcional)

Para reduzir o tamanho dos arquivos:

```bash
# Com TinyPNG CLI
npm install -g tinify-cli
tinify screenshots/*.png --key YOUR_API_KEY

# Ou use https://tinypng.com/ manualmente
```

---

**Pronto!** Seus screenshots estarão profissionais e otimizados para o README.
