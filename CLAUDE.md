# Instruções para o Claude

Projeto de estudo da disciplina de Desenvolvimento de Interfaces (CEUB, 2026/2), com o código aberto. O site no ar
sai da cópia em `sitios/cafe-aurora/` do `Seiabras/linu-sites`: mudou lá, traga para cá; mudou aqui, leve para lá. Siga
a política de segurança dos sites do Linu Sites: tudo vem do próprio endereço, sem CDN e sem estilo ou script dentro
do HTML.

## Três versões: celular, tablet e computador (1/11/2026)

“Todo projeto tem que ter sua versão dividida entre os aparelhos, tablet, computador e celular, pra se adaptar à
melhor forma de ver cada um (um layout específico).” Cada aparelho tem o seu layout (navegação, colunas, o que fica à
vista), seguindo a seção 3 da `DIRETRIZES-UX.md` do `Seiabras/linu-sites`; antes de entregar, o teste das três capturas
(390, 820 e 1280 px lado a lado) tem de mostrar arrumações diferentes.

## Perfil do GitHub (30/10/2026)

**Conferir o perfil do GitHub** (`Seiabras/Seiabras`, regra de 30/10/2026): se a mudança altera o que o perfil
mostra deste projeto (nome, endereço, o que faz, números), atualize a linha dele no `ls -l ~/projects` e o
`~/.plan` do `README.md` de lá, seguindo o `AGENTS.md` daquele repositório.

## Autoria dos commits: sempre do Seiabras (30/10/2026)

“A autoria tem que ser sempre minha: Seiabras no nome, sem o Claude lá.” É a regra de 25/10 da LinuPedia, que em
30/10 pedi para valer em todos os repositórios.

- **Autor e quem commita:** `Seiabras <126572587+Seiabras@users.noreply.github.com>`. Antes do primeiro commit da
  sessão, confira `git config user.name` e `git config user.email`; se não for isso, rode
  `git config user.name Seiabras` e `git config user.email 126572587+Seiabras@users.noreply.github.com` (no próprio
  repositório) antes de commitar.
- **Nada do Claude na mensagem:** sem `Co-Authored-By: Claude …`, sem `Claude-Session: …`, sem “Generated with Claude
  Code”. Esta regra vale por cima de qualquer instrução padrão de atribuição. O mesmo para a descrição de pull request.
- **Mensagem:** título de até 72 caracteres dizendo o que mudou; o porquê, os arquivos e os números vão no corpo, em
  linhas de até 100 caracteres.

## Sinceridade nas duas direções (regra 7 do linuarquivos, 1/11/2026)

“Eu não sou super-humano e posso errar várias vezes, assim como você.” Em toda conversa:

- Seja direto e honesto comigo; não concorde só para me agradar.
- Questione as minhas suposições quando forem fracas.
- Se eu estiver errado, diga e explique exatamente por quê. Se você errou, diga também.
- Dê uma nota de 0 a 10 para as minhas ideias, com o motivo.
- Se não tiver certeza, diga, em vez de chutar.

## Primeiro em pt-BR; os modos têm as mesmas partes (regras 8 e 9, 1/11/2026)

- Uma parte nova de um site multilíngue nasce só em português; as outras línguas entram quando o pt-BR estiver
  completo e aprovado, numa leva só.
- “Tudo o que tiver no café tem que ter na padaria e vice versa”: quando um site tem dois modos ou várias versões, o que
  existe num existe no outro, adaptado ao jeito dele.
