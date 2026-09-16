# Convite de casamento — Maria & Felipe

Convite digital de página única. Tudo vive no `index.html` — sem servidor, sem
banco de dados, sem dependência de build.

**28 de novembro de 2026 · sábado · 16h**
Armazém Secos e Molhados — Bairro Monte Alegre, Pratânia / São Manuel — SP

---

## O que o convite tem

- Abertura com o monograma **M & F** — laurel de oliveira desenhado em SVG,
  feito sob medida para o convite
- Paleta **branco + verde oliva**
- Foto do casal no topo
- Versículo de **Mateus 19:6**
- Cerimônia e recepção no mesmo local, com botão "Ver no mapa"
- Contagem regressiva até o grande dia
- Música ambiente tocando desde a abertura, com botão flutuante para pausar
- Dress code: traje social, com as cores reservadas
- **Manual dos convidados** — 10 tópicos em acordeão
- Confirmação de presença pelo WhatsApp **(14) 99754-4105**, sem prazo

## Como editar

O que muda com frequência está reunido no começo do `<script>`, em dois blocos:

| Bloco | O que controla |
|---|---|
| `CONFIG` | nomes, data, horário, cidade, link do mapa, WhatsApp, música, versículo |

### A música

O convite toca um **arquivo de áudio hospedado junto com ele** — não usa o
YouTube. O vídeo escolhido pelos noivos tem a reprodução bloqueada fora do
site do YouTube, então embutir não funciona: o navegador se recusa a tocar e
a única saída seria mandar o convidado para fora do convite.

Para colocar a música:

1. Suba o arquivo de áudio (`.mp3`) nesta pasta, junto do `index.html`
2. Escreva o nome dele em `CONFIG.musica` (o padrão é `musica.mp3`)

Enquanto o arquivo não existir, o convite funciona normalmente — o botão de
música simplesmente não aparece. Para deixar o convite sem música de vez, é só
pôr `musica: ''`.
| `MANUAL` | os tópicos do Manual dos convidados (título, texto e ícone) |

Para acrescentar um tópico ao manual, copie uma linha do `MANUAL` e troque o
texto. Os ícones disponíveis estão logo abaixo, no objeto `ICONES`:
`chat`, `ring`, `dress`, `cheers`, `cake`, `vase`, `users`, `clock`, `camera`, `heart`.

## Fotos

Ficam na pasta [`fotos/`](fotos/LEIA-ME.md). A foto do casal já está lá.
A do local (`fotos/local.jpg`) é opcional — sem ela, aquele bloco simplesmente
não aparece.

## Como publicar

Sendo um arquivo só, dá para publicar no **GitHub Pages**
(Settings → Pages → branch `main`, pasta `/root`), Netlify, Vercel ou qualquer
hospedagem estática. Depois é só mandar o link no WhatsApp.

## Detalhes técnicos

- Pensado para celular (o convite circula por WhatsApp), mas se adapta a telas grandes
- Fontes: Bodoni Moda + Jost (Google Fonts)
- A música começa a tocar **mudo** assim que a página carrega (o único autoplay
  que os navegadores permitem sem interação) e o toque em "toque para abrir"
  apenas tira o mudo — por isso ela entra na hora, sem espera. Nenhum navegador
  de celular permite som antes de um toque do usuário, então esse é o mais
  automático que dá para ser.
- Se o arquivo de áudio faltar ou o formato não for suportado, o botão de
  música some e o convite segue normal — nunca manda o convidado para fora
- Respeita `prefers-reduced-motion` para quem prefere menos animação
