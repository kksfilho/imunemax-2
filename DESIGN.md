# DESIGN.md — Imunemax (Versão 2)

> Spec de sistema de design no formato [DESIGN.md](https://stitch.withgoogle.com/docs/design-md/specification/) (Google Stitch). Escrito antes do código — o `index.html` desta pasta foi construído para segui-lo à risca. Paleta e tipografia próprias, pensadas para a Imunemax; não reutiliza o visual escuro/motion-first do exemplo Framer que inspirou o formato — só o processo (documentar o sistema em markdown antes de codar) foi aproveitado.

Base de conteúdo e regras de negócio: `../melhorespraticas.md`.

---

## 1. Visual Theme & Atmosphere

**Conceito: "Clínico-acolhedor".** Em vez do registro industrial/corporativo comum em sites de dedetizadora (ícones de inseto cruzado, paleta fria, texto denso), a Versão 2 pega emprestado o vocabulário visual de uma clínica de saúde moderna — bordas arredondadas, muito espaço em branco, formas orgânicas suaves (ondas/blobs entre seções) — e aplica a uma empresa de controle de pragas e desentupimento. A ideia: transmitir *cuidado com saúde e higiene* em vez de *combate/extermínio*, o que também compensa a ausência de prova social (empresa nova, sem reviews) com uma sensação imediata de limpeza, ordem e confiança.

Humor: calmo, gentil, seguro — nunca urgente-agressivo. Assimetria controlada (hero com imagem sangrando até a borda) em vez do grid perfeitamente simétrico da Versão 1.

## 2. Color Palette & Roles

| Token | Hex | Papel |
|---|---|---|
| `--bg` | `#F3F6F1` | Fundo base — verde-sálvia muito claro, não branco puro |
| `--surface` | `#FFFFFF` | Cards e superfícies elevadas |
| `--ink` | `#1B2620` | Texto principal |
| `--ink-soft` | `#57685C` | Texto secundário |
| `--line` | `#DCE5DD` | Bordas sutis |
| `--primary` | `#14524B` | Marca — verde-petróleo profundo (associação a água limpa/saúde); usado em headers, nav, texto de destaque |
| `--primary-soft` | `#E3EFEA` | Fundos suaves de badges/ícones sobre `--primary` |
| `--lime` | `#7DC400` | Cor de ação (CTA) — a mesma verde-limão da marca/logo, mantida igual à Versão 1 por continuidade de marca |
| `--lime-deep` | `#5E9600` | Hover/estado ativo do CTA |
| `--urgent` | `#E2673F` | Semântica de urgência (badge "emergência 24h") — cor separada do accent, usada só ali |

Regra: `--primary` (petróleo) é a cor de identidade/estrutura; `--lime` é *exclusivamente* ação (botões, links de CTA, ícones de confirmação). Nunca usar `--lime` como cor de fundo de seção inteira — vira ruído.

## 3. Typography Rules

- **Display:** `Fraunces` (serifada, com curvas suaves e ductos óticos) — pesos 500/600, `font-optical-sizing: auto`. Usada em títulos de seção e headline do hero. Traz o tom "acolhedor" que a Versão 1 (Manrope, geométrica) não tem.
- **Corpo:** `Nunito Sans` — pesos 400/600/700. Cantos levemente arredondados nas formas das letras, reforça a atmosfera "clínico-acolhedor" mesmo no texto corrido.
- Hierarquia: H1 `clamp(34px,5vw,54px)`, H2 `clamp(26px,3.4vw,36px)`, corpo `16px/1.7`, legendas `13px` com `letter-spacing:0.5px`.
- Nunca usar mais de 2 pesos por elemento. Títulos sempre com `text-wrap:balance`.

## 4. Component Stylings

- **Botões:** totalmente arredondados (`border-radius:100px`, formato pílula) — diferente dos botões `border-radius:8px` da Versão 1. Primário = `--lime` com texto `--primary` escuro (não branco — mais suave). Estados hover: leve escala (`scale(1.03)`) + sombra colorida suave (ver seção 6).
- **Cards:** `border-radius:20px`, sem borda dura — usam sombra difusa em vez de `border:1px solid`. Ícones em círculo (não quadrado com cantos levemente arredondados como na V1) preenchidos com `--primary-soft`.
- **Inputs (formulário):** `border-radius:14px`, fundo `--bg` (não branco) com borda que só aparece no focus.
- **Badges/chips:** pílula, fundo `--primary-soft`, texto `--primary`.
- **Divisores de seção:** onda SVG suave (`<svg>` com path de curva) entre hero e a seção seguinte, em vez de uma linha reta — reforça o tema orgânico.

## 5. Layout Principles

- Escala de espaçamento base: `8px` (8/16/24/32/48/64/96).
- Container principal: `max-width:1120px`, padding lateral `6%`.
- Hero **assimétrico**: imagem em coluna de largura irregular (não 50/50 como a V1), com um blob de cor atrás dela.
- Seções alternam fundo `--bg` / `--surface` para criar ritmo visual sem precisar de bordas.
- Uma ideia por seção — nenhuma seção deve ter mais de 2 blocos de conteúdo distintos.

## 6. Depth & Elevation

- Sombras **difusas e tingidas** com a cor primária em baixa opacidade, nunca cinza neutro puro: `box-shadow: 0 20px 40px -12px rgba(20,82,75,0.18)`.
- 3 níveis: `--elev-1` (cards em repouso, sombra sutil), `--elev-2` (hover, sombra mais larga e suave), `--elev-3` (modal/popup, sombra mais escura e próxima).
- Nunca usar sombra dura (`0 2px 4px rgba(0,0,0,.5)`) — quebra a atmosfera acolhedora.

## 7. Do's and Don'ts

**Faça:**
- Use formas arredondadas e curvas orgânicas (blobs, ondas) como elemento recorrente.
- Mantenha o texto sempre gentil/tranquilizador, mesmo em CTAs de urgência ("Fale com a gente agora" em vez de "LIGUE JÁ!!").
- Deixe respiro generoso — nenhuma seção deve parecer densa.
- Seja honesto: nenhuma nota, avaliação ou depoimento fictício (a empresa é nova — ver `../melhorespraticas.md`).

**Não faça:**
- Não use ícones de inseto/praga de forma literal (barata, rato desenhados) — reforça o registro "extermínio", contrário ao conceito.
- Não use cantos retos ou sombras duras — quebra o sistema.
- Não empilhe mais de 3 CTAs na mesma seção — dilui a ação.
- Não use `--lime` como fundo de seção grande — é cor de ação, não de ambientação.

## 8. Responsive Behavior

- Breakpoint único principal: `768px`. Abaixo disso, todo grid de 2 colunas vira 1 coluna, na ordem: conteúdo → imagem.
- Botão de WhatsApp flutuante vira formato pílula com texto visível permanentemente em mobile (não só no hover, que não existe em touch).
- Nav colapsa para um menu inferior fixo (bottom sheet) em vez do drawer superior da Versão 1 — variação deliberada para diferenciar a experiência mobile das duas versões.
- Tipografia do H1 nunca abaixo de `32px` mesmo na tela mais estreita (400px).

## 9. Agent Prompt Guide

Resumo rápido para regenerar componentes desta versão de forma consistente:

> "Site institucional Imunemax, tema clínico-acolhedor: fundo `#F3F6F1`, cards brancos com `border-radius:20px` e sombra difusa verde-petróleo (`rgba(20,82,75,0.18)`), sem bordas duras. Títulos em Fraunces (serifada suave), corpo em Nunito Sans. Botões sempre em pílula (`border-radius:100px`), cor de ação `#7DC400` com texto `#14524B`. Ícones em círculo preenchido `#E3EFEA`, nunca ícones literais de praga. Curvas orgânicas entre seções, nunca linhas retas de divisão. Nunca inventar nota do Google, depoimento ou avaliação — a empresa é nova."
