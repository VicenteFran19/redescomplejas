# 🔗 Análisis de Redes de Garantías Crediticias

Este repositorio contiene el desarrollo completo de una tarea formativa para el curso de *Redes Complejas* del programa de Maestría en Data Science en la Universidad Peruana de Ciencias Aplicadas (UPC). El trabajo analiza una red simulada de garantías entre empresas, utilizando técnicas de minería de grafos, predicción de enlaces y evaluación de robustez sistémica.

---

## 🧠 Objetivo del Proyecto

Simular, modelar y analizar una red financiera donde empresas actúan como garantes de otras en operaciones de crédito, identificando:
- Subestructuras de riesgo (triángulos, cliques),
- Posibles enlaces futuros mediante predicción,
- Nodos críticos cuya falla podría fragmentar o comprometer la red.

---

## 📂 Estructura del Repositorio

```
📁 redes-garantias-crediticias/
│
├── M8_Trabajo_Final_Redes_Garantias_Notebook.ipynb   # Notebook con todo el análisis y visualización
├── M8_Trabajo_Final_Redes_Garantias_Informe.pdf      # Informe académico con resultados, discusión y recomendaciones
├── data/
│   └── garantias_dataset_final.csv                             # Dataset simulado de relaciones de garantía (si aplica)
├── images/
│   └── *.png                                          # Gráficos exportados (grafo, cliques, heatmaps, curvas ROC, etc.)
└── README.md                                          # Este archivo
```

---

## 🛠️ Herramientas y Librerías Utilizadas

- Python 3.10+
- NetworkX
- pandas / numpy
- matplotlib / seaborn
- scikit-learn (RandomForestClassifier, métricas)
- Jupyter Notebook

---

## 🔍 Principales Análisis Realizados

1. **Construcción del grafo dirigido y ponderado** a partir de datos de garantías financieras simuladas.
2. **Clasificación de roles**: garante, avalado o mixto.
3. **Identificación de subestructuras frecuentes**:
   - Triángulos: 786 (riesgo recíproco).
   - Cliques ≥ 3 nodos: 660 (riesgo concentrado).
4. **Predicción de enlaces**:
   - Common Neighbors (Prec/Rec: 0.80 / AUC: 0.89)
   - Jaccard Coefficient (Prec/Rec: 0.80 / AUC: 0.88)
   - Random Forest Classifier (Prec: 0.85 / AUC: 0.91)
5. **Evaluación de robustez** de la red frente a fallas de nodos críticos (top betweenness).
6. **Visualización interactiva** y dashboards exportables para decisiones gerenciales.

---

## 📊 Resultados Clave

- La red presenta alta interconectividad (densidad ≈ 0.17, 1 solo componente).
- Los cliques grandes concentran riesgo sistémico y deben ser monitoreados.
- El modelo Random Forest mejora la precisión de predicción de nuevas garantías.
- La red es vulnerable: basta remover 5 nodos del clique principal para reducir en un 4.17% el componente gigante.

---

## 📌 Recomendaciones Estratégicas

- Limitar la formación de cliques > 8 nodos.
- Implementar alertas automáticas cuando densidad intra-cluster supere el 15%.
- Integrar el modelo de predicción en el dashboard de riesgo para scoring preventivo.

---

## 🧑‍💻 Autor

**Francis Javier Vicente Romero**  
Maestría en Data Science | Universidad Peruana de Ciencias Aplicadas (UPC)

---

## 📄 Referencias

- Newman, M. (2010). *Networks: An Introduction*. Oxford.
- Wasserman, S., & Faust, K. (1994). *Social Network Analysis*.
- Lü & Zhou (2011). *Link Prediction in Complex Networks*. Physica A.
- Borgatti & Everett (2006). *Graph-Theoretic Centrality*. Social Networks.
