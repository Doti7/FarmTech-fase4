# 🌾 FarmTech Solutions – Fase 4  
### Assistente Agrícola Inteligente com IA, Banco de Dados e Dashboard

Este repositório faz parte da Fase 4 do projeto **FarmTech Solutions**, desenvolvido na disciplina de Inteligência Artificial aplicada ao Agronegócio.

O foco desta etapa é mostrar, na prática, como os dados que vêm do campo (sensores, manejo e produtividade) podem ser organizados em um **banco de dados relacional**, usados para treinar **modelos de regressão** e apresentados em um **dashboard interativo** para apoiar decisões de gestão agrícola.

---

## 👥 Contexto do Projeto

- Curso: Tecnólogo em Inteligência Artificial  
- Instituição: FIAP  
- Fase: 4 – Previsão Inteligente na Agricultura  
- Grupo: FarmTech Solutions  
- Responsável por Banco + Integração + Documentação: Bernardo D. - RM566867 

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
   - P

