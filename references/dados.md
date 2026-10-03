# Formato dos dados no aplicativo

Aplicativo: https://claude.ai/artifact/SQfKeDAT3N21YLp5EJ3ni9
O código-fonte da página está em `assets/app.html`. Para alterar o aplicativo, edite esse arquivo e publique de novo passando a URL acima em `url`.

## Coleção `clientes`

```json
{ "nome": "@perfil ou nome", "criadoEm": "2026-10-03T12:00:00.000Z" }
```

O id do documento é livre (ex.: `c-nome-do-cliente`).

## Coleção `analises`

Um documento por cliente e período. Omita campos sem dado; não grave zero no lugar de "não sei".

```json
{
  "clienteId": "id do documento do cliente",
  "periodoDias": 30,
  "inicio": "2026-09-01",
  "fim": "2026-09-30",
  "trafego": true,
  "estrategia": "macro estratégia informada",
  "objetivo": "objetivo do período informado",
  "n": {
    "seg_total": 0, "seg_novos": 0, "seg_perdas": 0,
    "alc_total": 0, "alc_org": 0, "alc_pago": 0, "alc_naoseg": 0, "impressoes": 0, "posts": 0,
    "interacoes": 0, "curtidas": 0, "comentarios": 0, "salvamentos": 0, "compart": 0,
    "visitas": 0, "cliques": 0,
    "reels_qtd": 0, "reels_views": 0, "reels_3s": 0, "reels_ret": 0, "reels_inter": 0, "reels_alc": 0, "reels_seg": 0,
    "feed_qtd": 0, "feed_views": 0, "feed_inter": 0, "feed_alc": 0, "feed_salv": 0, "feed_seg": 0,
    "meta_seg": 0, "meta_leads": 0, "leads_total": 0
  },
  "anteriores": [
    { "rotulo": "Junho", "seg": 0, "alc": 0, "views": 0, "inter": 0, "cliques": 0 },
    { "rotulo": "Julho", "seg": 0, "alc": 0, "views": 0, "inter": 0, "cliques": 0 },
    { "rotulo": "Agosto", "seg": 0, "alc": 0, "views": 0, "inter": 0, "cliques": 0 }
  ],
  "conteudos": [
    { "titulo": "", "formato": "Reels", "tema": "", "cta": "Salvar",
      "views": 0, "alcance": 0, "interacoes": 0, "salvamentos": 0, "compart": 0, "comentarios": 0, "novosSeg": 0, "leads": 0 }
  ],
  "fechamento": { "funcionou": "", "melhoria": "", "acoes": "" },
  "analiseIA": "",
  "atualizadoEm": "2026-10-03T12:00:00.000Z"
}
```

Regras:

- `periodoDias`: 15, 30, 60 ou 90.
- `anteriores`: sempre 3 posições, do mais antigo para o mais recente; use `{}` para posição vazia.
- `formato`: `Reels`, `Carrossel`, `Imagem única` ou `Story`.
- `cta`: `Salvar`, `Compartilhar`, `Comentar`, `Seguir`, `Link / direct` ou `Sem CTA`.
- `alc_naoseg`, `reels_3s`, `reels_ret`: porcentagens em número (46 = 46%).
- `fechamento`: escrito por quem analisa. Não sobrescreva; em atualizações use `update`, não `set`.
- `analiseIA`: texto simples com os cinco títulos em maiúsculas definidos no SKILL.md.
