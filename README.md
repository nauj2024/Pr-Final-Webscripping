# Proyectp Final Webscripping
## **Descripción**


Este proyecto es un Web Scrapper desarrollado en Python, estructurada utilizando los principios de Programación Orientada a Objetos (POO).

Actualmente, la aplicación cuenta con lo básico para hacer scraping de dos tipos de páginas:

* **WikiScraper**: extrae párrafos relevantes de páginas tipo Wikipedia, filtrando por palabras clave proporcionadas por el usuario.

* **RetailScraper**: busca productos en sitios de comercio electrónico (como MercadoLibre) cuyos nombres coincidan estrictamente con todas las palabras clave ingresadas.

La clase principal ScrapingApp actúa como controlador de la aplicación, pidiendo las palabras clave al usuario, inicializando los scrapers y ejecutando el proceso.

Aunque por ahora es un avance funcional, la intención es extenderlo y mejorarlo

### Explicación breve del codigo

WikiScraper

Se encarga de extraer párrafos relevantes de páginas tipo Wikipedia.

* Usa requests para obtener el HTML de cada URL.

* Usa BeautifulSoup para analizar el contenido y buscar etiquetas.

* Filtra los párrafos que contengan todas las palabras clave del usuario.

* Guarda los resultados en el archivo wiki_resultados.txt.

RetailScraper

Busca productos en sitios de comercio electrónico (ej. MercadoLibre).

* Extrae los nombres de los productos usando selectores CSS.

* Filtra aquellos que contengan todas las palabras clave.

* Guarda los productos encontrados en el archivo productos.txt.

ScrapingApp

Es la clase principal que controla la ejecución del programa.

* Pide al usuario las palabras clave.

* Inicializa los scrapers (WikiScraper y RetailScraper) con las URLs y palabras clave.

* Llama al método parse() de cada scraper para ejecutar el proceso.





```mermaid
classDiagram
    class ScrapingApp {
        -palabras: list
        -scrapers: list
        +__init__()
        +run()
    }

    class WikiScraper {
        -urls: list
        -palabras_clave: list
        +__init__(urls, palabras_clave)
        +fetch_content(url)
        +parse()
    }

    class RetailScraper {
        -urls: list
        -palabras_clave: list
        +__init__(urls, palabras_clave)
        +fetch_content(url)
        +parse()
    }

    ScrapingApp --> WikiScraper : utiliza
    ScrapingApp --> RetailScraper : utiliza
