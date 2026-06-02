# Proyecto 3 — Procesamiento de Lenguaje Natural
## Question Answering extractivo con fine-tuning de DistilBERT sobre SQuAD

**Curso:** Procesamiento de Lenguaje Natural  
**Integrantes:** Diego Murillo, Santiago Arango

---

## Descripción

Este proyecto resuelve un problema de **Question Answering extractivo**: dado un párrafo de texto y una pregunta, el modelo extrae del propio texto el fragmento exacto que responde la pregunta.

Se aplicó **fine-tuning** sobre **DistilBERT** (`distilbert-base-uncased`), un modelo tipo BERT, usando el dataset **SQuAD v1.1** de Hugging Face. Se probaron distintos valores de learning rate para seleccionar el mejor modelo.

---

## Dataset

- **Nombre:** SQuAD v1.1 (Stanford Question Answering Dataset)
- **Fuente:** [Hugging Face — rajpurkar/squad](https://huggingface.co/datasets/rajpurkar/squad)
- **Dominio:** Comprensión lectora sobre artículos de Wikipedia en inglés
- **Tamaño usado:** 6.000 ejemplos de entrenamiento / 1.000 de validación

---

## Resultados

| Learning Rate | Span Accuracy | Eval Loss |
|---|---|---|
| 5e-5 | 0.387 | 1.71 ✅ mejor |
| 3e-5 | 0.351 | 1.82 |
| 2e-5 | 0.315 | 2.00 |

**Prueba cualitativa sobre texto no visto (Amazonas):**

| Pregunta | Respuesta del modelo |
|---|---|
| What type of forest is the Amazon? | moist broadleaf |
| How much of the rainforest does Brazil hold? | 60% |
| Where is the Amazon basin located? | South America |

---

## Cómo ejecutar

1. Abrir el notebook en Google Colab: [Abrir en Colab](https://colab.research.google.com/)
2. Activar GPU: *Entorno de ejecución → Cambiar tipo de entorno de ejecución → GPU T4*
3. Ejecutar todas las celdas en orden de arriba a abajo
4. El entrenamiento completo tarda aproximadamente 20 minutos

---

## Estructura del repositorio

---

## Tecnologías usadas

- Python 3.10
- Hugging Face Transformers
- Hugging Face Datasets
- PyTorch
- Google Colab (GPU T4)
