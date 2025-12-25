Previsão de Preços de Energia com Prophet (Séries Temporais)
Este projeto implementa um modelo de aprendizado de máquina utilizando a biblioteca Facebook Prophet para prever o preço horário da energia elétrica. O modelo integra 14 variáveis externas (regressores) para capturar a dinâmica complexa entre oferta, demanda e clima.

📊 Resultados e Performance
O modelo foi treinado com dados de agosto a dezembro de 2018 e validado para o início de 2019.

RMSE (Erro Quadrático Médio): 3.96.

MAPE (Erro Médio Absoluto Percentual): ~5.3%.

Estabilidade: A tendência foi controlada (changepoint_prior_scale=0.01) para garantir previsões realistas mesmo sob alta carga.

🛠️ Variáveis Utilizadas (Extra Regressors)
O diferencial deste modelo é a utilização de múltiplos fatores que influenciam o preço:

Carga (Load): Previsão de carga total do sistema (máximo observado: 30619.0).

Geração: Dados de geração fóssil e renovável (solar, eólica, etc.).

Clima: Temperatura e condições meteorológicas.

🚀 Como Executar o Projeto
Pré-requisitos
Certifique-se de ter o Python instalado. É recomendado o uso de um ambiente virtual (venv).

Instalação
Clone o repositório:

Bash

git clone https://github.com/GuiAlves1611/prophet-model-energy.git
Instale as dependências:

Bash

pip install -r requirements.txt
Uso do Modelo
Para utilizar o modelo treinado sem precisar reprocessar os dados:

Python

import joblib

# Carregar o modelo salvo
model = joblib.load('modelo_prophet_energia_v1.joblib')

# Gerar previsão (requer dataframe com regressores)
# forecast = model.predict(future_df)
📈 Visualizações
O projeto inclui visualizações interativas geradas com Plotly, permitindo analisar:

Componentes da série (tendência, sazonalidade diária e impacto dos regressores).

Comparação entre valores reais e previstos.

Evolução do erro ao longo do horizonte de previsão.