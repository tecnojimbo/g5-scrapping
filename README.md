# g5-scrapping
Practica 2 Tratamiento de datos

# Web Scrapping: Historial de Equipos de Hockey 🏒

Este proyecto automatiza la extracción de datos históricos de equipos de hockey desde la web. El proceso incluye la navegación por múltiples páginas, la limpieza de datos con **Pandas** y el almacenamiento de la información tanto en formato plano (**CSV**) como en una base de datos relacional (**SQLite**).

## 📌 Descripción del Proyecto

El objetivo es consolidar estadísticas de rendimiento de diversos equipos (victorias, derrotas, goles a favor y en contra) a lo largo de diferentes años. Este proyecto forma parte de las actividades de procesamiento de datos del **Grupo 5**.

## 📸 Capturas de Ejecución

Para que el proyecto funcione correctamente, asegúrate de que las capturas estén en la carpeta `imagenes/`.

![Instalación d librerías ](img1.png)

![Ejecución de scrapping de 24 pag. ](img2.png)

![Proceso finalizado ](img3.png)

![Tabla ](img4.png)

![Evidencia de la tabla sqlite ](img6.png)
 


Proceso de scrapping y generación de DataFrames en el entorno de desarrollo.*

Estructura final de los datos procesados.*

## 📂 Estructura de Archivos

* `g5_scrapping.ipynb`: Notebook de Jupyter con la lógica de extracción (Scrapping), transformación (ETL) y carga de datos.
* `historial_hockey_master.csv`: Archivo de salida con los datos limpios listo para análisis en Excel o Power BI.
* `historial_hockey_master.db`: Base de datos SQLite que contiene la tabla con todo el histórico extraído.
* Se agrega recursos visuales para la documentación.

## 🛠️ Tecnologías Utilizadas

* **Python 3.13**: Lenguaje base del proyecto.
* **Pandas**: Biblioteca principal para la manipulación y estructuración de datos en DataFrames.
* **BeautifulSoup4 / Requests**: Herramientas para el análisis de HTML y peticiones web.
* **SQLite3**: Motor de base de datos ligero para el almacenamiento persistente.
* **Visual Studio Code**: Entorno de desarrollo (IDE) utilizado.

## 🚀 Cómo Empezar

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/tecnojimbo/g5-scrapping.git](https://github.com/tecnojimbo/g5-scrapping.git)
    ```
2.  **Instalar las dependencias necesarias:**
    ```bash
    pip install pandas beautifulsoup4 requests
    ```
3.  **Ejecutar el Notebook:**
    Abre `g5_scrapping.ipynb` y ejecuta las celdas en orden para realizar una nueva extracción de datos.

## 👥 Autores - Grupo 5

* **Sixto Encalada** (Sencalada)
* **Yordhan Guerrón** (Yguerron)
* **Jimmy Anzules** (Janzules)

---
Proyecto desarrollado para la gestión y tratamiento de datos técnicos.

# Preguntas de Retroalimentación -  G5

# 2.	¿Cómo podría un atacante manipular el contenido de la página web origen para contaminar el dataset generado, y qué consecuencias tendría esto al utilizar esos datos en herramientas como Excel o Power BI?

Un atacante podría manipular el contenido de la página web origen alterando los datos que posteriormente son recolectados por procesos de scraping. Esto puede lograrse si el atacante tiene control sobre el sitio o mediante vulnerabilidades como ataques XSS (Cross-Site Scripting), permitiéndole inyectar contenido malicioso en los campos que luego serán procesados.

# Existen diversas formas de contaminar el dataset:
El atacante puede insertar valores que comiencen con símbolos como =, +, - o @. Por ejemplo, un campo podría contener una expresión que, al abrirse en herramientas como Microsoft Excel, sea interpretada como una fórmula y potencialmente ejecute comandos no deseados. 
Si el archivo generado utiliza comas como separadores y no se escapan correctamente los valores, un atacante puede insertar comas dentro de los campos, provocando desalineación de columnas y pérdida de integridad en el dataset. 
La inclusión de caracteres Unicode no visibles o saltos de línea puede afectar el procesamiento de datos, rompiendo scripts de limpieza o generando errores en herramientas de análisis. 

# Las consecuencias de utilizar estos datos contaminados en herramientas como Microsoft Excel o Microsoft Power BI pueden ser significativas:
En Excel, las celdas interpretadas como fórmulas pueden ejecutar acciones inesperadas, comprometiendo la seguridad del sistema del usuario. 
En Power BI, la presencia de datos inconsistentes o tipos incorrectos puede generar errores en cálculos, afectar métricas o excluir registros sin advertencia. 
La introducción de valores extremos o manipulados puede distorsionar indicadores clave, llevando a conclusiones incorrectas y decisiones basadas en información no confiable. 
Para mitigar estos riesgos, es fundamental implementar procesos de validación y sanitización de datos antes de su almacenamiento o análisis. Esto incluye limpiar caracteres sospechosos, validar tipos de datos y asegurar que la información provenga de fuentes confiables.
Si no se controla la integridad de los datos desde el origen, todo el proceso de análisis puede verse comprometido, afectando tanto la seguridad como la calidad de la información utilizada para la toma de decisiones.




