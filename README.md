# Café Aurora

Site de uma cafeteria fictícia, cyberpunk, “escondida entre dimensões”. Fiz para a disciplina de Desenvolvimento de
Interfaces (CEUB, 2026/2), na atividade em que o mesmo prompt foi usado em três IAs (ChatGPT, Gemini e DeepSeek) para
gerar páginas com HTML, CSS e JavaScript. Escolhi a versão do DeepSeek como a melhor, estudei e reconstruí o código
passo a passo, e hoje ele é o site de exemplo do simulador do [Linu Sites](https://sites.linupedia.com.br/#exemplo).

**No ar:** https://cafe.linupedia.com.br

## Versões

| Versão | Endereço | O que muda |
|---|---|---|
| CSS puro | [`/`](https://cafe.linupedia.com.br/) (`index.html`, `estilo.css`, `script.js`) | Todo o layout e o tema escritos à mão; é a versão que aparece no simulador do Linu Sites |
| Bootstrap 5.3 | [`/bootstrap/`](https://cafe.linupedia.com.br/bootstrap/) | O grid, a navbar e os utilitários vêm do Bootstrap (em `bootstrap/vendor/`); o tema neon sobrescreve os componentes |
| Tailwind CSS 3.4 | [`/tailwind/`](https://cafe.linupedia.com.br/tailwind/) | O layout vira classes utilitárias no HTML, compiladas em `tailwind/tailwind.css`; o CSS próprio fica com o tema e as animações |

As três têm o mesmo conteúdo: tela de abertura, cursor próprio, fundo de partículas em canvas, seções que aparecem ao
rolar, cardápio, um “laboratório” para montar a bebida (a xícara é desenhada só com CSS) e um painel que desloca o
matiz de todas as cores.

## Segurança

O site segue a mesma política de segurança dos sites do Linu Sites: tudo vem do próprio endereço, sem CDN, sem fonte
do Google e sem estilo ou script dentro do HTML. Por isso as fontes (Orbitron e Rajdhani, licença OFL em
`fontes/OFL.txt`) e o Bootstrap (licença MIT em `bootstrap/vendor/`) ficam aqui dentro, e o Tailwind vai compilado.

Dentro do simulador, a página do Linu Sites liga e desliga partes do Café por `postMessage`; o Café só aceita essas
mensagens de `https://sites.linupedia.com.br`.

## Como abrir

Pelo endereço acima, ou abrindo o `index.html` no navegador. Não tem build nem dependência para instalar.

## Acessibilidade

- Respeita `prefers-reduced-motion`: com “menos movimento” ligado no sistema, as animações param.
- O cursor próprio some em telas de toque.
- Link para pular direto ao conteúdo, foco visível e textos alternativos nos elementos decorativos.
