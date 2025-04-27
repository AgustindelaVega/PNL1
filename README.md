# Procesamiento de Lenguaje Natural (PNL1)

## Alumno

**Nombre**: Agustín de la Vega

**Nº SIU**: a1713

## Descripción

Este repositorio contiene los cuatro desafíos realizados durante el curso de Procesamiento de Lenguaje Natural en la carrera de Especialización en Inteligencia Artificial de la FIUBA. Cada notebook contiene la implementación y experimentación para un problema específico en el campo del PLN.

## Contenido

- [Desafío 1: Vectorización y Similitud de Documentos](#desafío-1-vectorización-y-similitud-de-documentos)
- [Desafío 2: Embeddings Personalizados](#desafío-2-embeddings-personalizados)
- [Desafío 3: Modelo de lenguaje con tokenización por caracteres](#desafío-3-modelo-de-lenguaje-con-tokenización-por-caracteres)
- [Desafío 4: Bot QA con LSTM](#desafío-4-bot-qa-con-lstm)

## Desafío 1: Vectorización y Similitud de Documentos

![Naive Bayes Classifier](/images/naive_bayes.png)

### Problema

Vectorización de texto y clasificación de noticias utilizando el dataset 20 Newsgroups. El desafío incluye la exploración de similaridad entre documentos, optimización de modelos de clasificación, y análisis de similaridad entre términos.

### Arquitecturas Implementadas

- Vectorización mediante Bag of Words (BoW) y TF-IDF
- Naïve Bayes Multinomial
- Complement Naïve Bayes
- Análisis de similaridad coseno entre documentos y términos

### Resultados

Se logró mejorar significativamente el desempeño de clasificación desde un F1-score baseline de 0.58 hasta 0.77 mediante la optimización de hiperparámetros. Se verificó que el análisis de similaridad produce agrupaciones semánticamente coherentes tanto a nivel de documentos como de términos.

### Implementación

[Ver notebook completo](desafio_1/desafio_1.ipynb)

---

## Desafío 2: Embeddings Personalizados

![Word2Vec](/images/word2vec.jpeg)

### Problema

Creación y análisis de word embeddings utilizando Gensim y Word2Vec, explorando las relaciones semánticas entre palabras en el texto de "Moby Dick" de Herman Melville.

### Arquitecturas Implementadas

- Word2Vec (Skip-gram) con Gensim
- Visualización de embeddings en 2D y 3D mediante t-SNE
- Análisis de similaridad entre términos

### Resultados

El modelo de Word2Vec demostró una notable capacidad para identificar:

- Relaciones semánticas entre términos del ámbito náutico (ship, vessel, craft, harpoon)
- Agrupaciones de términos relacionados con el océano y la caza de ballenas
- Relaciones entre personajes del libro (Ahab, Queequeg, Captain)
- Agrupaciones de palabras por categorías semánticas (números, unidades de medida, partes del barco)

Se verificó que las palabras similares en el espacio de embeddings reflejan relaciones significativas dentro del contexto de la obra literaria, demostrando la efectividad del modelo para capturar el significado semántico a partir del contexto.

### Implementación

[Ver notebook completo](desafio_2/desafio_2.ipynb)

---

## Desafío 3: Modelo de lenguaje con tokenización por caracteres

![RNN](/images/rnn.jpg)


### Problema

Implementación de un modelo de lenguaje con tokenización por caracteres utilizando el libro "Don Quijote" como corpus para generar texto automáticamente.

### Arquitecturas Implementadas

- SimpleRNN (200 neuronas)
- GRU (dos capas de 128 unidades)
- LSTM (dos capas de 128 unidades)

### Resultados

- **SimpleRNN**: Perplejidad mínima ~5.11, genera texto con repeticiones y poca coherencia.
- **GRU**: Perplejidad mínima ~4.5, mejor rendimiento que SimpleRNN pero con patrones repetitivos.
- **LSTM**: Perplejidad mínima ~4.60, genera texto más coherente y con puntuación adecuada.

Se implementaron estrategias de generación por greedy search y beam search, donde LSTM demostró mejor calidad y coherencia.

### Implementación

[Ver notebook completo](desafio_3/desafio_3.ipynb)

---

## Desafío 4: Bot QA con LSTM

![QA_BOT](/images/QA_BOT.jpg)

### Problema

Desarrollo de un chatbot basado en arquitectura encoder-decoder para responder preguntas del usuario utilizando datos de conversaciones del challenge ConvAI2. El objetivo fue construir un sistema de pregunta-respuesta que pudiera mantener conversaciones coherentes.

### Arquitectura Implementada

- Arquitectura Encoder-Decoder con LSTM
- Mecanismo de atención para mejorar las respuestas generadas
- Uso de embeddings pre-entrenados de GloVe (300 dimensiones)
- Tokenización de entrada y salida con manejo de vocabulario limitado

### Resultados

El modelo mostró capacidad para generar respuestas coherentes a preguntas simples ("Do you read?" → "yes i do", "How are you?" → "i am doing well how are you"). Sin embargo, en preguntas más complejas o fuera del dominio de entrenamiento, las respuestas resultaron genéricas o semánticamente irrelevantes.

El uso del mecanismo de atención permitió al modelo enfocarse en las partes relevantes de la pregunta para generar respuestas más adecuadas, aunque con limitaciones. La curva de aprendizaje mostró convergencia después de aproximadamente 10 épocas, con una precisión de validación del 73%.

### Implementación

[Ver notebook completo](desafio_4/desafio_4.ipynb)

---

**Nota:** Para obtener información detallada sobre cada desafío, metodología y resultados específicos, consulte los notebooks individuales.
