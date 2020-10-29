# Com fer la PWA instal·lable

## L'arxiu Manifest

> L'arxiu **Manifest** permet informar al disposiu que la web és instal·lable.

Consisteix en un arxiu en format **json**.

## Propietats principals del arxiu Manifest

* **name**: nom de l'aplicació
* **short\_name**: un cop instal·lada apareix a sota l'icona
* **start\_url**: url de la pàgina d'inici
* **background-color:** color de fons de la pantalla mentre carrega l'aplicació \(screen splash: pantalla amb color de fons i logo\)
* **theme-color:** color de la barra superior de l'app
* **orientation \(any\|landscape\|portrait\):** amb les opcions **landscape** i **portrait** l'app no es canviarà d'orientació al girar el dispositiu.
* **display \(standalone\|browser\)**: 
  * amb **browser** es veu la barra de navegació del navegador 
  * amb **standalone** la web es veu com si vos una app natiua
* **icons**: icones de l'aplicació per diferents resolucions
  * src
  * type
  * sizes
* **dir\(ltr\)**: orientació del text \(ltr\)
* **lang**: llenguatge
* **description**
* scope
* **serviceworker**: registrar quin és el serviceworker de l'app
  * src
  * scope
* **related\_applications**: enllaç a l'app si està en algun marketplace.
* **prefer\_related\_aplications**: `true` si preferim que s'obri l'app natiua si existeix
* screenshots

## Exemple Manifest

```text
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

## Indicar el Manifest

En el `index.html` cal afegir:

```text
<link rel="manifest" href="manifest.json?v=1" />
```

## Generar un Manifest

[https://realfavicongenerator.net/](https://realfavicongenerator.net/)

Ens permet generar els icones de l'app i un **Manifest** base.

Si complim un sèrie de requeriments, el navegador mostrarà un **banner al usuari indicant que la web és instal·lable**.

Requeriments de Chrome: [https://developers.google.com/web/fundamentals/app-install-banners/\#criteria](https://developers.google.com/web/fundamentals/app-install-banners/#criteria)

## Exeples de PWAs

[https://pwa.rocks/](https://pwa.rocks/)

