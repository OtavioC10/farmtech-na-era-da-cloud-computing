# 🌱 FarmTech na era da cloud computing


Este projeto foi desenvolvido como parte da disciplina de **Inteligência Artificial aplicada à Agricultura**, na FIAP.  
O objetivo é **analisar dados de condições climáticas e de solo** para prever o **rendimento de diferentes culturas agrícolas** em uma fazenda de médio porte, utilizando técnicas de **Machine Learning supervisionado e não supervisionado**.

---

## 👨‍💻 Integrantes do Grupo

- Otávio Custódio — RM: 565606  
- Matheus Parra — RM: 561907  
- Tiago Alves Cordeiro — RM: 561791  
- Thiago Henrique Pereira de Almeida Santos — RM: 563327  
- Leandro Arthur Marinho Ferreira — RM: 565240  

---

## 📂 Estrutura do Repositório

- `OtavioCustodio_RM565606_pbl_fase4.ipynb` → Notebook Jupyter principal com toda a análise, código e conclusões.  
- `crop_yield.csv` → Base de dados utilizada.  
- `requirements.txt` → Lista de bibliotecas necessárias para executar o notebook.  
- `README.md` → Este arquivo com instruções e informações do projeto.  

---

## 1️⃣ Entrega 1 — Análise e Modelagem de Machine Learning

### 1.1 Análise Exploratória

- Estatísticas descritivas, histogramas e boxplots das variáveis.  
- Detecção de outliers usando **IQR** e **IsolationForest**.  
- Clusterização com **KMeans** para identificar tendências e padrões de rendimento.

### 1.2 Modelos Preditivos

Foram treinados 5 modelos de regressão supervisionada:

| Modelo               | RMSE (teste) | MAE (teste) | R² (teste) | Observação |
|---------------------|--------------|-------------|------------|------------|
| Regressão Linear     | 4394         | 3132        | 0.995      | Melhor modelo |
| Random Forest        | 4549         | 2567        | 0.9946     | Próximo da Linear |
| Gradient Boosting    | 6187         | 3407        | 0.990      | Bom desempenho |
| KNN Regressor        | 6915         | 4192        | 0.9877     | Desempenho mediano |
| SVR (RBF)            | 71125        | 38753       | -0.30      | Não generalizou |

**Conclusão:** A **Regressão Linear** foi o modelo mais eficiente para este dataset, explicando quase toda a variância dos dados.  

---

### 1.3 Vídeo Demonstrativo

Gravamos um vídeo mostrando a execução do notebook e análise dos resultados:  
- **Título:** “Entrega 1 — Modelagem e Resultados ML”  
- **Visibilidade:** Não listado  
- **Link:**  
[Link para o vídeo](https://youtu.be/tP3mAiOYjtQ)

---

---

## 2️⃣ Entrega 2 — Estimativa de Custos AWS e Decisão de Região

### 2.1 Estimativa de Custos

Utilizamos a **AWS Pricing Calculator** para estimar os custos de uma máquina **Linux On-Demand (100%)** com:

- 2 vCPUs  
- 1 GiB de memória (próximo → instância t3.small 2 GiB)  
- Até 5 Gbps de rede  
- 50 GB de armazenamento EBS  

| Região             | Instância | Custo estimado (USD/mês) | Observações |
|-------------------|-----------|--------------------------|-------------|
| Virgínia do Norte | t3.small  | **8,52 USD**             | Região mais barata |
| São Paulo         | t3.small  | **13,26 USD**            | Região mais cara, mas atende requisitos legais |

> Valores obtidos diretamente na **AWS Pricing Calculator** (2025), considerando EC2 + 50 GB EBS.

---

### 2.2 Escolha da Região

Optamos por hospedar a instância em **São Paulo (sa-east-1)**.  

**Justificativa:**

1. **Conformidade legal**: garante que dados sensíveis permaneçam em território nacional.  
2. **Baixa latência**: acesso mais rápido aos sensores e processamento em tempo real.  
3. **Custo justificável**: mesmo sendo **~55% mais caro** que Virgínia do Norte, atende às necessidades de compliance e performance local.

---

### 2.3 Evidências

- 📸 **Print da AWS Pricing Calculator** (comparando São Paulo e Virgínia do Norte)  
  *(adicione a captura de tela aqui)*

- 📺 **Vídeo Demonstrativo (até 5 minutos, não listado)**  
[Link para o vídeo](https://youtu.be/XhTxATA2ML4?si=rJXKc8309zmI3DdL)

---

✅ **Conclusão Final:**  

- **Entrega 1:** ML foi treinada com sucesso, melhor modelo identificado (Regressão Linear).  
- **Entrega 2:** Instância EC2 em São Paulo é a melhor opção para hospedar a API de sensores, garantindo legalidade, desempenho e confiabilidade, mesmo com custo ligeiramente maior (**13,26 USD/mês**).

