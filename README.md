# 🏥 Business Intelligence para Robótica Cirúrgica – Projeto Justina

## 🎯 Objetivo

Avaliar a estratégia econômica e estratégica da adoção de um sistema de **cirurgia robótica renal (Justina)** no Brasil, utilizando dados públicos do **DATASUS** e modelagem econômica aplicada.

---

# 📊 1. Metodologia e Extração de Dados

## 🔹 Fonte de Dados

Os dados foram extraídos de bases oficiais do SUS:

- **SIH/SUS** – Sistema de Informações Hospitalares  
- **CNES** – Cadastro Nacional de Estabelecimentos de Saúde  
- **SIGTAP** – Tabela de Procedimentos, Medicamentos e OPM do SUS  

Todos os dados utilizados são **públicos e oficiais**.

---

## 🔹 Extração via Python

A extração foi realizada utilizando:

- Biblioteca **pysus**
- Download direto do **FTP do DATASUS**
- Processamento em **Python (Pandas)**

### Processo

1. Download dos **microdados SIH** (arquivos `.DBC`)
2. Conversão para **DBF**
3. Leitura via **Pandas**
4. Filtragem por **códigos de procedimentos renais (SIGTAP)**
5. Integração com **CNES** para identificar hospitais com **centro cirúrgico**

---

# 🧹 2. Tratamento e Estrutura dos Dados

Pipeline estruturado em camadas:


RAW → Dados brutos (SIH / CNES / SIGTAP)

STAGING → Dados limpos e padronizados

MART → Tabelas analíticas (fato_cirurgia_renal)


### Tratamentos realizados

- Padronização de códigos **CNES**
- Extração de **UF via UF_ZI**
- Conversão de **valores monetários**
- Remoção de inconsistências
- Cálculo de **gasto estimado**  
  *(Volume × Valor SIGTAP)*

---

# 📈 3. Análise de Mercado – TAM / SAM / SOM

## 🔹 TAM (Total Addressable Market)

Total de **cirurgias renais realizadas no SUS** no período analisado.

| Estado | Cirurgias |
|------|------|
| SP | 28.249 |
| MG | 12.931 |
| RS | 8.018 |
| RJ | 6.705 |

**Total estimado:** ~60 mil cirurgias no período analisado.

---

## 🔹 SAM (Serviceable Available Market)

Hospitais que possuem:

- Centro cirúrgico
- Realização efetiva de cirurgias renais

**Total identificado:** **333 hospitais**

### Distribuição por UF

| UF | Hospitais |
|----|----|
| SP | 113 |
| MG | 60 |
| RS | 48 |
| RJ | 44 |
| PR | 37 |

---

## 🔹 Estados Prioritários (TAM + Estrutura)

Critérios utilizados:

- Alto volume de cirurgias
- Alta concentração hospitalar
- Alto gasto total

Estados estratégicos:

- São Paulo
- Minas Gerais
- Rio Grande do Sul

---

# 🏥 4. Hospitais Prioritários

Top 5 hospitais por volume de cirurgias:

| Hospital | UF | Cirurgias | Gasto (R$ mi) |
|------|------|------|------|
| Zerbini | SP | 3.793 | 6,49 |
| Instituto do Câncer SP | SP | 2.016 | 4,47 |
| Associação Mário Penna | MG | 1.971 | 5,31 |
| Amaral Carvalho | SP | 1.800 | 3,73 |
| Fundação Pio XII | SP | 1.670 | 3,98 |

### Características desses hospitais

✔ Alto volume  
✔ Alta complexidade  
✔ Capacidade instalada  
✔ Potenciais **early adopters**

---

# 🤖 5. Estrutura para Robótica

Os hospitais prioritários possuem:

- Centro cirúrgico habilitado (**CNES**)
- Alto volume anual
- Alta complexidade
- Perfil de hospital universitário ou de referência

**Conclusão:**  
São **candidatos viáveis para adoção de cirurgia robótica**.

---

# 💰 6. Modelo Econômico

## 🔹 CAPEX (Investimento Inicial)

Estimativa baseada no mercado internacional:

- Sistema robótico: **US$ 1 milhão – 2 milhões**
- Treinamento
- Infraestrutura

---

## 🔹 OPEX (Custo Operacional Anual)

- Manutenção
- Consumíveis
- Atualizações
- Equipe técnica

---

## 🔹 Custo Total de Propriedade (TCO)


TCO = CAPEX + (OPEX × 5 anos)


Modelo aplicado em simulação com hospital de:

**1.500 cirurgias/ano**

---

# 📊 7. Simulação SOM Realista

Hipótese conservadora:

- **10% das cirurgias migram para robótica**
- Ticket médio maior por procedimento
- Redução do tempo de internação
- Ganho reputacional

### Exemplo – São Paulo

28.249 cirurgias  

10% → **2.824 cirurgias robóticas**

Com acréscimo médio de **R$ 5.000 por cirurgia**

➡ **Receita adicional:** ~ **R$ 14 milhões/ano**

---

# 📈 8. KPIs do Projeto

## Indicadores Econômicos

- TAM por UF
- SAM por UF
- SOM
- Custo médio por cirurgia
- Gasto total por hospital
- Receita incremental

---

## Indicadores Estratégicos

- Concentração **80/20**
- Classificação hospitalar
- Potencial de adoção por estado
- Payback

---

# 📊 9. Estrutura do Dashboard

Sugestão de divisão em **5 abas**:

### 1️⃣ Visão Geral
- TAM Brasil
- Total de procedimentos
- Gasto total

### 2️⃣ Análise por UF
- Mapa do Brasil
- Volume de cirurgias
- Custo médio

### 3️⃣ Ranking Hospitalar
- Top 10 hospitais
- Gasto total
- Custo médio

### 4️⃣ Simulação Econômica
- Slider de %
- Projeção de receita
- Payback

### 5️⃣ Modelo CAPEX/OPEX
- TCO
- ROI (Retorno sobre investimento)
- Cenários:  
  - Conservador  
  - Moderado  
  - Agressivo

---

# 🎯 10. Conclusão Estratégica

O mercado brasileiro apresenta:

✔ Alta concentração em poucos estados  
✔ Hospitais com capacidade estrutural  
✔ Volume suficiente para adoção  
✔ Viabilidade econômica mesmo em cenário conservador  

**Conclusão:**

O **Projeto Justina** apresenta **potencial real de implementação escalável no SUS e no setor privado**, com oportunidades estratégicas em estados com maior concentração hospitalar e volume cirúrgico.
