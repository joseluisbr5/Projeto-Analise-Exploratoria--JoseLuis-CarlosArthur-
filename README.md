# 📦 Projeto Final – Ciência de Dados  
**Análise e Pré-Processamento dos Dados do E-commerce Olist**

---

## 👥 Integrantes do Grupo
- José Luis Meneses da Silva  
- [Adicionar nomes dos outros integrantes, se houver]

---

## 🔗 Base de Dados Utilizada  
Os seguintes datasets oficiais da Olist foram utilizados no projeto:

- **olist_orders_dataset.csv**  
- **olist_order_items_dataset.csv**  
- **olist_products_dataset.csv**

📌 Disponível publicamente em:  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

---

## 🎯 Objetivo do Projeto
O objetivo deste trabalho é realizar um **pipeline completo de pré-processamento** sobre os dados do e-commerce Olist, aplicando todas as etapas de limpeza, padronização, tratamento de inconsistências, engenharia de atributos, codificação, normalização e seleção de atributos.

O resultado final consiste em duas bases tratadas:

- `olist_clean_final.csv.gz` → Base limpa, padronizada e codificada.  
- `olist_clean_scaled.csv.gz` → Base final normalizada e pronta para modelagem.

---

## 🛠️ Descrição do Processo de Tratamento dos Dados
O pipeline completo atravessa as seguintes fases:

### **1. Conversão e Padronização de Tipos**  
- Conversão de colunas de data para o tipo `datetime`.  
- Correção de tipos numéricos inconsistentes.

### **2. Limpeza dos Dados**  
- Remoção de duplicatas.  
- Tratamento de valores ausentes com estratégias adequadas (remoção, mediana, zero ou "desconhecido").  
- Correção de valores impossíveis (dimensões = 0, peso = 0g).  
- Análise de outliers com boxplots.

### **3. Feature Engineering**  
Criação de variáveis que adicionam contexto operacional e logístico ao dataset:
- `delivery_delay_days`  
- `delivered_late`  
- `freight_ratio`  
- `product_volume_cm3`

### **4. Tratamento e Codificação de Categóricos**  
- Padronização das categorias.  
- Agrupamento de categorias raras em "other".  
- One-Hot Encoding para uso em modelos estatísticos.

### **5. Seleção de Atributos**  
- Remoção de variáveis com baixa variância.  
- Remoção de colunas altamente correlacionadas (multicolinearidade).  
- Redução de ruído e dimensionalidade.

### **6. Normalização (Z-score)**  
- Padronização das variáveis numéricas para média 0 e desvio 1.  
- Melhora da estabilidade dos modelos preditivos.

---

## ⚠️ Principais Desafios Encontrados
- Grande quantidade de valores ausentes e inconsistências nas dimensões dos produtos.  
- Distorção na distribuição de preços, com forte presença de outliers.  
- Volume elevado de categorias — exigiu tratamento de categorias raras.  
- Necessidade de sincronizar datas e timestamps para cálculo correto de atrasos.  
- Tamanho grande do CSV final, necessitando compactação para upload no GitHub.

---

## 📌 Principais Conclusões
- **Frete é fortemente influenciado por peso e volume**, reforçando a importância das dimensões na logística.  
- **Atrasos de entrega estão ligados ao tempo de aprovação e processamento interno**, não apenas ao transporte.  
- **Categorias volumosas apresentam mais atrasos**, indicando maior complexidade operacional.  
- **A variável preço apresenta forte assimetria e outliers**, o que impacta diretamente análises estatísticas.  
- O pipeline gerou um dataset final **limpo, consistente, padronizado e enriquecido**, adequado para análises futuras e modelos preditivos.

---

## 📎 Estrutura Final do Projeto
├── notebook_pipeline.ipynb
├── olist_clean_final.csv.gz
├── olist_clean_scaled.csv.gz
├── README.md
└── Relatorio_Final.pdf
