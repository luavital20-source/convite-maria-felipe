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
- Lista de presentes (site externo) e chave Pix, com botão de copiar
- Confirmação de presença pelo WhatsApp **(14) 99754-4105**, sem prazo

## Como editar

O que muda com frequência está reunido no começo do `<script>`, em dois blocos:

| Bloco | O que controla |
|---|---|
| `CONFIG` | nomes, data, horário, cidade, link do mapa, WhatsApp, música, Pix, versículo |

### Os presentes

A seção tem duas opções, e cada uma aparece só se estiver preenchida:

- **`CONFIG.listaPresentes`** — link do site da lista (hoje, Final Feliz).
  Abre em nova aba, para o convidado não perder o convite.
- **`CONFIG.pixChave`** / **`CONFIG.pixTitular`** — o cartão do Pix.

O separador "ou, se preferir, por Pix" só aparece quando as duas existem. Com
os dois campos vazios, a seção inteira some do convite. Uma chave de 11 dígitos é reconhecida como CPF e exibida formatada
(`451.194.328-16`); telefone, e-mail ou chave aleatória aparecem como foram
escritos. O botão copia sempre a chave crua, que é o que se cola no app do
banco. Com `pixChave: ''`, a seção inteira some do convite.

### A música

O convite tenta duas fontes, nesta ordem:

1. **`CONFIG.musica`** — um arquivo de áudio hospedado nesta mesma pasta
   (o padrão é `musica.mp3`). É o caminho mais confiável: toca sempre, não
   depende de ninguém.
2. **`CONFIG.musicaYoutube`** — se o arquivo não existir, o convite tenta o
   vídeo do YouTube. Só funciona se o dono do vídeo permitir a reprodução fora
   do YouTube; muitos vídeos bloqueiam isso, e não há nada a fazer do nosso lado.

Se nenhuma das duas tocar, o botão de música simplesmente não aparece e o
convite segue normal. Em nenhum caso o convidado é mandado para fora.

Hoje o convite usa o arquivo `musica.mp3` desta pasta, então o YouTube não
chega a ser consultado. Para deixar o convite sem música de vez, ponha os dois
campos vazios (`''`).

O arquivo foi reduzido de 320 kbps (7,8 MB) para 128 kbps (3,1 MB): a música
tem 3min23s e toca em fundo, no alto-falante do celular, onde a diferença não
se ouve — mas 4,7 MB a menos pesam bastante para quem abre o convite no 4G.
O original continua no histórico do Git, caso queiram voltar atrás.
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
- Se nenhuma fonte de música tocar, o botão some e o convite segue normal —
  nunca manda o convidado para fora
- O player do YouTube fica num contêiner recortado a 1px e invisível, mas o
  iframe em si continua com tamanho normal: navegadores tratam melhor a mídia assim
- Respeita `prefers-reduced-motion` para quem prefere menos animação
