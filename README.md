# orientacao-analise-sm

Skill do Claude para analisar métricas de Instagram a partir da macro estratégia e do objetivo do período, com o dashboard "Orientação Análise SM".

## O que tem aqui

- `SKILL.md`: o roteiro da análise (perguntas de contexto, coleta dos números, raciocínio e formato da entrega).
- `references/metricas.md`: como ler cada métrica.
- `references/dados.md`: formato dos dados que o aplicativo guarda.
- `assets/app.html`: código do aplicativo (dashboard, formulário e glossário).

## Como instalar a skill

Compacte esta pasta em um `.zip`, renomeie para `orientacao-analise-sm.skill` e adicione em Configurações > Skills no Claude. No Claude Code, copie a pasta para `~/.claude/skills/orientacao-analise-sm`.

## Sobre o aplicativo

O aplicativo é publicado como artifact no Claude e é privado da conta que o publicou. Para ter o seu, peça ao Claude para publicar `assets/app.html` como artifact e troque o link em `SKILL.md` e `references/dados.md`.

Aberto fora do Claude, o arquivo salva os dados só no navegador, e a leitura de prints e a análise escrita ficam indisponíveis.
