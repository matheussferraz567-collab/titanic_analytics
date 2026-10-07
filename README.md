# 🚢 Titanic Analytics

[![Status](https://img.shields.io/badge/status-concluído-brightgreen)](https://github.com/)
[![Power BI](https://img.shields.io/badge/Power%20BI-relatório%20interativo-F2C811?logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Excel](https://img.shields.io/badge/Excel-tratamento%20e%20análise-217346?logo=microsoftexcel&logoColor=white)](https://www.microsoft.com/microsoft-365/excel)
[![Dataset](https://img.shields.io/badge/dataset-Titanic%20%28Kaggle%29-0811A2)](https://www.kaggle.com/)

**Análise de dados aplicada ao conjunto do Titanic: da limpeza no Excel ao dashboard interativo no Power BI.**

Projeto de análise de dados desenvolvido a partir do dataset público do Titanic, disponibilizado no Kaggle, com o objetivo de investigar os padrões de sobrevivência dos passageiros considerando características como sexo, classe, faixa etária e local de embarque.

> [!NOTE]
> Todos os indicadores, tratamentos e conclusões descritos aqui podem ser reproduzidos a partir dos arquivos deste repositório.

---

## Sumário

- [Sobre o projeto](#sobre-o-projeto)
- [Perguntas da análise](#perguntas-da-análise)
- [Dataset](#dataset)
- [Metodologia](#metodologia)
- [Tratamento de dados](#tratamento-de-dados)
- [Indicadores](#indicadores)
- [Resultados](#resultados)
- [Dashboard](#dashboard)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Como executar](#como-executar)
- [Ferramentas e competências](#ferramentas-e-competências)
- [Contato](#contato)

---

## Sobre o projeto

O projeto começou pela **análise exploratória** do dataset para compreender sua estrutura e identificar problemas que poderiam comprometer a análise.

Em seguida, foi realizada a **limpeza e o tratamento dos dados**, incluindo identificação e tratamento de valores nulos e duplicados, além da correção de formatos.

Após a preparação dos dados, foi desenvolvido no Power BI um **dashboard interativo** para transformar os dados em informações de fácil interpretação.

A solução foi estruturada com KPIs, seis visualizações e filtros para segmentação dos dados, aplicando princípios de **Data Visualization** e **Storytelling com Dados**.

---

## Perguntas da análise

- Quem sobreviveu — e o que diferencia esse grupo?
- O perfil do passageiro (sexo, classe, idade e local de embarque) influencia a chance de sobrevivência?
- Quais padrões conseguem ser comunicados de forma direta a um tomador de decisão?

---

## Dataset

| Item | Descrição |
|---|---|
| **Fonte** | Kaggle — Titanic |
| **Volume** | 891 registros |
| **Campos** | 12 |
| **Base tratada** | 891 registros, 0 valores ausentes |

### Campos disponíveis

| Campo | Significado |
|---|---|
| `PassengerId` | Identificador único do passageiro |
| `Survived` | Sobrevivência (1 = sobreviveu, 0 = não sobreviveu) |
| `Pclass` | Classe do bilhete (1, 2 ou 3) |
| `Name` | Nome do passageiro |
| `Sex` | Sexo |
| `Age` | Idade |
| `SibSp` | Irmãos/cônjuge a bordo |
| `Parch` | Pais/filhos a bordo |
| `Ticket` | Número da passagem |
| `Fare` | Tarifa paga |
| `Cabin` | Cabine |
| `Embarked` | Porto de embarque (S, C ou Q) |

---

## Metodologia

| Etapa | O que foi feito |
|---|---|
| **1. Exploração** | Leitura da estrutura do dataset, checagem de tipos, contagens e distribuição dos campos. |
| **2. Limpeza** | Identificação de duplicidades, tratamento de valores nulos e correção de formatos. |
| **3. Análise** | Consolidações por sexo, classe e embarque, mediana de idade e contagens de sobrevivência. |
| **4. Visualização** | Construção do dashboard no Power BI com KPIs, visualizações e filtros. |

---

## Tratamento de dados

O arquivo de Excel guarda a base bruta e a base tratada lado a lado, permitindo comparar o antes e o depois.

### Relatório de verificação

| Verificação | Resultado |
|---|---|
| Duplicidades em `PassengerId` | Nenhuma duplicidade encontrada |
| Formato de `Fare` | Estava sendo interpretado como texto; convertido para decimal |

### Valores ausentes na base bruta

| Campo | Ausentes | Tratamento aplicado |
|---|---:|---|
| `Age` | 177 | Preenchimento pela mediana do campo (28 anos) |
| `Cabin` | 687 | Classificação como `Unknown` / não informado |
| `Embarked` | 2 | Preenchimento pela categoria mais frequente (`S`) |

> [!IMPORTANT]
> **Nota metodológica:** o preenchimento das idades pela mediana amplia a faixa de 20 a 29 anos na base tratada. Nos dados brutos, essa faixa concentra 230 passageiros; na base tratada, 407. A leitura dessa faixa deve considerar o preenchimento realizado.

---

## Indicadores

O projeto contempla os seguintes indicadores:

- Total de passageiros
- Total de sobreviventes
- Total de não sobreviventes
- Taxa de sobrevivência
- Sobrevivência por sexo
- Sobrevivência por classe
- Distribuição por faixa etária
- Local de embarque

---

## Resultados

- Dos **891** passageiros analisados, **342** sobreviveram, representando uma **taxa de sobrevivência de 38,38%**.
- **233 mulheres** e **109 homens** figuram entre os sobreviventes.
- A **1ª classe** concentrou **136 sobreviventes**, o maior número absoluto entre as classes.
- A faixa etária entre **20 e 29 anos** concentrou a maior quantidade de passageiros.
- O porto de **Southampton (S)** concentrou a maior parte dos embarques.

### Consolidação por sexo e classe

| Recorte | Sobreviventes | Não sobreviventes | Total |
|---|---:|---:|---:|
| Mulheres | 233 | 81 | 314 |
| Homens | 109 | 468 | 577 |
| 1ª classe | 136 | 80 | 216 |
| 2ª classe | 87 | 97 | 184 |
| 3ª classe | 119 | 372 | 491 |
| **Total** | **342** | **549** | **891** |

### Embarque

| Porto | Passageiros |
|---|---:|
| Southampton (S) | 646 |
| Cherbourg (C) | 168 |
| Queenstown (Q) | 77 |

---

## Dashboard

O dashboard foi estruturado com KPIs, seis visualizações e filtros para segmentação dos dados.

A leitura foi organizada do **geral para o específico**, buscando responder inicialmente **quantos sobreviveram** e, posteriormente, **quem sobreviveu e quais características estavam associadas à sobrevivência**.

| Recurso | Descrição |
|---|---|
| **KPIs** | Total de passageiros, sobreviventes, não sobreviventes e taxa de sobrevivência |
| **Visualizações** | Seis gráficos com recortes por sexo, classe, idade e embarque |
| **Filtros** | Segmentação interativa dos dados |
| **Temas** | Aplicação de princípios de Data Visualization e Storytelling |

### 🖥️ Dashboard

<!-- Adicione aqui a imagem do dashboard -->

![Dashboard Titanic](imagens/dashboard_titanic.png)

> **Power BI:** o relatório `.pbix` está disponível neste repositório.

[📂 Abrir arquivo DASHBOARD_-_TITANIC.pbix](./DASHBOARD_-_TITANIC.pbix)

---

## Estrutura do repositório

```text
.
├── README.md
│
├── DASHBOARD_-_TITANIC.pbix
│
├── PROJETO_TITANIC_-_DADOS_NO_EXCEL.xlsx
│   ├── 01_Dados_Brutos
│   ├── 02_Dados_Limpos
│   ├── 03_Analise
│   └── 04_Conclusoes
│
├── dados/
│   ├── titanic_original.csv
│   └── titanic_tratado.csv
│
└── imagens/
    └── dashboard_titanic.png
```

---

## Como executar

### 1. Excel

Abra o arquivo:

```text
PROJETO_TITANIC_-_DADOS_NO_EXCEL.xlsx
```

Percorra as abas na seguinte ordem:

```text
01_Dados_Brutos
        ↓
02_Dados_Limpos
        ↓
03_Analise
        ↓
04_Conclusoes
```

Assim é possível acompanhar todo o processo de tratamento e análise.

### 2. Power BI

Abra:

```text
DASHBOARD_-_TITANIC.pbix
```

O modelo de dados e as visualizações já estão configurados no arquivo.

Depois, utilize os filtros e gráficos para explorar os dados.

---

## Ferramentas e competências

### Ferramentas

![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

### Competências aplicadas

`Limpeza de Dados` · `Tratamento de Dados` · `Análise Exploratória` · `Excel` · `Power BI` · `KPIs` · `Data Visualization` · `Storytelling com Dados` · `Dashboard`

---

## Contato

**Matheus Ferraz**

**Analista de Dados Júnior | Analista de BI**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/matheusferrazportela)

📧 **E-mail:** matheusferraz0@outlook.com

🌐 **Portfólio:** em breve

---

⭐ Se este projeto foi útil ou interessante, considere deixar uma estrela no repositório.
