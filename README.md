



<img width="801" height="531" alt="image" src="https://github.com/user-attachments/assets/5680d76d-4362-4d4b-96bf-a92de9765721" />





# 🏥 Business Intelligence para Robótica Cirúrgica – Projeto Justina

## 🎯 Objetivo

Avaliar a estratégia econômica e estratégica da adoção de um sistema de **cirurgia robótica renal (Justina)** no Brasil, utilizando dados públicos do **DATASUS** e modelagem econômica aplicada.

---

# 📊 Metodologia e Extração de Dados

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

# 🧹  Tratamento e Estrutura dos Dados

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

# 📈 Análise de Mercado – TAM / SAM / SOM

## 🔹 TAM (Total Addressable Market)





Quantidade Total de **cirurgias renais realizadas no SUS** no período de 2022 a 2024 nos estados:

| Estado | Cirurgias |
|------|------|
| SP | 28.249 |
| MG | 12.931 |
| RS | 8.018 |
| RJ | 6.705 |

**Total estimado:** ~60 mil cirurgias no período analisado.



### <img width="1135" height="908" alt="cirurgias_tam_por_uf" src="https://github.com/user-attachments/assets/aed4152f-a81c-422e-aa01-2fadb84281d8" />





<img width="1148" height="908" alt="gasto_tam_por_uf" src="https://github.com/user-attachments/assets/48679430-724b-4d10-916a-238abdc570be" />





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





<img width="1191" height="872" alt="centro_cirurgico_vs_renal" src="https://github.com/user-attachments/assets/f72b1092-1be1-492d-8d7e-6ad30ee42666" />






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

# 🏥 Hospitais Prioritários

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

# 🤖  Estrutura para Robótica

Os hospitais prioritários possuem:

- Centro cirúrgico habilitado (**CNES**)
- Alto volume anual
- Alta complexidade
- Perfil de hospital universitário ou de referência

## 🔹 SOM - Estimativa de hospitais para serem conquistada







<img width="1163" height="870" alt="distribuicao_custo_hospital" src="https://github.com/user-attachments/assets/f711e276-8571-41b4-a3f3-6b35f308624b" />






<img width="1162" height="909" alt="volume_vs_custo_uf" src="https://github.com/user-attachments/assets/9f998750-a463-4e19-869a-dcbf6cab4c4b" />






**Conclusão:**  
São **candidatos viáveis para adoção de cirurgia robótica**.


---

# 💰  Modelo Econômico

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

# 📊  Simulação SOM Realista

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

# 📈  KPIs do Projeto

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

# 📊  Dashboard












### Ranking Hospitalar




<img width="1982" height="1177" alt="top10_hospitais_cirurgias_renais" src="https://github.com/user-attachments/assets/0cc4a28f-9b4a-4d8c-98e6-46e9aa22d7bb" />





<img width="2013" height="1177" alt="top10_hospitais_gasto_renais" src="https://github.com/user-attachments/assets/52dfe203-7dc6-4bce-bcee-a33393777aa7" />





### Simulação Econômica





<img width="1172" height="939" alt="pizza_cirurgias_tam_top8_outros" src="https://github.com/user-attachments/assets/a51d5ce8-7498-4db0-b4dd-fc3fcb209ea7" />





<img width="1260" height="938" alt="scatter_cirurgias_vs_gasto_tam" src="https://github.com/user-attachments/assets/a3ac4efb-e9cd-4859-8edc-b4e3362e479d" />





### CAPEX/OPEX

- TCO
- ROI (Retorno sobre investimento)
- Cenários:  
  - Conservador  
  - Moderado  
  - Agressivo

---

# 🎯 Conclusão Estratégica

O mercado brasileiro apresenta:

✔ Alta concentração em poucos estados  
✔ Hospitais com capacidade estrutural  
✔ Volume suficiente para adoção  
✔ Viabilidade econômica mesmo em cenário conservador  


**Conclusão:**

O **Projeto Justina** apresenta **potencial real de implementação escalável no SUS e no setor privado**, com oportunidades estratégicas em estados com maior concentração hospitalar e volume cirúrgico.
