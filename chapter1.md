# Com fer instal·lables les PWA

## L'arxiu Manifest

> L'arxiu **Manifest** permet informar al disposiu que la web és instal·lable.

Consisteix en un arxiu en format **json**.

## Propietats principals del arxiu Manifest

* **name**: nom de l'aplicació
* **short_name**: un cop instal·lada apareix a sota l'icona
* **start_url**: url de la pàgina d'inici
* **background-color:** color de fons de la pantalla mentre carrega l'aplicació (screen splash: pantalla amb color de fons i logo)
* **theme-color:** color de la barra superior de l'app
* **orientation (any|landscape|portrait):** amb les opcions **landscape** i **portrait** l'app no es canviarà d'orientació al girar el dispositiu.
* **display (standalone|browser)**: 
  * amb **browser** es veu la barra de navegació del navegador 
  * amb **standalone** la web es veu com si vos una app natiua
* **icons**: icones de l'aplicació per diferents resolucions
  * src
  * type
  * sizes
* **dir**
* **lang**
* description
* scope
* serviceworker
  * src
  * scope
* related_applications
* prefer_related_aplications
* screenshots

**Exemple Manifest:**

```
{
  "name": "Progressive Web App",
  "short_name": "PWA",
  "start_url": "/?utm_source=homescreen",
  "background-color": "#ffffff",
  "theme_color": "#ffffff",
  "orientation": "any",
  "display": "standalone",
  "icons": [
    {
      "src": "android-chrome-96x96.png",
      "sizes": "96x96",
      "type": "image/png"
    }
  ],
  "dir": "ltr",
  "lang": "es-ES",
  "description": "Una apliación web progresiva para el curso de AWP",
  "scope": "/",
  "serviceworker": {
    "src": "scripts/sw.js",
    "scope": "/"
  },
  "related_applications": [{
    "platform": "play",
    "url": "url/a/la/app",
    "id": "es.carherco.pwa"
  }],
  "prefer_related_applications": true,
  "screenshots": [
    {
      "src": ""
    },
    {
      "src": ""
    }
  ]

}
```

