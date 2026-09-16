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
- Música ambiente (YouTube) tocando desde a abertura, com botão flutuante
  para pausar
- Dress code: traje social, com as cores reservadas
- **Manual dos convidados** — 10 tópicos em acordeão
- Confirmação de presença pelo WhatsApp **(14) 99754-4105**, sem prazo

## Como editar

O que muda com frequência está reunido no começo do `<script>`, em dois blocos:

| Bloco | O que controla |
|---|---|
| `CONFIG` | nomes, data, horário, cidade, link do mapa, WhatsApp, música, versículo |

Para trocar a música, cole o link do YouTube em `CONFIG.musica` — vale
`watch?v=…`, `youtu.be/…`, `/embed/…`, `/shorts/…` ou só o ID do vídeo.
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
- Se o vídeo não puder ser tocado dentro do convite (dono do vídeo bloqueou a
  reprodução em outros sites) ou o YouTube não carregar, o botão de música vira
  um link "Ouvir no YouTube" em vez de sumir
- Respeita `prefers-reduced-motion` para quem prefere menos animação
