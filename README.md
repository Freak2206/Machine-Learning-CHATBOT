Previsão de Cancelamento de Clientes (Churn) em Streaming com Orange Data Mining

Projeto da disciplina Machine Learning & Chatbot (UniFECAF) que constrói um modelo preditivo para identificar clientes com alta probabilidade de cancelamento em um serviço de streaming fictício, usando o Orange Data Mining.

 Objetivo

Prever quais clientes têm maior propensão a cancelar o serviço (churn), a partir de dados demográficos, de consumo e de pagamento, permitindo à empresa direcionar ações de retenção de forma proativa em vez de campanhas genéricas.

🗂️ Estrutura do repositório
├── clientes_streaming_churn.csv              # base de dados (1.200 clientes simulados)
├── previsao_churn_streaming.ows              # fluxo completo do Orange Data Mining
├── Relatorio_Churn_Streaming_UniFECAF.docx   # relatório analítico (parte teórica)
└── README.md
🔧 Como reproduzir
Baixe e instale o Orange Data Mining.
Abra o arquivo previsao_churn_streaming.ows.
Quando solicitado, aponte o widget File para o arquivo clientes_streaming_churn.csv.
O fluxo já contém todo o pipeline: File → Preprocess → Logistic Regression / Random Forest → Test & Score → Confusion Matrix / ROC Analysis.
🧠 Pipeline de Machine Learning
Etapa	Widget	Descrição
Carregamento	File	Leitura da base, com cancelou como variável-alvo
Pré-processamento	Preprocess	Normalização das variáveis numéricas e tratamento de outliers
Modelagem	Logistic Regression, Random Forest	Treinados com balanceamento de classes
Validação	Test & Score	Validação cruzada (10 folds estratificados)
Avaliação	Confusion Matrix, ROC Analysis	Comparação de desempenho entre os modelos
📊 Principais resultados
Métrica	Regressão Logística	Random Forest
Acurácia (CA)	0,703	0,787
Precisão (classe "cancela")	0,365	0,426
Recall (classe "cancela")	0,694	0,255
F1-score	0,478	0,319
AUC (ROC)	0,794	0,695

A Regressão Logística foi o modelo escolhido: mesmo com acurácia geral menor, ela identifica corretamente 69% dos clientes que de fato cancelam — o que importa mais para uma estratégia de retenção do que a acurácia bruta.

Principais fatores associados ao churn: engajamento (horas de uso semanais), tempo de assinatura e satisfação declarada do cliente.


🛠️ Tecnologias
Orange Data Mining — construção e avaliação do modelo
Python (pandas, scikit-learn, matplotlib) — geração e análise exploratória da base simulada

👤 Autor

Felipe Queiroz Santos — RA 138226 Centro Universitário UniFECAF — Análise e Desenvolvimento de Sistemas
