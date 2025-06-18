# Pr-Final-Webscripping
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
