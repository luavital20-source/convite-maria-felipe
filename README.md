# Convite de casamento — Maria & Felipe

Convite digital de página única (um só arquivo: `index.html`).

**28 de novembro de 2026 · sábado · 16h**
Armazém Secos e Molhados — Bairro Monte Alegre, Pratânia / São Manuel — SP

---

## ✅ O que já está pronto

- Abertura (splash) com monograma **M & F** — laurel de oliveira desenhado em SVG,
  feito sob medida para o convite
- Paleta **branco + verde oliva**
- Versículo de **Mateus 19:6**
- Cerimônia e recepção no mesmo local, com botão "Ver no mapa"
- Contagem regressiva até o grande dia
- Música ambiente: vídeo do YouTube tocando ao abrir o convite, com botão de pausar
- Dress code com as cores reservadas
- **Manual dos convidados** (9 tópicos, em acordeão)
- **Lista de presentes** com 16 cotas e pagamento por Pix "copia e cola"
- Confirmação de presença pelo WhatsApp **(14) 99754-4105**

## ⚠️ O que falta preencher

### 1. A chave Pix (obrigatório para a lista de presentes)

Abra o `index.html`, procure o bloco `const CONFIG` (perto do começo do `<script>`)
e preencha:

```js
pixChave:   '',              // ← CPF, telefone, e-mail ou chave aleatória
pixTitular: 'Maria e Felipe',
```

Enquanto a chave estiver vazia, o convite **não quebra**: ao tocar em
"Presentear", o convidado vê um aviso de que a chave está sendo cadastrada e um
botão para falar com os noivos pelo WhatsApp.

Com a chave preenchida, o convite gera sozinho o código Pix de cada cota, já com
o valor certo — o convidado só cola no app do banco.

### 2. As fotos

Veja as instruções em [`fotos/LEIA-ME.md`](fotos/LEIA-ME.md).

---

## ✏️ Como editar

Tudo que muda com frequência está reunido no começo do `<script>`, em três blocos:

| Bloco | O que controla |
|---|---|
| `CONFIG` | nomes, data, horário, cidade, link do mapa, WhatsApp, música, Pix, versículo |
| `MANUAL` | os tópicos do Manual dos convidados |
| `PRESENTES` | as cotas da lista de presentes (nome, descrição, valor, ícone) |

Para trocar um valor de presente, basta mudar o número em `valor:` — o código Pix
é gerado a partir dele automaticamente.

## 🌐 Como publicar

O convite é um arquivo só, sem servidor e sem banco de dados. Pode ser publicado
no **GitHub Pages** (Settings → Pages → branch `main`, pasta `/root`), Netlify,
Vercel ou qualquer hospedagem simples.

## 📱 Detalhes técnicos

- Feito para celular (o convite é enviado por WhatsApp), mas se adapta a telas grandes
- Fontes: Bodoni Moda + Jost (Google Fonts)
- Música pelo player do YouTube, iniciada pelo toque do convidado em "toque para abrir"
  (assim o navegador não bloqueia o áudio)
- Código Pix no padrão BR Code do Banco Central, gerado no próprio navegador
- Respeita `prefers-reduced-motion` para quem prefere menos animação
