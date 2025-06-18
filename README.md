# Proyectp Final Webscripping
## **Descripción**


Este proyecto es un Web Scrapper desarrollado en Python, estructurada utilizando los principios de Programación Orientada a Objetos (POO).

Actualmente, la aplicación cuenta con lo básico para hacer scraping de dos tipos de páginas:
WikiScraper: extrae párrafos relevantes de páginas tipo Wikipedia, filtrando por palabras clave proporcionadas por el usuario.

RetailScraper: busca productos en sitios de comercio electrónico (como MercadoLibre) cuyos nombres coincidan estrictamente con todas las palabras clave ingresadas.
La clase principal ScrapingApp actúa como controlador de la aplicación, pidiendo las palabras clave al usuario, inicializando los scrapers y ejecutando el proceso.

Aunque por ahora es un avance funcional, la intención es extender y mejorar el proyecto en el futuro.



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
