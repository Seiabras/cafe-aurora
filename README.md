# Café Aurora

Site de uma cafeteria fictícia, cyberpunk, “escondida entre dimensões”. Fiz para a disciplina de Desenvolvimento de
Interfaces (CEUB, 2026/2), na atividade em que o mesmo prompt foi usado em três IAs (ChatGPT, Gemini e DeepSeek) para
gerar páginas com HTML, CSS e JavaScript. Escolhi a versão do DeepSeek como a melhor e depois estudei e reconstruí o
código passo a passo.

**Ver no ar:** https://seiabras.github.io/cafe-aurora/

## Versões

| Versão | Arquivo | O que muda |
|---|---|---|
| CSS puro | [`index.html`](index.html) | Todo o layout e o tema escritos à mão, organizados em 16 blocos de CSS |
| Bootstrap 5.3 | [`bootstrap/index.html`](bootstrap/index.html) | O grid, a navbar e os utilitários vêm do Bootstrap; o tema neon sobrescreve os componentes |
| Tailwind CSS 3.4 | [`tailwind/index.html`](tailwind/index.html) | O layout vira classes utilitárias no HTML; o CSS próprio fica só com o tema e as animações |

As três têm o mesmo conteúdo e o mesmo JavaScript: tela de abertura, cursor próprio, fundo de partículas em canvas,
seções que aparecem ao rolar, cardápio, um “laboratório” para montar a bebida (a xícara é desenhada só com CSS) e um
painel que desloca o matiz de todas as cores.

## Como abrir

É só abrir o `index.html` no navegador. Não tem build nem dependência para instalar; o Bootstrap e o Tailwind vêm
por CDN.

## Acessibilidade

- Respeita `prefers-reduced-motion`: com “menos movimento” ligado no sistema, as animações param.
- O cursor próprio some em telas de toque.
- Link para pular direto ao conteúdo, foco visível e textos alternativos nos elementos decorativos.
