Com certeza! Vou estruturar o conteúdo do seu README.md com a sintaxe Markdown completa. Você pode simplesmente copiar o bloco de código abaixo e colar no seu arquivo.

Markdown

# ⚡ Previsão de Preços de Energia com Prophet

![Status](https://img.shields.io/badge/Status-Finalizado-success)
![Precisão](https://img.shields.io/badge/RMSE-3.96-blue)

Este projeto utiliza o modelo **Facebook Prophet** para realizar a previsão horária do preço de energia elétrica, integrando **14 regressores externos** para capturar a complexidade do mercado energético.

---

## 📊 Performance do Modelo

O modelo apresentou uma alta fidelidade aos dados reais, mantendo uma tendência estável mesmo em períodos de alta volatilidade.

* **Erro Quadrático Médio (RMSE):** `3.96`
* **MAPE:** `~5.3%`
* **Configuração de Tendência:** `changepoint_prior_scale = 0.01` (ajustado para evitar distorções por valores extremos)

---

## 🛠️ Variáveis de Entrada (Extra Regressors)

Diferente de modelos simples, este projeto considera fatores críticos que influenciam o preço:

1.  **Demanda:** `total load forecast` (com picos de até **30619.0**).
2.  **Geração:** Matriz fóssil e renovável (eólica, solar, etc.).
3.  **Clima:** Dados de temperatura e condições meteorológicas.

Esses regressores chegam a impactar o preço final em até **11 €** para cima ou para baixo, dependendo da carga do sistema.

---

## 🚀 Como Utilizar

### 1. Instalação
Clone o repositório e instale as dependências listadas no `requirements.txt`:
```bash
git clone [https://github.com/GuiAlves1611/prophet-model-energy.git](https://github.com/GuiAlves1611/prophet-model-energy.git)
pip install -r requirements.txt