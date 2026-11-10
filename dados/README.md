# Bases de dados do módulo DS-PY-018

Todas as bases ficam nesta pasta e são lidas pelos notebooks com `pd.read_csv("../dados/<arquivo>.csv")`.
Nenhuma depende de internet.

## Bases públicas (reais)

| Arquivo | Linhas × colunas | Origem | Usada em |
|---|---|---|---|
| `titanic.csv` | 891 × 15 | seaborn-data | Aula 1 (exercícios), Aula 5 (exercícios) |
| `taxis.csv` | 6433 × 14 | seaborn-data (NYC, mar/2019) | Aula 3 (exercícios) |
| `penguins.csv` | 344 × 7 | seaborn-data (Palmer Penguins) | Aula 5 (ao vivo) |
| `anscombe.csv` | 44 × 3 | seaborn-data (quarteto de Anscombe) | Aula 5 (ao vivo) |
| `winequality-red.csv` | 1599 × 12 | UCI Wine Quality (vinho tinto) | Aula 6 (ao vivo) |
| `winequality-white.csv` | 4898 × 12 | UCI Wine Quality (vinho branco) | Aula 6 (exercícios) |
| `cancer_mama.csv` | 569 × 11 | Breast Cancer Wisconsin (scikit-learn), 10 variáveis "média" traduzidas | Aula 5 (exercícios) |
| `vagas_ds.csv` | 637 × 13 | Salários de dados (ai-jobs.net, 2020–2022) **com sujeira inserida de propósito** | Aula 4 (ao vivo) |

## Bases geradas para o curso

Criadas com sementes fixas para que os resultados dos gabaritos sejam sempre os mesmos. Cada uma tem padrões
("histórias") que o material leva o aluno a descobrir.

| Arquivo | Linhas × colunas | Conteúdo | Usada em |
|---|---|---|---|
| `pedidos_loja.csv` | 4230 × 15 | Pedidos de um e-commerce multicanal, 2023–2024 | Aulas 1, 2 e 3 (ao vivo), Aula 5 (exercícios) |
| `vendas_campanha.csv` | 910 × 7 | Vendas diárias de 5 lojas, jan–jun/2024, campanha em abril | Aula 2 (ao vivo) |
| `vendas_pandemia.csv` | 480 × 7 | Faturamento mensal 2018–2022 por canal e categoria | Aula 2 (exercícios) |
| `notas_escola.csv` | 6864 × 9 | Notas por aluno, disciplina e bimestre em 3 escolas | Aula 2 (exercícios) |
| `casas.csv` | 555 × 8 | Preços de casas por bairro, com mansões e erros de digitação | Aula 4 (ao vivo) |
| `clientes_academia.csv` | 900 × 10 | Cadastro de academia com texto sujo, idades inválidas e colunas constantes | Aula 4 (exercícios) |
| `alugueis.csv` | 1492 × 8 | Aluguéis em 4 cidades com muitos outliers (erros + imóveis de luxo) | Aula 4 (exercícios) |
| `delivery_pedidos.csv` | 8058 × 18 | Pedidos de um app de delivery em 2024 — **base do projeto final** | Projeto final |

## Dicionário resumido

**pedidos_loja.csv** — `pedido_id`, `data` (AAAA-MM-DD), `cliente_id`, `cidade`, `uf`, `canal` (Site, App, Loja física),
`categoria`, `produto`, `preco_unitario`, `quantidade`, `desconto` (fração 0–0,3), `valor_total` (= preço × qtd × (1 − desconto)),
`frete`, `prazo_entrega_dias`, `avaliacao` (1–5, com faltantes).

**vendas_campanha.csv** — `data`, `loja`, `regiao`, `periodo` (antes / durante / depois da campanha de abril),
`num_clientes`, `ticket_medio`, `vendas`.

**vendas_pandemia.csv** — `mes_referencia`, `ano`, `mes`, `canal` (Loja física, E-commerce), `categoria`, `pedidos`, `faturamento`.

**notas_escola.csv** — `aluno_id`, `escola`, `serie`, `turma`, `sexo`, `disciplina`, `bimestre` (1–4), `nota` (0–10), `faltas`.

**vagas_ds.csv** — `fonte` (constante), `ano`, `nivel` (códigos e nomes misturados), `contrato`, `cargo`, `salario`, `moeda`,
`salario_usd` (texto em vários formatos), `pais_residencia`, `remoto_pct` (texto), `pais_empresa`, `porte_empresa`, `vaga_ativa` (constante).

**casas.csv** — `casa_id`, `bairro`, `area_m2`, `quartos`, `banheiros`, `vagas`, `idade_anos`, `preco`.

**clientes_academia.csv** — `cliente_id`, `idade` (texto), `sexo`, `unidade`, `plano`, `mensalidade` (texto em reais),
`data_adesao` (dd/mm/aaaa), `frequencia_mensal`, `pais` (constante), `status` (constante).

**alugueis.csv** — `imovel_id`, `cidade`, `tipo`, `area_m2`, `quartos`, `aluguel`, `condominio`, `iptu`.

**cancer_mama.csv** — `raio`, `textura`, `perimetro`, `area`, `suavidade`, `compacidade`, `concavidade`, `pontos_concavos`,
`simetria`, `dimensao_fractal`, `diagnostico` (maligno / benigno).

**delivery_pedidos.csv** — `pedido_id`, `data_hora`, `cidade` (com variações de escrita), `bairro`, `restaurante_id`,
`tipo_cozinha`, `plataforma`, `forma_pagamento` (com variações), `cupom` (Sim/Não), `cliente_novo`, `chuva`, `distancia_km`,
`tempo_entrega_min` (com códigos inválidos), `valor_pedido` (texto), `taxa_entrega`, `avaliacao`, `pais` (constante), `moeda` (constante).
