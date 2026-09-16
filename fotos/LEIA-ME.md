# Fotos do convite

| Arquivo | Onde aparece | Status |
|---|---|---|
| `casal.jpg` | Foto grande no topo do convite | ✅ no lugar |
| `local.jpg` | Foto do Armazém Secos e Molhados | opcional, ainda não enviada |

## Para trocar ou acrescentar uma foto

- Use exatamente esses nomes, em **minúsculas**, terminando em `.jpg`.
- `casal.jpg`: vertical ou quadrada, com o casal centralizado. Ideal ~1200 × 1600 px.
- `local.jpg`: horizontal. Ideal ~1200 × 800 px.
- Se um arquivo não existir, o convite continua funcionando: aquele bloco
  simplesmente não aparece — nada quebra e nada fica com ícone de imagem quebrada.
- Tente deixar cada foto abaixo de **1 MB** para o convite abrir rápido no celular.

## Sobre o enquadramento

A foto do casal é recortada pelo topo. O ponto de corte está no `index.html`, em
`.hero-photo img { object-position: 50% 14%; }` (e `50% 12%` para telas grandes).
Se um dia trocar a foto e os rostos ficarem altos ou baixos demais, é só mexer
nesse segundo número: **menor** mostra mais do topo, **maior** mostra mais da base.
