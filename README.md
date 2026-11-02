# Café Aurora

> **In English:** a fictional cyberpunk café "hidden between dimensions", built for the Interface Development course
> (CEUB, 2026/2). The same prompt went to three AIs (ChatGPT, Gemini and DeepSeek); I picked the best result, studied it
> and rebuilt the code step by step. It comes in five builds (plain CSS, Bootstrap, Tailwind, Bulma and Pico), in 13
> languages, and turns into a bakery by day. Live: https://cafe.linupedia.com.br

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
| Bulma 1.0 | [`/bulma/`](https://cafe.linupedia.com.br/bulma/) | Colunas e componentes prontos como no Bootstrap, mas só CSS, sem script; a compilação com prefixo `bulma-` e sem utilitários (em `bulma/vendor/`) para não brigar com o tema |
| Pico CSS 2 | [`/pico/`](https://cafe.linupedia.com.br/pico/) | Quase sem classes: estiliza as próprias tags (`nav`, `button`, `input`, `article`); o HTML fica o mais limpo dos cinco, e o trabalho é desfazer o que ele faz sozinho (em `pico/vendor/`) |

As cinco têm o mesmo conteúdo: tela de abertura, cursor próprio, fundo de partículas em canvas, seções que aparecem ao
rolar, cardápio, um “laboratório” para montar a bebida (a xícara é desenhada só com CSS) e um painel que desloca o
matiz de todas as cores.

## Idiomas

O site está em 13 idiomas: português do Brasil na raiz e `/pt-pt/`, `/es/`, `/ca/`, `/nl/`, `/en/`, `/fr/`, `/de/`,
`/it/`, `/intl/` (inglês internacional), `/ja/`, `/ko/` e `/zh-hant/`, com as alternativas
de cada página para os buscadores; o simulador de cada idioma do Linu Sites abre o Café no mesmo idioma. As páginas de cada idioma são geradas no repositório do
[Linu Sites](https://github.com/Seiabras/linu-sites) (o modelo e os textos ficam em `ferramentas/cafe/`); aqui ficam as
páginas prontas. As frases que o script escreve vão num `<script type="application/json">` em cada página.

Desde 1/11/2026, as versões `/bootstrap/` e `/tailwind/` também estão nos 13 idiomas (`/<idioma>/bootstrap/`,
`/<idioma>/tailwind/`), e a Bulma e a Pico também (`/<idioma>/bulma/`, `/<idioma>/pico/`): 65 páginas no total. Só a
`versoes.html` fica em português, porque é da disciplina.

## Trocar de versão e entender o que muda (1/11/2026)

O rodapé de cada versão tem a mesma lista (CSS puro · Bootstrap · Tailwind · Bulma · Pico · comparar as cinco), que
leva de qualquer uma para qualquer outra, com a atual marcada. A página [`versoes.html`](versoes.html), só em
português, explica o que muda quando entra um framework: a ideia de cada um, quem faz o layout, como fica o HTML, o
tema, o JavaScript, o peso e o que quebrou de verdade ao trocar. O peso do código comprimido (CSS e scripts, sem fontes
nem imagens): CSS puro 40 KB, Bootstrap 83 KB, Tailwind 30 KB, Bulma 63 KB e Pico 41 KB.

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

## Um café “de verdade” (1/11/2026)

Só na versão em CSS puro (as outras duas ficam como a página original, para comparar o jeito de fazer):

| O quê | Como funciona |
|---|---|
| Pedido | “+ Pedido” em cada item do cardápio e “Adicionar ao pedido” no laboratório; o “Pedir agora” abre o pedido, com quantidades, total, nome (validado na hora), comer aqui ou levar, hora e observação. “Mandar no WhatsApp” abre a mensagem pronta. O Café é fictício: o WhatsApp abre sem número, para a pessoa escolher o contato. |
| Cardápio | Filtros (de noite: quente, gelado, doce, intenso, sem lactose, sem cafeína; de dia: doce, salgado, saindo do forno, sem lactose, sem glúten) e “Detalhes” em cada item (temperatura, cafeína, calorias, alérgenos). |
| Teste | “Que bebida combina com você?” (de dia, “que pão”): três perguntas e o item do cardápio que mais combina, com o botão de pedir. |
| Reservas | Nome, pessoas, dia e hora, com erro ao lado do campo; a hora respeita o horário (o café fecha das 4h às 6h; a padaria abre das 6h às 18h). As reservas ficam listadas, com “Confirmar no WhatsApp” e “Cancelar”. |
| Cartão de carimbos | Cada pedido mandado vale um carimbo; com dez, “o próximo é por conta da casa”. |
| Sem internet | `sw.js` e `manifest.webmanifest`: a página principal e o que ela usa ficam guardados; os outros idiomas e versões, quando a pessoa os abre. |

O que a pessoa faz fica no `localStorage` do navegador. Embutido no simulador do Linu Sites, nada disso aparece: o
simulador só mostra as partes que estão na tabela de preços dele.

Lighthouse no celular (1/11/2026, servidor local, sem compressão): a página principal com 93 de desempenho e 100 em
acessibilidade, boas práticas e SEO; a `versoes.html` com 99 e 100. O axe 4.10 não acha falha de dia nem de noite, em
390 e 1280 px.

## Café e padaria com as mesmas partes (1/11/2026)

Tudo o que o café tem, a padaria tem, e vice-versa: os quatro detalhes de cada item, seis filtros (de dia: doce, salgado,
saindo do forno, sem lactose, sem glúten e vegano), o teste, o pedido e as reservas. As versões com framework
também viram padaria de dia, com o botão de sol e lua, o pão do “Monte o seu pão” e a farinha no ar, pelos arquivos
`padaria.css` e `padaria.js`, que as quatro usam. No simulador do Linu Sites, o pedido, o cardápio com filtros, o teste,
as reservas e o cartão de carimbos são módulos com preço, que ligam e desligam ali.

## Os modificadores aparecem na xícara (1/11/2026)

No “Monte sua bebida”, cada modificador muda a xícara, como as coberturas mudam o pão de dia: a Poeira de Cometa cai do
alto em brilhos, a Espuma de Plasma faz uma espuma rosa que pulsa, o Cristal de Açúcar boia na bebida e a Flor de Neon
gira sobre a espuma. O script põe `com-1` a `com-4` na `.cup-wrap`; nas versões com framework, quem faz isso é o
`padaria.js`. Com “menos movimento”, aparecem parados.

## A abertura (1/11/2026)

A tela de abertura (“Calibrando moagem quântica…”, de dia “Acendendo o forno…”) é a exceção “abertura de identidade”
das diretrizes de UX do Linu Sites: aparece só na primeira página da sessão (`sessionStorage`, classe `ja-abriu` posta
pelo `inicio.js`), dura 3 s, some com um toque em qualquer lugar, no botão “Pular abertura” ou com Esc, Enter ou
espaço, e fica parada com “menos movimento”. Vale nas cinco versões. Embutido no simulador do Linu Sites, ela só
aparece quando alguém liga o módulo “Abertura de identidade” ou toca em “Ver a abertura”, com a duração escolhida ali
(1,5 ou 3 s).

## Segurança

O site segue a mesma política de segurança dos sites do Linu Sites: tudo vem do próprio endereço, sem CDN, sem fonte
do Google e sem estilo ou script dentro do HTML. Por isso as fontes (Orbitron e Rajdhani, licença OFL em
`fontes/OFL.txt`), o Bootstrap, a Bulma e a Pico (licença MIT, cada uma no seu `vendor/`) ficam aqui dentro, e o Tailwind vai compilado.

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

## Três versões: celular, tablet e computador (1/11/2026)

Pela regra 6 do linuarquivos, cada aparelho tem o seu layout:

| | Celular (até 699 px) | Tablet (700 a 1099 px) | Computador (1100 px ou mais) |
|---|---|---|---|
| Ação principal | “Pedir agora” preso embaixo, ao alcance do polegar, com o número de itens; o pedido sobe de baixo | no menu de gaveta; o pedido abre no meio | no topo, sempre à vista; o pedido abre numa gaveta à direita |
| Cardápio | faixa que rola de lado, um cartão por vez | 2 colunas | 3 colunas |
| Monte o seu pão | o montador e o pão um embaixo do outro | lado a lado | lado a lado, maior |
| Sintonizar dimensão | recolhido acima do botão de pedir | aberto no canto | aberto no canto |

Também deixou de rolar de lado no celular (o menu de gaveta e o halo do topo esticavam a página para 445 px).

