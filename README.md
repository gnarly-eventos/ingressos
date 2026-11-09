# Ingressos · A Night To Remember e Nostalgias 2000

Página de links da bio: **https://gnarly-eventos.github.io/ingressos/**

- Direto na A Night To Remember: `https://gnarly-eventos.github.io/ingressos/#antr`
- Direto no Nostalgias 2000: `https://gnarly-eventos.github.io/ingressos/#nostalgias`

## Como os eventos atualizam

Um robô do próprio GitHub (`.github/workflows/publicar.yml`) roda **de hora em hora**:
busca os eventos publicados no Sympla, guarda só os da A Night To Remember e do Nostalgias
e publica a página de novo. Evento que já passou some sozinho.

Para atualizar na hora: aba **Actions** → **Publicar página** → **Run workflow**.

## Marcar esgotado, últimos ingressos, trocar título ou esconder

Edite o arquivo `ajustes.json` (pelo site do GitHub, no lápis ✏️) e coloque o id do evento
(está no `eventos.json`, ex.: `s36c760`):

```json
"eventos": {
  "s36c760": { "selo": "ultimos" },
  "s363ea0": { "selo": "esgotado" },
  "s376df9": { "titulo": "Baile de Formatura" },
  "s36bb03": { "ocultar": true }
}
```

Salve (Commit) e em cerca de 1 minuto a página atualiza.

## Onde mexer em links, fotos e textos

Tudo fica no começo do `<script>` do `index.html`:
- `FESTAS` → links (Sympla, WhatsApp, playlists, álbum, redes)
- `FOTOS` → fotos da Pasta de Fotos (pasta `fotos/`, cada foto tem a versão `-t` em miniatura)

## Tokens do Sympla

Ficam em **Settings → Secrets and variables → Actions** com os nomes
`SYMPLA_TOKEN_1` e `SYMPLA_TOKEN_2`. Nunca coloque o token dentro dos arquivos.

## Analytics

Google Analytics `G-437SS7TQKQ` (tag `GTM-W2X5PHGB`). Eventos enviados:
`abrir_festa`, `clique_ingresso` (com cidade e id do evento), `clique_sympla_geral`,
`clique_whatsapp`, `clique_playlist`, `clique_album`, `clique_rede`, `ver_foto`, `abrir_janela`.

> O GitHub pausa robôs agendados em repositórios sem nenhuma mudança por 60 dias.
> Se a lista parar de atualizar, é só rodar o **Run workflow** uma vez.
