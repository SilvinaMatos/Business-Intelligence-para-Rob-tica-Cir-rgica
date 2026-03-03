🏥 Business Intelligence para Robótica Cirúrgica – Projeto Justina 🎯 Objetivo

Avaliar a viabilidade econômica e estratégica da adoção de um sistema de cirurgia robótica renal (Justina) no Brasil, utilizando dados públicos do DATASUS e modelagem econômica aplicada.

📊 1. Metodologia e Extração de Dados 🔹 Fonte de Dados

Os dados foram extraídos da base oficial do:

SIH/SUS (Sistema de Informações Hospitalares)

CNES (Cadastro Nacional de Estabelecimentos de Saúde)

SIGTAP (Tabela de Procedimentos, Medicamentos e OPM do SUS)

Todos os dados são públicos e oficiais.

🔹 Extração via Python

A extração foi realizada utilizando:

Biblioteca pysus

Download direto do FTP do DATASUS

Processamento em Python (Pandas)

Processo:

Download dos microdados SIH (arquivos DBC)

Conversão para DBF

Leitura via Pandas

Filtragem por códigos de procedimentos renais (SIGTAP)

Integração com CNES para identificar hospitais com centro cirúrgico 🧹 2. Tratamento e Estruturação dos Dados

Pipeline estruturada em camadas:

RAW → Dados brutos SIH / CNES / SIGTAP STAGING → Dados limpos e padronizados MART → Tabelas analíticas (fato_cirurgia_renal) Tratamentos realizados:

Padronização de códigos CNES

Extração de UF via UF_ZI

Conversão de valores monetários

Remoção de inconsistências

Cálculo de gasto estimado (Volume × Valor SIGTAP)

📈 3. Análise de Mercado – TAM / SAM / SOM 🔹 TAM (Total Addressable Market)

Total de cirurgias renais realizadas no SUS no período analisado.

Exemplo:

SP: 28.249 cirurgias

MG: 12.931 cirurgias

RS: 8.018 cirurgias

RJ: 6.705 cirurgias

Total estimado (exemplo): ~ 60 mil cirurgias no período analisado.

🔹 SAM (Serviceable Addressable Market)

Hospitais com:

Centro cirúrgico

Realização efetiva de cirurgias renais

Total identificado: 333 hospitais

Distribuição por UF:

UF Hospitais SP 113 MG 60 RS 48 RJ 44 PR 37 🔹 Estados Prioritários (TAM + Estrutura)

Critérios:

Alto volume

Alta concentração hospitalar

Alto gasto total

Estados estratégicos:

São Paulo

Minas Gerais

Rio Grande do Sul

🏥 4. Hospitais Prioritários

Top 5 por volume:

Hospital UF Cirurgias Gasto (R$ mi) Zerbini SP 3.793 6.49 Instituto do Câncer SP SP 2.016 4.47 Associação Mário Penna MG 1.971 5.31 Amaral Carvalho SP 1.800 3.73 Fundação Pio XII SP 1.670 3.98

Esses hospitais:

✔ Alto volume ✔ Alta complexidade ✔ Capacidade instalada ✔ Potenciais early adopters

🤖 5. Estrutura para Robótica

Hospitais prioritários possuem:

Centro cirúrgico habilitado (CNES)

Alto volume anual

Complexidade elevada

Perfil de hospital universitário ou referência

Conclusão: São candidatos viáveis para adoção de robótica.

💰 6. Modelo Econômico 🔹 CAPEX (Investimento Inicial)

Estimativa baseada em mercado internacional:

Sistema robótico: US$ 1M – 2M

Treinamento

Infraestrutura

🔹 OPEX (Custo Operacional Anual)

Manutenção

Consumíveis

Atualizações

Equipe técnica

🔹 TCO (Total Cost of Ownership)

TCO = CAPEX + (OPEX × 5 anos)

Modelo aplicado:

Simulação com hospital de 1.500 cirurgias/ano. 📊 7. Simulação SOM Realista

Hipótese conservadora:

10% das cirurgias migram para robótica

Ticket médio maior por procedimento

Redução de tempo de internação

Ganho reputacional

Exemplo:

SP: 28.249 cirurgias 10% = 2.824 cirurgias robóticas

Com acréscimo médio de R$ 5.000 por cirurgia:

→ Receita adicional: ~ R$ 14 milhões/ano

📈 8. KPIs do Projeto Indicadores Econômicos

TAM por UF

SAM por UF

SOM estimado

Custo médio por cirurgia

Gasto total por hospital

Receita incremental projetada

Indicadores Estratégicos

Concentração 80/20

Ranking hospitalar

Potencial de adoção por estado

Payback estimado

📊 9. Estrutura do Dashboard

Recomendo dividir em 5 abas:

1️⃣ Visão Geral

TAM Brasil

Total hospitais

Gasto total

2️⃣ Análise por UF

Mapa do Brasil

Volume

Custo médio

3️⃣ Ranking Hospitalar

Top 10 hospitais

Gasto

Custo médio

4️⃣ Simulação Econômica

Slider % adoção

Projeção receita

Payback

5️⃣ Modelo CAPEX/OPEX

TCO

ROI estimado

Cenários (conservador / moderado / agressivo)

🎯 10. Conclusão Estratégica

O mercado brasileiro apresenta:

✔ Alta concentração em poucos estados ✔ Hospitais com capacidade estrutural ✔ Volume suficiente para justificar adoção ✔ Viabilidade econômica em cenário conservador

O projeto Justina apresenta potencial real de implementação escalável no SUS e setor privado.
