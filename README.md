# Descripción General

Este repositorio presenta el desarrollo del sistema RAG (Recuperación-Aumento de Generación), 
diseñado para abordar información relacionada con reservas ecológicas, animales en peligro de 
extinción y expertos ambientales en Argentina. Los datos fundamentales para este sistema se 
extrajeron de un extenso libro con más de 500 páginas y dos archivos CSV, que luego se 
organizaron en dos tipos de bases de datos: una vectorial (chromadb) y otra de grafos (neo4j).

## Funciones del Sistema RAG

### 1. grafos()
Realiza consultas a la base de datos de grafos para obtener información sobre las reservas naturales ubicadas en una provincia específica.

### 2. clasificador()
Clasifica las preguntas recibidas por RAG, devolviendo una tupla que indica la fuente de datos que se debe consultar para responder la pregunta, utilizando la técnica de few-shots.

### 3. obtener_contexto()
Recibe la salida del clasificador y extrae el contexto necesario de las fuentes de datos para responder a la consulta.

### 4. LLM()
Genera la instancia del Modelo de Lenguaje de Formato Largo (LLM) utilizado para la generación de texto.

### 5. sistema()
Coordinador principal que invoca las funciones necesarias para generar una respuesta completa a una consulta.

### 6. responder()
Encargada de dar formato a la respuesta generada por el modelo antes de ser presentada.
