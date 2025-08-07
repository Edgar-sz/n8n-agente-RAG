# 🤖 Asistente de Investigación y Elaboración de Tesis con n8n

Este repositorio contiene dos flujos avanzados de automatización con **n8n** que implementan **agentes conversacionales inteligentes conectados a WhatsApp**. Ambos proyectos se construyeron como soluciones de **asistencia académica enriquecida**, capaces de interpretar texto, audio e imágenes, realizar consultas a una base de conocimientos vectorial y ofrecer respuestas personalizadas mediante inteligencia artificial.

---

## 🔁 Flujo 1: Vectorización de Libro Académico en Pinecone

Este es el flujo de preparación y carga de conocimiento académico. Procesa un **libro en PDF** sobre metodología de la investigación, lo divide por secciones y lo transforma en vectores que se almacenan en **Pinecone**, una base de datos vectorial. Este contenido vectorizado puede ser consultado posteriormente por el agente conversacional para dar respuestas fundamentadas.

### ✨ Funcionalidades

- 📄 **PDF Loader**: Carga y extrae el contenido completo del libro académico.  
- ✂️ **División en fragmentos**: Separa el texto en bloques lógicos de contenido.  
- 🧠 **OpenAI Embeddings**: Convierte cada fragmento en un vector numérico mediante modelos de lenguaje.  
- 📚 **Pinecone**: Almacena los vectores generados junto con metadatos clave como título, capítulo y sección.  
- 🔄 **Reprocesamiento automático**: Permite actualizar fácilmente el vector store al subir nuevos libros o materiales académicos.

---

## 🥗 Flujo 2: Agente Académico en WhatsApp

Este segundo flujo es un **asistente conversacional académico** diseñado para ayudar a estudiantes universitarios, tesistas e investigadores a través de WhatsApp. Está integrado con múltiples herramientas para interpretar preguntas complejas, realizar búsquedas vectoriales en el libro cargado y complementar con resultados de internet cuando sea necesario.

### ✨ Funcionalidades

- 📩 **WhatsApp**: Recibe y responde mensajes a través de la API de **Evolution**.  
- 🧠 **OpenAI**: Interpreta consultas en lenguaje natural, desde preguntas simples hasta temas metodológicos avanzados.  
- 🧠 **Think Tool (OpenAI)**: Para tareas que requieren razonamiento paso a paso (ej. redacción de objetivos específicos).  
- 🔊 **Transcripción de audio**: Detecta mensajes de voz y los convierte a texto automáticamente.  
- 🖼️ **Análisis de imágenes**: Recibe imágenes (como capturas de textos o esquemas) y devuelve una interpretación o resumen.  
- 🧾 **RAG con Pinecone**: Realiza búsquedas inteligentes dentro del libro vectorizado usando técnicas de recuperación aumentada.  
- 💬 **Redis**: Utilizado como sistema de cola de mensajes para manejar conversaciones extensas o fragmentadas.  
- 🌐 **SerpAPI**: Permite realizar búsquedas web en tiempo real cuando el contenido no está disponible en la base vectorial.

Este flujo puede responder sobre temas como:  
🔹 Formulación de problemas  
🔹 Objetivos y justificación  
🔹 Diseño metodológico  
🔹 Tipos de investigación  
🔹 Variables y técnicas de recolección  
🔹 Redacción y estructura de tesis  

---

## 🔐 Requisitos y credenciales

Para que estos flujos funcionen correctamente, se requiere la creación y configuración de cuentas en varios servicios:

- Una cuenta en **n8n**, ya sea instalada localmente o en una **VPS**.  
- Acceso a una API de WhatsApp como **Evolution API**, junto con su **token de autenticación**.  
- Una cuenta de **OpenAI**, con una **clave de API activa** para permitir generación de texto, embeddings, transcripción de audio y análisis de imágenes.  
- Una cuenta en **Pinecone**, para almacenar y consultar vectores del contenido académico.  
- Una instancia funcional de **Redis**, ya sea en el mismo servidor o como servicio externo, para manejar la cola de mensajes.  
- Una cuenta en **SerpAPI**, necesaria para realizar búsquedas web automatizadas desde el flujo.  

> ⚠️ **No se requiere instalar Luxon**, ya que está integrado en los nodos de expresiones de n8n.

Cada servicio requiere su propia configuración y autenticación (**API Keys**, **URLs**, **Tokens**, etc.), por lo que se recomienda revisar la documentación oficial de cada uno antes de ejecutar el flujo.

---

## ⚙️ Recomendaciones para la implementación

- Instala **n8n** en una **VPS** o tu entorno local.  
- Carga el archivo **.json** del flujo desde el editor de flujos.  
- Configura las **credenciales necesarias** en la sección de "Credenciales" de n8n.  
- Asegúrate de tener acceso a todas las **APIs y servicios mencionados**.  
- Para **Redis**, puedes usar una instancia en la nube o local.  
- Ajusta los **prompts y condiciones** según el tipo de investigación académica a la que apuntes.  
- Revisa que el índice de **Pinecone** esté correctamente configurado y que los vectores se hayan cargado satisfactoriamente.  

---

## 📎 Recursos en video

- [🎥 VIDEO: Conexión de WhatsApp con n8n](https://www.youtube.com/watch?v=4qG8TA_yMxI&t=116s)  
- [🎥 VIDEO: Creación de agente conversacional](https://www.youtube.com/watch?v=-T5i6wDOM2E)  
- [🎥 VIDEO: Creación buffer de mensajes](https://www.youtube.com/watch?v=HubhYIo4Iys&t=881s)  
- [🎥 VIDEO: Solución problema Redis](https://www.youtube.com/watch?v=YFJqf-utKxc)  
- [🎥 VIDEO: Vectorización de PDFs y sistema RAG con Pinecone](https://www.youtube.com/watch?v=UzzKxydTlNE&t=1103s)
