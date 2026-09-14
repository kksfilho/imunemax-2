# Imunemax — Site Estático

**Stack:** HTML + CSS + JS (single file) · Deploy via GitHub → Hostinger Git

---

## Estrutura de pastas

```
/
├── index.html              ← renomeie imunemax_v4.html para este nome
├── README.md
└── assets/
    └── img/
        ├── imunemax-logo.png       ← logo principal (PNG transparente, ~160×52px)
        ├── imunemax-hero.jpg       ← foto hero coluna direita (JPG, ~800×600px)
        ├── imunemax-og.jpg         ← imagem para WhatsApp/redes (JPG, 1200×630px)
        ├── favicon-32.png          ← favicon 32×32px
        ├── favicon-16.png          ← favicon 16×16px
        └── apple-touch-icon.png    ← ícone iOS 180×180px
```

---

## Como subir para o GitHub

```bash
# 1. Na pasta do projeto:
git init
git add .
git commit -m "feat: imunemax_v4 — SEO completo, Schema.org, imagens locais"
git remote add origin https://github.com/SEU_USUARIO/imunemax.git
git push -u origin main
```

## Como conectar ao Hostinger

1. Painel Hostinger → **Hospedagem** → **Git**
2. Conecte o repositório GitHub `imunemax`
3. Branch: `main` | Diretório: `/public_html`
4. Ative deploy automático

A partir daí: `git push` → site atualizado em segundos.

---

## Imagens — o que preparar

| Arquivo | Dimensão | Formato | Uso |
|---------|----------|---------|-----|
| `imunemax-logo.png` | 320×104px min | PNG transparente | Nav + Footer |
| `imunemax-hero.jpg` | 800×600px | JPG (qualidade 85) | Coluna direita hero |
| `imunemax-og.jpg` | 1200×630px | JPG (qualidade 85) | WhatsApp/Facebook preview |
| `favicon-32.png` | 32×32px | PNG | Aba do navegador |
| `favicon-16.png` | 16×16px | PNG | Aba do navegador |
| `apple-touch-icon.png` | 180×180px | PNG | iOS homescreen |

---

## SEO implementado na v4

- ✅ `<title>` otimizado com palavras-chave + localização
- ✅ `<meta description>` com CTA e telefone
- ✅ Open Graph (Facebook, WhatsApp, LinkedIn)
- ✅ Twitter Card
- ✅ Schema.org `LocalBusiness` com endereço, telefone, serviços, área de cobertura
- ✅ Schema.org `FAQPage` (3 perguntas)
- ✅ `<link rel="canonical">`
- ✅ `aria-label` em todas as seções
- ✅ `role="tablist"` / `role="tabpanel"` nas abas de serviços
- ✅ `aria-expanded` no hamburger
- ✅ `loading="lazy"` nas imagens do footer
- ✅ `loading="eager"` + `preload` no logo e hero
- ✅ `rel="noopener noreferrer"` em todos os links externos
- ✅ `<address>` semântico no footer
- ✅ Links de telefone com `href="tel:"`
- ✅ Link do endereço abrindo Google Maps
