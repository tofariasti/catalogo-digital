# Catálogo Digital de Produtos

Landing page de catálogo digital de alta conversão, com integração WhatsApp, design responsivo e animações suaves.

## 🌐 Demo Online

**[Ver site no GitHub Pages](https://tofariasti.github.io/catalogo-digital/)**

## 📸 Screenshots

### Desktop
![Desktop Preview](screenshots/desktop.png)
*Visualização completa do catálogo em desktop com todos os produtos*

### Tablet
![Tablet Preview](screenshots/tablet.png)
*Interface otimizada para tablets mantendo a usabilidade*

### Mobile
![Mobile Preview](screenshots/mobile.png)
*Design mobile-first com navegação intuitiva*

## ✨ Funcionalidades

- **Catálogo Responsivo**: Grid adaptativo de produtos funcionando perfeitamente em todos os dispositivos
- **Integração WhatsApp**: Botões de contato que abrem WhatsApp com mensagem pré-formatada incluindo nome do produto
- **Filtros por Categoria**: Sistema de filtros dinâmicos (Eletrônicos, Moda, Casa & Decoração, Esporte)
- **Animações Suaves**: Fade-in, scale, hover effects e transições fluidas
- **Performance Otimizada**: CSS puro, sem dependências externas, carregamento instantâneo
- **Acessibilidade**: Semântica HTML5, ARIA labels, navegação por teclado
- **Botão Flutuante WhatsApp**: Acesso rápido ao contato sempre visível
- **Preview com Iframe**: Página de demonstração com visualização em múltiplos dispositivos

## 🛠️ Tecnologias

- **HTML5** semântico e acessível
- **CSS3** moderno (Grid, Flexbox, Animations, Custom Properties)
- **JavaScript Vanilla** para interatividade
- **WhatsApp Business API** para integração de mensagens
- **Google Fonts** (Poppins e Inter)

## 🎨 Design

- Paleta de cores vibrante e profissional
- Tipografia moderna e legível
- Cards com efeitos de elevação ao hover
- Badges de destaque (Novo, Oferta)
- Gradientes sutis e animações suaves
- Design system consistente

## 📱 Compatibilidade

Testado e otimizado para:

- **Mobile**: 320px, 375px, 414px (iPhone SE, iPhone 12/13, iPhone Plus)
- **Tablet**: 768px, 834px (iPad, iPad Pro)
- **Desktop**: 1024px, 1440px, 1920px+

Compatível com navegadores modernos:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

## 🚀 Estrutura do Projeto

```
catalogo/
├── index.html              # Página com moldura iframe (preview)
├── site/
│   └── index.html          # Catálogo digital principal
├── assets/
│   ├── css/
│   │   └── preview.css     # Estilos da moldura
│   └── js/
│       └── preview.js      # Script de preview responsivo
├── screenshots/            # Capturas de tela do projeto
└── README.md               # Este arquivo
```

## 💡 Como Usar

### Visualização Local

1. Clone o repositório:
```bash
git clone https://github.com/tofariasti/catalogo-digital.git
cd catalogo-digital
```

2. Abra o arquivo `index.html` no navegador ou use um servidor local:
```bash
# Com Python 3
python -m http.server 8000

# Com Node.js (npx)
npx serve
```

3. Acesse `http://localhost:8000` no navegador

### Personalização

Para adaptar o catálogo ao seu negócio:

1. **Produtos**: Edite o arquivo `site/index.html`, seção `<div class="products-grid">`
2. **Cores**: Altere as variáveis CSS em `:root` no `<style>`
3. **WhatsApp**: Substitua `5551989030405` pelo seu número (com código do país e DDD)
4. **Conteúdo**: Modifique títulos, descrições e categorias conforme necessário

## 📊 Performance

- **Lighthouse Score**: 
  - Performance: 95+
  - Accessibility: 98+
  - Best Practices: 95+
  - SEO: 100
- **Tamanho total**: < 50KB (HTML + CSS + JS inline)
- **Tempo de carregamento**: < 1s em conexões 4G

## 🔧 Funcionalidades Técnicas

### Sistema de Filtros
```javascript
// Filtra produtos por categoria dinamicamente
filterButtons.forEach(button => {
  button.addEventListener('click', () => {
    const filter = button.getAttribute('data-filter');
    // Lógica de filtragem...
  });
});
```

### Integração WhatsApp
```javascript
// Gera URL do WhatsApp com mensagem personalizada
const productName = button.getAttribute('data-product');
const message = encodeURIComponent(`Olá! Tenho interesse no produto: ${productName}...`);
const whatsappUrl = `https://wa.me/5551989030405?text=${message}`;
```

### Animações e Intersection Observer
```javascript
// Anima elementos quando entram no viewport
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.style.opacity = '1';
      entry.target.style.transform = 'translateY(0)';
    }
  });
}, observerOptions);
```

## 🎯 Casos de Uso

Ideal para:
- Lojas de varejo que querem vender pelo WhatsApp
- E-commerces que desejam um catálogo visual simples
- Representantes comerciais e revendedores
- Negócios locais que dependem de atendimento personalizado
- Qualquer empresa que precise de um catálogo online profissional

## 📞 Suporte

Para dúvidas, personalizações ou contratar desenvolvimento similar:

- **WhatsApp**: [+55 51 98903-0405](https://wa.me/5551989030405)
- **Email**: [tiago@fariasdigital.com.br](mailto:tiago@fariasdigital.com.br)
- **Portfolio**: [tofariasti.github.io](https://tofariasti.github.io/)

## 📄 Licença

Este projeto é um concept demo desenvolvido por Tiago O. de Farias.

Para uso comercial, entre em contato para licenciamento e personalização.

## 🏆 Créditos

**Desenvolvido por Tiago O. de Farias**
- Portfolio: [tofariasti.github.io](https://tofariasti.github.io/)
- GitHub: [@tofariasti](https://github.com/tofariasti)
- Site: [fariasdigital.com.br](https://fariasdigital.com.br/)

---

⭐ Se este projeto foi útil, considere dar uma estrela no GitHub!
