# FIAP - Faculdade de Informática e Administração Paulista  

<p align="center">
<a href="https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# FarmTech Solutions – Fase 4: Memorizando e Aprendendo com os Dados da Farm Tech Solutions

## Integrantes
- [Leticia Grossi Dornelas - RM568172](https://www.linkedin.com/in/leticiagdornelas/)
- [Leonardo Borges Alves da Mota - RM566939](https://www.linkedin.com/in/leonardo-borges-alves-da-mota-649703177/)  
- [Bernardo Naves Doti Avelar - RM566867](https://www.linkedin.com/in/bernardo-doti/)  
- [David Eduardo da Silva Correia - RM567525](https://www.linkedin.com/in/eduardo-correia-29327631/)

## Professores  
### Tutor(a)
- Ana Cristina dos Santos 
### Coordenador(a)
- André Godoi Chiovato

---

## 1. Descrição e Objetivo

Projeto desenvolvido na Fase 4 do Challenge FIAP, integrando IoT, Banco de Dados, Machine Learning e um Dashboard Interativo em Streamlit para criar um Assistente Agrícola Inteligente capaz de:

- armazenar dados de sensores agrícolas
- treinar modelos preditivos
- estimar produtividade
- sugerir ações de manejo (irrigação, pH e fertilização)
- exibir gráficos e previsões de forma clara

---

## 2. Arquitetura Geral do Projeto

A arquitetura integra:
- Sensores reais ou simulados
- Banco de dados relacional
- Pipeline de aprendizado de máquina
- Aplicação web em Streamlit
- Módulo de recomendações automáticas
- O diagrama da arquitetura pode ser encontrado na pasta de diagramas.

---

## 3. Estrutura do Repositório

FarmTech-fase4/
│
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

---

## 4. Banco de Dados (SQL)

O banco de dados foi modelado conforme princípios de ciência de dados cognitiva e contém as tabelas:
- safra
- sensor
- leitura_sensor
- manejo

Essas tabelas armazenam variáveis essenciais para análises preditivas, incluindo leituras de sensores e informações de irrigação e fertilização.

Os prints do banco (estrutura e consultas) encontram-se na pasta assets/prints_banco/.

---

## 5. Pipeline de Machine Learning

A solução treina e compara três modelos de regressão:
- Regressão Linear
- Regressão Ridge
- Random Forest Regressor

Etapas executadas:
- tratamento dos dados e montagem do dataset final
- separação treino/teste
- treinamento dos modelos
- avaliação com métricas de erro
- seleção do melhor modelo
- integração com recomendações práticas

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

---

## 6. Visualizações

Foram gerados gráficos para análise exploratória e avaliação dos modelos, incluindo:
- dispersão entre umidade e produtividade
- gráfico de resíduos
- gráfico de valores reais versus previstos

Os prints das visualizações estão na pasta assets/prints_dashboard/.

---

## 7. Dashboard Streamlit

O dashboard permite:
- inserir valores de umidade, pH, água e fertilizante
- gerar uma previsão de produtividade baseada no modelo de Random Forest
- exibir recomendações automáticas
- visualizar métricas e gráficos de forma objetiva

Execução local:

pip install -r requirements.txt
streamlit run streamlit_app/app.py

Os prints da interface estão em assets/prints_dashboard/.

---

## 8. Recomendações Agrícolas Inteligentes

Com base na produtividade prevista, o sistema gera orientações automáticas relacionadas a:
- volume de irrigação
- correção de pH
- adubação
- impacto estimado na produtividade

Essas recomendações são calculadas a partir de regras de domínio e correlações observadas nos dados.

---

## 9. Vídeo de Apresentação

A entrega do video contempla:
- Parte 1: pipeline de ML e dashboard
- Parte 2: modelos preditivos, métricas e recomendações
- link: (https://youtu.be/3OPDGnlfr1w)

---

## 10. Conclusão

A solução integra IoT, banco de dados, regressão, automação e visualização para criar um assistente agrícola inteligente, capaz de apoiar decisões reais no campo com base em dados.

Este projeto representa o avanço da Agricultura Cognitiva ao aplicar inteligência artificial para melhorar a eficiência e a produtividade agrícola.

---

## Histórico de Lançamentos  

* 0.1.0 - 27/11/2025  
  * Entrega da Fase 4 – Memorizando e Aprendendo com os Dados da Farm Tech Solutions. 

---

## Licença  

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1">

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/">
<a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sob 
<a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.
</p>
