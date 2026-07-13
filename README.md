# 📊 Dashboard Financeiro - Inteligência de Tempo com DAX

Este repositório contém um painel executivo desenvolvido no **Power BI** focado em análise financeira comparativa ano a ano ($YoY$). O objetivo principal foi transformar dados brutos de uma DRE em um layout limpo, intuitivo e focado na tomada de decisão.

---

## 🚀 O Projeto

O painel foi estruturado para permitir que gestores comparem instantaneamente o desempenho do ano atual com o mesmo período do ano anterior, identificando tendências de crescimento ou pontos de atenção.

![Demonstração do Dashboard](./painel.png)

---

## 🛠️ Recursos Técnicos & Fórmulas DAX

Para a construção das métricas e da inteligência de tempo, foram criadas medidas personalizadas utilizando a linguagem **DAX**, garantindo a performance e a automação do relatório:

### 1. Valor Total
Soma simples do faturamento/valor da base de dados.
```dax
Valor Total = SUM(Planilha1[Valor])
Ano Anterior = CALCULATE([Valor Total], SAMEPERIODLASTYEAR(dCalendario[Date]))
Variação Ano Anterior % = 
DIVIDE(
    [Valor Total] - [Ano Anterior], 
    [Ano Anterior], 
    0
)
