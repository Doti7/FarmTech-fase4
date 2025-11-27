# 🌾 FarmTech Solutions – Fase 4  
### Assistente Agrícola Inteligente com IA, Banco de Dados e Dashboard

Este repositório faz parte da Fase 4 do projeto **FarmTech Solutions**, desenvolvido na disciplina de Inteligência Artificial aplicada ao Agronegócio.

O foco desta etapa é mostrar, na prática, como os dados que vêm do campo (sensores, manejo e produtividade) podem ser organizados em um **banco de dados relacional**, usados para treinar **modelos de regressão** e apresentados em um **dashboard interativo** para apoiar decisões de gestão agrícola.

---

## 👥 Contexto do Projeto

- Curso: Tecnólogo em Inteligência Artificial  
- Instituição: FIAP  
- Fase: 4 – Previsão Inteligente na Agricultura  
- Grupo: 
   Leticia Grossi Dornelas – RM568172
   Leonardo Borges Alves da Mota – RM566939
   Bernardo Naves Doti Avelar – RM566867
   David Eduardo da Silva Correia - RM567525
- Responsável por Banco + Integração + Documentação: **(seu nome aqui)**  

---

## 🎯 Objetivo da Fase 4

Construir um **protótipo de Assistente Agrícola Inteligente** capaz de:

1. **Armazenar dados agrícolas**  
   - Campos (talhões)  
   - Safras  
   - Sensores (umidade, pH, etc.)  
   - Leituras dos sensores  
   - Eventos de manejo (irrigação, fertilização)  
   - Produtividade final das safras  

2. **Preparar os dados para modelos de Machine Learning (regressão)**  
   - A partir dos dados históricos, gerar uma base consolidada para treinar modelos.  

3. **Permitir previsões e recomendações via dashboard (Streamlit)**  
   - Prever variáveis como umidade, necessidade de irrigação, e rendimento estimado.  
   - Exibir métricas de desempenho (MAE, MSE, RMSE, R²).  

4. **Oferecer uma visão integrada de “Agricultura Cognitiva”**  
   - Sensores + Banco de Dados + IA + Visualização → campo mais eficiente e sustentável.

---

## 🧱 Arquitetura Geral da Solução

A solução foi organizada em camadas:

1. **Camada de Dados (Banco SQL – pasta `db/`)**
   - Modelagem das tabelas principais do contexto agrícola.
   - Scripts de criação e povoamento inicial.
   - Script extra para simular ingestão de dados de sensores IoT.

2. **Camada de Machine Learning (pasta `backend_ml/`)**
   - Scripts responsáveis por:
     - preparar os dados,
     - treinar modelos de regressão,
     - salvar modelos para uso no dashboard.

3. **Camada de Visualização / Interface (pasta `streamlit_app/`)**
   - Aplicação em Streamlit que:
     - consome os modelos treinados,
     - exibe gráficos e métricas,
     - permite simular cenários e obter previsões.

4. **Evidências e Materiais de Apoio (pasta `assets/`)**
   - Prints do banco de dados,
   - prints do dashboard,
   - diagramas de arquitetura, se necessários.

---

## 📂 Estrutura de Pastas

```text
FarmTech-fase4/
│
├── backend_ml/
│   ├── preprocessamento.py       # limpeza, seleção de features, etc.
│   ├── treino_modelos.py         # treinamento dos modelos de regressão
│   ├── avaliacao_modelos.py      # cálculo de métricas (MAE, MSE, RMSE, R²)
│   └── modelos/                  # modelos treinados (arquivos .pkl, por exemplo)
│
├── streamlit_app/
│   └── app.py                    # aplicação Streamlit (dashboard do gestor)
│
├── db/
│   ├── schema.sql                # definição das tabelas do banco de dados
│   ├── seed_inicial.sql          # insert de dados iniciais (campo, safra, sensores, etc.)
│   ├── ingestao_iot.py           # script para simular leituras de sensores IoT
│   └── consultas_exemplo.sql     # consultas SQL usadas para análise e prints
│
├── data/
│   ├── raw/                      # dados brutos (se houver CSVs de sensores, etc.)
│   └── processed/                # bases tratadas usadas no treinamento de ML
│
├── assets/
│   ├── prints_banco/             # evidências do banco: consultas, tabelas, etc.
│   ├── prints_dashboard/         # evidências do dashboard: gráficos, métricas, etc.
│   └── diagramas/                # diagramas de arquitetura/modelagem
│
├── README.md                     # este documento
└── requirements.txt              # bibliotecas Python utilizadas no projeto
