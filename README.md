# lp-ferramentas — as quatro ferramentas novas

Página aberta pelo pop-up da área de membros. Quatro seções, uma por
ferramenta, cada uma com o vídeo do YouTube. Tema institucional escuro,
descrito na seção 1 de `../PADRAO-LP.md`.

## O que trocar

Tudo o que é conteúdo está marcado com `TROCAR:` no `index.html`.

| Onde | O que |
|---|---|
| `<title>`, `description`, `og:*` | título e frase da página |
| `.abertura h1` e o parágrafo | chamada da página |
| `nav.indice` | os quatro nomes, iguais aos dos títulos |
| Cada `<section class="ferramenta">` | `h2`, a linha de apoio, os três itens |
| `a.acao href="#"` | link direto da ferramenta dentro da plataforma |
| `.fecho` | chamada final e o link de volta para a plataforma |
| rodapé `.fino` | nome da peça |

## Os vídeos

Cada quadro é um `<button class="video">` com três atributos:

```html
data-video="ID_DO_VIDEO_1"      <!-- os 11 caracteres depois de watch?v= -->
data-titulo="Nome da ferramenta 1"
data-tempo="2:40"
```

O `data-tempo` também aparece escrito no `.rotulo`, logo abaixo — trocar nos
dois lugares.

Enquanto o `data-video` começar com `ID_DO_VIDEO`, o quadro mostra "Vídeo a
definir" e o clique não faz nada. Assim a página pode ir ao ar antes dos
vídeos ficarem prontos.

**Por que não quatro `<iframe>` direto:** quatro players do YouTube na carga
passam de 3 MB e dezenas de requisições, antes de a pessoa pedir qualquer
vídeo. Aqui a capa é só a imagem do próprio YouTube; o player entra no
clique, por `youtube-nocookie.com`, já com `autoplay`. A capa tenta
`maxresdefault` e cai para `hqdefault` quando o vídeo não tem a de alta.

## O link do pop-up

A página funciona sozinha, aberta em aba nova. O pop-up da área de membros
só precisa apontar para a raiz; para cair direto numa ferramenta, usar a
âncora: `…/#ferramenta-3`.

## Conferido antes de entregar

- Sem rolagem lateral em 1280 e em 500 de largura.
- Contraste medido **contra o fundo já iluminado** pelos brilhos: corpo
  14,9:1, texto mudo 6,7:1, apagado 4,9:1, branco no botão azul 8,2:1.
- Com movimento reduzido ligado, tudo aparece — os blocos não dependem da
  animação de entrada para existir.
- Capa, clique e player testados com um ID real: a capa carrega, o clique
  cria o `iframe` do domínio sem cookie, o segundo clique não duplica.
- Alvos de toque: botões de 48px, ícones de rede 44×44.
