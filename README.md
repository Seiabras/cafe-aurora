# Café Aurora

> **In English:** a fictional cyberpunk café "hidden between dimensions", built for the Interface Development course
> (CEUB, 2026/2). The same prompt went to three AIs (ChatGPT, Gemini and DeepSeek); I picked the best result, studied it
> and rebuilt the code step by step. It comes in three builds (plain CSS, Bootstrap and Tailwind), in 13 languages, and
> turns into a bakery by day. Live: https://cafe.linupedia.com.br

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

## Idiomas

O site está em 13 idiomas: português do Brasil na raiz e `/pt-pt/`, `/es/`, `/ca/`, `/nl/`, `/en/`, `/fr/`, `/de/`,
`/it/`, `/intl/` (inglês internacional), `/ja/`, `/ko/` e `/zh-hant/`, com as alternativas
de cada página para os buscadores; o simulador de cada idioma do Linu Sites abre o Café no mesmo idioma. As páginas de cada idioma são geradas no repositório do
[Linu Sites](https://github.com/Seiabras/linu-sites) (o modelo e os textos ficam em `ferramentas/cafe/`); aqui ficam as
páginas prontas. As frases que o script escreve vão num `<script type="application/json">` em cada página.

As versões `/bootstrap/` e `/tailwind/` continuam só em português.

## De dia, a Padaria Aurora

Das 6h às 18h no relógio de quem visita, o Café vira a Padaria Aurora: o mesmo universo da fenda, só que de manhã
(croissant de 2087 camadas, pão de gravidade zero). Mudam as cores (creme, trigo, casca), o fundo (farinha no ar em vez
da grade de neon), o letreiro, o cardápio, os depoimentos, o horário, e o laboratório vira “Monte o seu pão”: a
farinha, o tempo de forno (a casca doura e o pão cresce) e o que vai por cima.

- O `inicio.js` escolhe o modo antes de pintar (`data-modo` no `<html>`): primeiro `?modo=dia` ou `?modo=noite` no
  endereço, depois a escolha guardada pelo botão de sol e lua, depois o relógio. Sem JavaScript, fica o café.
- Cada texto que muda está duas vezes no HTML (`.so-noite` e `.so-dia`) e o CSS esconde o do outro modo. As cores de
  dia são as mesmas variáveis redefinidas no bloco 17 do `estilo.css`, e o painel de matiz gira as duas paletas.
- O botão faz a virada: o neon pisca, a tela se cobre, o sol nasce (ou a lua desce) e o modo troca por baixo. Com
  “menos movimento”, troca direto.

Para abrir direto a padaria: https://cafe.linupedia.com.br/?modo=dia

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
- O texto do rodapé usa a mesma cor suave do resto da página (não mais os 3,7:1 de antes), o link do rodapé é
  sublinhado e todo link e botão solto tem pelo menos 24 px de altura (WCAG 2.2, 2.5.8).
- Conferido com o axe 4.10 em 31/10/2026, de dia e de noite, nas três versões: nenhuma falha. Nas versões Bootstrap e
  Tailwind, o laboratório deixou de ser um `<form>` sem botão de enviar, como já era na versão principal.
