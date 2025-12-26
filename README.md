# 🔌 Previsão Horária do Preço de Energia Elétrica com Prophet

## 📌 Visão Geral
Este projeto tem como objetivo **prever o preço horário da energia elétrica** utilizando o modelo **Facebook Prophet**, incorporando **regressores externos** para capturar a complexidade do mercado energético, que é fortemente influenciado por demanda, geração e condições climáticas.

O foco do projeto é apoiar **decisões estratégicas e operacionais** no setor de energia, como planejamento, compra e venda no mercado.

---

## 🎯 Problema de Negócio
O preço da energia elétrica apresenta **alta volatilidade**, influenciada por múltiplos fatores externos. Previsões imprecisas podem gerar impactos financeiros relevantes, especialmente em operações de grande volume.

Este projeto busca responder à seguinte pergunta:

> É possível melhorar a previsão do preço horário da energia ao incorporar variáveis externas como demanda, geração e clima?

---

## 👥 Stakeholders
- Traders e analistas do mercado de energia  
- Planejamento estratégico e operacional  
- Gestores de risco  
- Operadores do sistema elétrico  

---

## 🧠 Abordagem Utilizada
Foi utilizado o modelo **Facebook Prophet**, escolhido por:
- Boa interpretabilidade  
- Capacidade de lidar com sazonalidades  
- Facilidade de integração de **regressores externos**

Para evitar overfitting em períodos de alta volatilidade, o parâmetro de tendência foi ajustado:

- **changepoint_prior_scale = 0.01**

---

## 🛠️ Variáveis de Entrada (Regressores Externos)
O modelo incorpora **14 regressores**, incluindo:

### 🔹 Demanda
- Total load forecast  
- Picos observados de até **30.619 MW**

### 🔹 Geração
- Fontes fósseis  
- Fontes renováveis (eólica, solar, entre outras)

### 🔹 Clima
- Temperatura  
- Condições meteorológicas  

Esses fatores podem impactar o preço final em até **±11 €**, dependendo da carga e da composição do sistema.

---

## 📊 Avaliação do Modelo
O modelo apresentou **alta aderência aos dados reais**, mantendo estabilidade mesmo em períodos de maior volatilidade.

### Métricas utilizadas
- **RMSE:** 3.96  
- **MAPE:** ~5.3%

O uso do MAPE permite avaliar o erro relativo, o que é especialmente relevante em séries temporais de preços.

---

## 📈 Resultados
- Captura consistente de tendências e sazonalidades do preço horário  
- A inclusão de regressores externos aumentou a estabilidade das previsões  
- Resultados indicam potencial de uso como ferramenta de apoio à decisão  

---

## ⚠️ Limitações
- O Prophet assume uma estrutura **aditiva**, podendo não capturar choques extremos do mercado  
- A performance depende diretamente da qualidade dos regressores externos  
- Eventos inesperados (crises energéticas, falhas sistêmicas) não são totalmente modelados  

---

## 🚀 Como Executar o Projeto

### 1️⃣ Clonar o repositório
```bash
git clone https://github.com/GuiAlves1611/prophet-model-energy.git
