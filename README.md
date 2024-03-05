# Procesamiento del lenguaje natural 

## Sistema RAG (Retrieval Augmented Generation)

### Trabajo práctico de la Tecnicatura Universitaria en Inteligencia Artificial UNR

## Descripción General
Un sistema RAG utiliza una técnica avanzada de procesamiento del lenguaje natural que combina la recuperación de información con la generación de texto. Permite a un usuario interactuar con un chatbot con información extraída de documentos o archivos específicos.

Este repositorio presenta el desarrollo de un sistema RAG, diseñado para abordar información relacionada con:

- Expertos, peritos o consultores en materia ambiental.
- Reservas naturales en provincias argentinas.
- Animales en peligro de extinción en Argentina.

### Fuentes de datos
El sistema RAG toma datos de dos fuentes de datos distintas, una base de datos vectorial y otra de grafos.

#### Base de datos vectorial (chromadb)
Los datos almacenados en la base de datos vectorial constan del libro "DOS DÉCADAS DE TRABAJO CON ESPECIES AMENAZADAS DE LA ARGENTINA" de más de 500 páginas que habla sobre especies en peligro de extinción en Argentina y datos tabulares provenientes de un archivo CSV (descargado de la página https://datos.gob.ar/) que trata sobre consultores, peritos y expertos en materia ambiental.

#### Base de datos en grafos (neo4j)
Los datos almacenados en la base de datos en grafos tratan sobre las reservas naturales de las provincias argentinas, conteniendo información del año de creación, cantidad de hectáreas que preservan, ambiente que protegen, entre otros datos.

### Funcionamiento del Sistema RAG
Luego de cargar los datos se realizan una serie de funciones que se encargan de clasificar la pregunta, obtener contexto y generar una respuesta.

#### 1. grafos()
Realiza consultas a la base de datos de grafos para obtener información sobre las reservas naturales ubicadas en una provincia específica.

#### 2. clasificador()
Clasifica las preguntas recibidas por RAG, devolviendo una tupla que indica la fuente de datos que se debe consultar para responder la pregunta, utilizando la técnica de few-shots.

#### 3. obtener_contexto()
Recibe la salida del clasificador y extrae el contexto necesario de las fuentes de datos para responder a la consulta.

#### 4. LLM()
Genera la instancia del Modelo de Lenguaje de Formato Largo (LLM) utilizado para la generación de texto.

#### 5. sistema()
Coordinador principal que invoca las funciones necesarias para generar una respuesta completa a una consulta.

#### 6. responder()
Encargada de dar formato a la respuesta generada por el modelo antes de ser presentada.

### Ejecución del sistema RAG
El sistema RAG se implementó desde un entorno colab. Para ejecutarlo, se deben proporcionar ciertas claves como API-KEYS personales y ejecutar las respectivas celdas de códigos.
