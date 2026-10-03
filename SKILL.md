---
name: orientacao-analise-sm
description: Conduz a análise de métricas de Instagram de um cliente cruzando os números com a macro estratégia e o objetivo do período, e entrega o resultado no dashboard "Orientação Análise SM". Use SEMPRE que pedirem para analisar métricas, fechar o mês, fechar o ciclo, montar relatório de Instagram, comparar períodos (15, 30, 60 ou 90 dias), entender por que um conteúdo performou ou não, decidir o que replicar no próximo período, ou quando enviarem prints do Insights / Meta Business Suite ou números soltos de um perfil, mesmo que não usem a palavra "análise".
---

# Orientação Análise SM

Análise de métricas de Instagram que parte da estratégia, não do número. O número só diz algo quando comparado com o que se queria alcançar e com os períodos anteriores.

O resultado vive em um aplicativo já publicado:
**https://claude.ai/artifact/SQfKeDAT3N21YLp5EJ3ni9**

O aplicativo guarda clientes e análises, calcula os indicadores, monta as tabelas e listas e mostra a leitura dos números. O papel desta skill é coletar o que falta, registrar no aplicativo e escrever a análise.

## 1. Pergunte antes de analisar

Sem estas respostas a análise vira opinião solta. Pergunte o que ainda não foi dito, de uma vez só:

1. Qual cliente / perfil.
2. Qual era a macro estratégia (do trimestre; se não houver, do mês; se não houver, o objetivo principal).
3. Qual era o objetivo do período analisado.
4. Qual período: últimos 15, 30, 60 ou 90 dias, com datas de início e fim.
5. Houve tráfego pago?
6. Havia meta numérica (novos seguidores, leads)?

Não invente estratégia nem objetivo. Se a pessoa não souber responder, registre "não informado" e diga que a leitura fica limitada aos números.

## 2. Receba os números

Chegam de duas formas: prints do Insights ou digitados. Dos prints, extraia só o que está visível; não estime nem complete lacunas. Liste o que ficou faltando e pergunte se a pessoa tem.

Campos (as chaves são as do aplicativo; veja `references/dados.md` para o formato completo):

- **Seguidores**: total no fim do período, novos, perdas.
- **Alcance e impressões**: alcance total, orgânico, pago, % de não seguidores, impressões, posts publicados.
- **Engajamento**: interações totais, curtidas, comentários, salvamentos, compartilhamentos.
- **Perfil**: visitas, cliques no link.
- **Reels**: quantidade, visualizações, % que passou dos 3 s, retenção média, interações, contas alcançadas, novos seguidores.
- **Feed**: quantidade, visualizações, interações, contas alcançadas, salvamentos, novos seguidores.
- **Períodos anteriores** (até 3): seguidores, alcance, visualizações, interações, cliques. Siga o modelo por quarter: os números lado a lado numa única tabela, nunca isolados.
- **Conteúdos**: título, formato, assunto/tema, CTA usado, visualizações, alcance, interações, salvamentos, compartilhamentos, comentários, novos seguidores e leads (só se der para rastrear de qual conteúdo vieram).

## 3. Registre no aplicativo

Com a ferramenta `ArtifactData` (carregue por ToolSearch se estiver adiada), grave na URL acima:

- coleção `clientes`: liste primeiro; reutilize o cliente se já existir, senão crie `{nome, criadoEm}`.
- coleção `analises`: um documento por período, no formato de `references/dados.md`.

Liste as análises anteriores do mesmo cliente. Se existirem, use os números delas para preencher `anteriores` em vez de perguntar de novo.

Se `ArtifactData` não estiver disponível, entregue os números organizados na ordem dos campos e oriente a pessoa a abrir o aplicativo, clicar em "Nova análise" e preencher (ou enviar os prints por lá).

## 4. Conduza a análise

Quatro passos, nesta ordem:

1. **Números gerais do período**, lado a lado com os anteriores.
2. **Melhores conteúdos**: quais deram mais interações, mais visualizações, mais seguidores novos e, se rastreável, mais leads. Conteúdo que aparece em mais de uma lista já é um sinal.
3. **Cruzar dados com visão analítica**: resultado positivo ou negativo quase sempre tem causa. Separe o que está dentro e fora do controle.
4. **Fechar o ciclo**: o que funcionou, o que não funcionou, ações do próximo período.

Três linhas de raciocínio para decidir mudanças:

- **Formato vs. formato**, mesma métrica, por médias e nunca por totais. Média maior em carrossel não significa abandonar reels; significa testar aumentar a proporção e observar se se sustenta.
- **Este período vs. o anterior**. Métrica caindo dois períodos seguidos é padrão. Queda isolada pode ser ruído. Não proponha mudança de rota por causa de um mês; procure o que se repete.
- **Interação vs. seguidores vs. visualização**. O mesmo conteúdo nas três listas é sinal forte para replicar. Listas completamente diferentes também informam: alcance e conversão podem estar desconectados. Nem tudo que dá alcance dá lead; conteúdo de qualificação, específico, com CTA direto ou de produto engaja menos e é crucial.

Padrões em comum a observar nos conteúdos: formato, assunto/tema, estilo visual (detalhe, não fator decisivo) e captação de leads (CTA mais forte, mais cliques ou contatos). Servem de norte; não determinam tudo.

Como ler cada métrica: `references/metricas.md`. Leia antes de escrever a análise.

## 5. O que não lhe cabe

A análise fala do que os dados e a estratégia informada sustentam. Fica de fora:

- julgar a estratégia, o negócio, o produto, o preço ou o posicionamento;
- opinar sobre design, roteiro ou qualidade de um conteúdo que você não viu;
- citar benchmark de mercado ou "taxa ideal" que a pessoa não forneceu;
- afirmar causa. Toda explicação de causa é **hipótese** e vem marcada assim.

Quando faltar dado para concluir, diga o que falta. Isso é mais útil do que uma conclusão frágil, porque a decisão do próximo período vai se apoiar nesta análise.

## 6. Entregue

Grave a análise escrita no campo `analiseIA` do documento e mande o link do aplicativo. Texto simples, sem markdown, com estes títulos em maiúsculas:

```
LEITURA FRENTE À ESTRATÉGIA
O QUE FUNCIONOU
PONTOS DE MELHORIA
AÇÕES PARA O PRÓXIMO PERÍODO
O QUE OS DADOS NÃO RESPONDEM
```

- **O que funcionou**: conteúdos e ações com resultado acima da média, com a hipótese do porquê.
- **Pontos de melhoria**: o que ficou abaixo do esperado nos números e frente ao objetivo. Meta de leads ou de crescimento não batida entra aqui e precisa levar a uma ação.
- **Ações para o próximo período**: decisões concretas e práticas (proporção de formato, tema a repetir, CTA a trocar, ponto do funil a ajustar). Elas se unem ao planejamento geral do negócio, então proponha e deixe a decisão com quem conhece o negócio.

No chat, resuma em poucas linhas: o que se destacou, o principal ponto de melhoria e o link. Os campos "Fechamento do ciclo" do aplicativo são de quem analisa; não preencha por ela.
