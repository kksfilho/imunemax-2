# Imunemax — Site Estático

**Stack:** HTML + CSS + JS (arquivo único) · Deploy via GitHub → Hostinger Git

---

## Estrutura de pastas

```
/
├── index.html              ← site oficial
├── DESIGN.md               ← sistema de design do site (cores, tipografia, componentes)
├── melhorespraticas.md     ← base de decisões do projeto (pesquisa de concorrência, plano de ação, histórico)
├── README.md
├── robots.txt
├── sitemap.xml
└── assets/
    └── img/
        ├── imunemax-logo.png
        ├── imunemax-hero.jpg      ← não usado no site atual (mantido por compatibilidade)
        ├── imunemax-og.jpg        ← imagem de preview WhatsApp/redes (1200×630px)
        ├── favicon-32.png
        ├── favicon-16.png
        └── apple-touch-icon.png
```

---

## Como atualizar o GitHub

```bash
git add .
git commit -m "sua mensagem"
git push
```

## Como conectar ao Hostinger (primeira vez)

1. Painel Hostinger → **Hospedagem** → **Git**
2. Conecte o repositório GitHub `imunemax`
3. Branch: `main` | Diretório: `/public_html`
4. Ative deploy automático

A partir daí: `git push` → site atualizado em segundos.

**Importante:** ativar o deploy automático no Hostinger substitui o conteúdo atual de `/public_html` pelo conteúdo deste repositório. Se já existir um site publicado nesse diretório, ele será sobrescrito.

---

## SEO implementado

- ✅ `<title>` e `<meta description>` com palavras-chave, localização e "15 anos de experiência"
- ✅ Open Graph (Facebook, WhatsApp, LinkedIn) e Twitter Card
- ✅ Schema.org `LocalBusiness` com endereço, telefone, geo, área de cobertura e catálogo de serviços
- ✅ Schema.org `FAQPage` com 9 perguntas (sincronizado com o FAQ visível na página)
- ✅ `<link rel="canonical">`, `robots.txt`, `sitemap.xml`
- ✅ `theme-color` para navegadores mobile
- ✅ Hierarquia de headings sem pular nível (H1→H2→H3→H4)
- ✅ Contraste de cor verificado (WCAG AA) em todos os pares texto/fundo
- ✅ `prefers-reduced-motion` respeitado
- ✅ Estado de foco de teclado (`:focus-visible`) visível em todos os elementos interativos
- ✅ `aria-label`/`role="dialog"` no menu mobile e no popup de orçamento
- ✅ `rel="noopener noreferrer"` em links externos, `<address>` semântico, links `tel:`

## Sobre o conteúdo

A Imunemax é uma empresa real com **15 anos de experiência** — mas ainda não tem nota/avaliações do Google nem depoimentos organizados digitalmente. O site foi construído para **não inventar** essas informações (ver `melhorespraticas.md`). Pontos ainda pendentes de confirmação com o cliente antes de expandir o conteúdo: se o orçamento é gratuito, formas de pagamento aceitas, horário real de atendimento, e se os links de Instagram/Facebook estão ativos.
