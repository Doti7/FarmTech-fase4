FarmTech Solutions – Fase 4
Assistente Agrícola Inteligente

Projeto desenvolvido na Fase 4 do Challenge FIAP, integrando IoT, Banco de Dados, Machine Learning e um Dashboard Interativo em Streamlit para criar um Assistente Agrícola Inteligente capaz de:

armazenar dados de sensores agrícolas

treinar modelos preditivos

estimar produtividade

sugerir ações de manejo (irrigação, pH e fertilização)

exibir gráficos e previsões de forma clara

1. Arquitetura Geral do Projeto

A arquitetura integra:

Sensores reais ou simulados

Banco de dados relacional

Pipeline de aprendizado de máquina

Aplicação web em Streamlit

Módulo de recomendações automáticas

O diagrama da arquitetura pode ser encontrado na pasta de diagramas.

2. Estrutura do Repositório
/
├── backend_ml/
│   ├── modelos/                  # modelos .pkl e arquivo de métricas
│   ├── modelos_preditivos.py     # pipeline de modelos
│   ├── treino_modelos.py         # treinamento dos modelos
│   ├── preprocessamento.py       # tratamento e montagem do dataset
│   ├── visualizacoes.py          # geração de gráficos analíticos
│   └── recomendacoes.py          # lógica de recomendações agrícolas
│
├── db/
│   ├── schema.sql                # criação das tabelas do banco
│   ├── seed_inicial.sql          # simulação de dados
│   └── ingestao_iot.py           # ingestão automatizada
│
├── streamlit_app/
│   └── app.py                    # dashboard interativo
│
├── assets/
│   ├── prints_banco/             # prints das tabelas e consultas
│   ├── prints_dashboard/         # prints de ML e dashboard
│   └── diagramas/                # diagramas e fluxos visuais
│
└── README.md

3. Banco de Dados (SQL)

O banco de dados foi modelado conforme princípios de ciência de dados cognitiva e contém as tabelas:

safra

sensor

leitura_sensor

manejo

Essas tabelas armazenam variáveis essenciais para análises preditivas, incluindo leituras de sensores e informações de irrigação e fertilização.

Os prints do banco (estrutura e consultas) encontram-se na pasta assets/prints_banco/.

4. Pipeline de Machine Learning

A solução treina e compara três modelos de regressão:

Regressão Linear

Regressão Ridge

Random Forest Regressor

Etapas executadas:

tratamento dos dados e montagem do dataset final

separação treino/teste

treinamento dos modelos

avaliação com métricas de erro

seleção do melhor modelo

integração com recomendações práticas

Métricas registradas em backend_ml/modelos/resultados_parte2.txt:

REGRESSÃO LINEAR
MAE  = 148.52
MSE  = 30584.13
RMSE = 174.85
R²   = 0.82

REGRESSÃO RIDGE
MAE  = 145.77
MSE  = 29741.09
RMSE = 172.43
R²   = 0.83

RANDOM FOREST REGRESSOR
MAE  = 112.34
MSE  = 18952.60
RMSE = 137.62
R²   = 0.91


O Random Forest apresentou o melhor desempenho e foi o modelo adotado para as previsões do dashboard.

5. Visualizações

Foram gerados gráficos para análise exploratória e avaliação dos modelos, incluindo:

dispersão entre umidade e produtividade

gráfico de resíduos

gráfico de valores reais versus previstos

Os prints das visualizações estão na pasta assets/prints_dashboard/.

6. Dashboard Streamlit

O dashboard permite:

inserir valores de umidade, pH, água e fertilizante

gerar uma previsão de produtividade baseada no modelo de Random Forest

exibir recomendações automáticas

visualizar métricas e gráficos de forma objetiva

Execução local:

pip install -r requirements.txt
streamlit run streamlit_app/app.py


Os prints da interface estão em assets/prints_dashboard/.

7. Recomendações Agrícolas Inteligentes

Com base na produtividade prevista, o sistema gera orientações automáticas relacionadas a:

volume de irrigação

correção de pH

adubação

impacto estimado na produtividade

Essas recomendações são calculadas a partir de regras de domínio e correlações observadas nos dados.

8. Vídeos de Apresentação

A entrega contempla dois vídeos:

Parte 1: pipeline de ML e dashboard

Parte 2: modelos preditivos, métricas e recomendações

Ambos mostram o funcionamento completo da solução do início ao fim.

9. Conclusão

A solução integra IoT, banco de dados, regressão, automação e visualização para criar um assistente agrícola inteligente, capaz de apoiar decisões reais no campo com base em dados.

Este projeto representa o avanço da Agricultura Cognitiva ao aplicar inteligência artificial para melhorar a eficiência e a produtividade agrícola.
