<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1F9BD4,50:2E75B6,100:16265F&height=200&section=header&text=Dashboard%20de%20Vendas%20Excel&fontSize=44&fontColor=ffffff&fontAlignY=38&desc=Análise%20Completa%20de%20Planos%20e%20Jogadores%20em%20Excel&descAlignY=58&descSize=18" width="100%"/>

[![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)](https://microsoft.com/excel)
[![Data Analysis](https://img.shields.io/badge/Análise%20de%20Dados-Dashboard-blue?style=for-the-badge)](https://github.com/fassir)
[![KPIs](https://img.shields.io/badge/KPIs-Indicadores-orange?style=for-the-badge)](https://github.com/fassir)

[![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)](https://microsoft.com/excel)
[![Charts](https://img.shields.io/badge/Gráficos-Dashboard-1565C0?style=flat-square)](https://github.com/fassir)
[![KPIs](https://img.shields.io/badge/KPIs-FF6F00?style=flat-square)](https://github.com/fassir)
[![Pivot](https://img.shields.io/badge/Tabela%20Dinâmica-4CAF50?style=flat-square)](https://github.com/fassir)

</div>

---

## 🎯 Sobre o Projeto

Dashboard de **análise de vendas de planos e assinaturas** desenvolvido inteiramente no **Microsoft Excel**, organizado em 4 abas funcionais com separação clara entre dados brutos, cálculos auxiliares e visualização final. O arquivo `Arquivo_final.xlsx` responde perguntas-chave sobre receita por tipo de plano, perfil dos jogadores e performance por categoria.

---

## 🗂️ Estrutura do Arquivo

```
Arquivo_final.xlsx
├── 📋 Assets        → Paleta de cores, ícones e imagens da marca
├── 📊 Bases         → Dados brutos de vendas e cadastros
├── 🔢 Cálculos      → KPIs, fórmulas auxiliares e tabelas dinâmicas
└── 📈 Dashboard     → Página final com gráficos e indicadores
```

---

## 💡 Tecnologias

<div align="center">

[![My Skills](https://skillicons.dev/icons?i=windows&theme=dark)](https://microsoft.com/excel)

</div>

| Tecnologia | Uso |
|------------|-----|
| Microsoft Excel | Plataforma completa do dashboard |
| Tabelas Dinâmicas | Agregações por tipo de plano e gênero |
| Gráficos Excel | Visualizações no Dashboard final |
| Fórmulas (SOMASE, CONT.SE, PROCV) | KPIs e cálculos auxiliares |
| Formatação Condicional | Destaque visual de métricas críticas |
| Validação de Dados | Integridade nos dados de entrada |

---

## 📋 Descrição das Abas

<details>
<summary><strong>🎨 Aba Assets — Identidade Visual</strong></summary>

```
Conteúdo:
  ├── Paleta de cores oficial do dashboard
  │     Primary:   #1F9BD4 (azul)
  │     Secondary: #2E75B6 (azul escuro)
  │     Accent:    #F2C811 (amarelo)
  │     Neutral:   #F5F5F5 (cinza claro)
  ├── Ícones dos tipos de plano
  ├── Logos e imagens de suporte visual
  └── Referência de tipografia (Calibri, tamanhos)
```

</details>

<details>
<summary><strong>📊 Aba Bases — Dados Brutos</strong></summary>

```
Estrutura da tabela de vendas:
  ID_Venda | Data | Tipo_Plano | Genero_Jogador | Valor | Status

Tipos de plano presentes:
  • Plano Anual
  • Auto-Renovação
  • EA Play
  • Minecraft Season Pass

Campos de jogador:
  • Gênero (Masculino / Feminino / Não informado)
  • Categoria de assinatura
  • Data de aquisição
```

</details>

<details>
<summary><strong>🔢 Aba Cálculos — KPIs e Auxiliares</strong></summary>

```
KPIs calculados:
  ┌──────────────────────────────────────────────────┐
  │  Total de Vendas — Plano Anual                   │
  │  Total de Vendas — Auto-Renovação                │
  │  Total de Vendas — EA Play                       │
  │  Total de Vendas — Minecraft Season Pass         │
  │  Quantidade de Jogadores por Gênero              │
  │  Total por Tipo de Plano (todos)                 │
  └──────────────────────────────────────────────────┘

Fórmulas principais:
  =SOMASE(Bases[Tipo_Plano];"Plano Anual";Bases[Valor])
  =CONT.SE(Bases[Genero_Jogador];"Masculino")
  =SOMASES(Bases[Valor];Bases[Status];"Ativo";
           Bases[Tipo_Plano];A2)
```

</details>

---

## 📈 Aba Dashboard — Visualização Final

<div align="center">

```
┌──────────────────────────────────────────────────────────────────┐
│  🏆 DASHBOARD DE VENDAS — PLANOS E ASSINATURAS                  │
├────────────────────────────────────────────────────────────────── ┤
│  💰 Total Anual  │ 🔄 Auto-Renovação │ 🎮 EA Play │ ⛏️ Minecraft │
│  [KPI Card]      │  [KPI Card]        │ [KPI Card] │  [KPI Card]  │
├──────────────────────────────────────────────────────────────────┤
│  📊 Receita por Tipo de Plano    │  👥 Jogadores por Gênero       │
│  [Barras horizontais ordenadas]  │  [Pizza — M/F/Não informado]   │
├──────────────────────────────────────────────────────────────────┤
│  📅 Evolução Mensal de Vendas    │  🏅 Ranking por Plano          │
│  [Gráfico de Linha]              │  [Tabela formatada]            │
└──────────────────────────────────────────────────────────────────┘
```

</div>

---

## ❓ Perguntas Respondidas pelo Dashboard

| Pergunta | Onde encontrar |
|----------|---------------|
| Qual o total de vendas do Plano Anual? | KPI Card — Plano Anual |
| Qual o total de Auto-Renovação? | KPI Card — Auto-Renovação |
| Qual o total de EA Play? | KPI Card — EA Play |
| Qual o total do Minecraft Season Pass? | KPI Card — Minecraft |
| Quantos jogadores por gênero? | Gráfico Pizza — Gênero |
| Qual o total por tipo de plano? | Barras horizontais |

---

## 🔧 Boas Práticas Aplicadas

```
✅ Separação de responsabilidades (Assets / Bases / Cálculos / Dashboard)
✅ Sem fórmulas hardcoded no Dashboard — todas referenciadas de Cálculos
✅ Tabela estruturada (Ctrl+T) na aba Bases para expansão automática
✅ Nomes definidos para ranges críticos
✅ Proteção de planilha nas abas Cálculos e Dashboard
✅ Formatação condicional nos KPIs (verde = acima da meta)
✅ Gráficos vinculados a ranges nomeados (não a células fixas)
✅ Paleta de cores consistente via aba Assets
```

---

## 🚀 Como Usar

1. **Baixe** `Arquivo_final.xlsx`
2. **Abra** no Microsoft Excel (versão 2016 ou superior recomendada)
3. **Navegue** pelas abas na ordem: Assets → Bases → Cálculos → Dashboard
4. Para **atualizar os dados**: edite a aba Bases; Dashboard atualiza automaticamente
5. Para **adicionar novos tipos de plano**: atualize as listas de validação na aba Bases

```
⚠️ Requisito mínimo: Microsoft Excel 2016
   LibreOffice Calc pode apresentar incompatibilidades com formatação
```

---

## 👤 Autor

<div align="center">

**Fabio Piassi**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/fabio-piassi)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/fassir)

</div>

---

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:16265F,50:2E75B6,100:1F9BD4&height=120&section=footer" width="100%"/>
