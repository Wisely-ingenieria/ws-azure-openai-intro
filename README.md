# Azure Cognitive Search con OpenAI

Este repositorio contiene tres archivos de prueba de Python que demuestran cómo usar OpenAI y Azure Cognitive Search para crear un poderoso motor de búsqueda y chatbot.

`01_create_index.ipynb`

- Este es un Jupyter Notebook que contiene el código para crear un índice en Azure Cognitive Search. Primero instala todas las bibliotecas necesarias, luego carga las credenciales de OpenAI y Azure desde un archivo .env. 

- Después de establecer los clientes de Azure, crea un esquema de índice y lo sube a Azure. Luego, convierte los archivos PDF en el directorio de datos en texto y genera embeddings para cada página utilizando la API de OpenAI. Finalmente, sube estos datos al índice de Azure.

`02_search_queries.ipynb`

- Este Jupyter Notebook demuestra cómo realizar diferentes tipos de búsquedas utilizando Azure Cognitive Search y OpenAI. Empieza por establecer los clientes de Azure y luego realiza una búsqueda simple, una búsqueda semántica, una búsqueda vectorial y dos tipos de búsquedas híbridas. 

- Los resultados de cada tipo de búsqueda se imprimen en la consola para comparar la efectividad de cada método.

`03_chatbot_rag.py`

- Este es un script de Python que crea un chatbot utilizando Streamlit, OpenAI y Azure Cognitive Search. Primero, establece los clientes de Azure y OpenAI. Luego, utiliza Streamlit para crear la interfaz de usuario del chatbot.

- Cuando un usuario envía un mensaje, el chatbot utiliza Azure Cognitive Search para buscar documentos relevantes. Luego, genera embeddings para la consulta del usuario y realiza una búsqueda vectorial para encontrar los documentos más relevantes. Finalmente, utiliza la API de generación de texto de OpenAI para generar una respuesta basada en los documentos encontrados y lo agrega al chat.

- Para ejecutar estos archivos, necesitarás tener una cuenta de OpenAI y Azure. Coloca tus credenciales en un archivo .env y asegúrate de tener algunos archivos PDF en tu directorio de datos. 

## Variables de entorno

Las variables de entorno en el archivo `.env` estan referenciados en `.env.reference`. Estos incluyen:

| Variable de Entorno | Descripción |
| --- | --- |
| `SEARCH_SERVICE_NAME`   | El nombre del servicio de Azure Cognitive Search. |
| `SEARCH_SERVICE_KEY`    | La clave del servicio de Azure Cognitive Search. |
| `SEARCH_INDEX_NAME`     | El nombre del índice de Azure Cognitive Search. |
| `SEARCH_VECTOR_CONFIG_NAME` | El nombre de la configuración del vector de Azure Cognitive Search. |
| `SEARCH_SEMANTIC_CONFIG_NAME` | El nombre de la configuración semántica de Azure Cognitive Search. |
| `OPENAI_API_TYPE` | El tipo de API de OpenAI. |
| `OPENAI_API_BASE` | La URL base de la API de OpenAI. |
| `OPENAI_API_VERSION` | La versión de la API de OpenAI. |
| `OPENAI_API_KEY` | La clave de la API de OpenAI. |
| `OPENAI_EMBEDDING_MODEL` | El nombre del modelo de incrustación de OpenAI utilizado para generar vectores de incrustación. |
| `FILEPATH_TO_DATA` | La ruta al directorio que contiene los datos que se cargarán en Azure Cognitive Search.
|`FILEPATH_TO_INDEX_SCHEMA` | Especificar la ruta al archivo que contiene el esquema del índice para Azure Cognitive Search


## Requisitos

Para ejecutar los scripts de este proyecto, necesitarás:

- Credenciales Azure y servicio de Azure Cognitive Search configurado.
- Credenciales de API de OpenAI.
- Utilizar Python 3.10+.
- Instalar las bibliotecas de Python 

    `pip install requirement.txt`

- Documentos para cargar en Azure Cognitive Search. Los scripts actuales asumen que los documentos son archivos PDF, pero esto podría modificarse para admitir otros tipos de archivos.