# Angular

> **Angular** is a TypeScript-based open-source web application framework led by the Angular Team at Google and by a community of individuals and corporations.

> **Angular** és un framework del costat client per desenvolupar aplicacions dinàmiques.

L'**arquitectura web client-servidor** es basa en que el client web fa peticions al servidor i el servidor respon amb una nova pàgina que es recarrega al navegador.

> **SPAs** (**_Single Page Applications_**) és una aplicació web que carrega inicialment la pàgina i el servidor només retorna dades o part de la pàgina que s'**_injecten_** a la mateixa pàgina. 

* La pàgina mai es recarrega.
* Millora l'experiència de l'usuari.
* Evitem tràfic perquè s'envia menys informació (només dades en format JSON).

**Avantatges**
* Empresa que hi ha darrere és Google.
* Temps curt d'aprenentatge.
* Optimització en el desenvolupament. Ràpid desenvolupament.
* Normalitza com estructurem el nostre software (js, html, css, etc…).

## Versions

La primera versió d'Angular s'anomenava **AngularJS**.

* **AngularJS**: 1.0 ... 1.7 

**AngularJS** es va reescriure per l'equip desenvolupador i es va passar a dir **Angular**.

* **Angular**: 2.0 ... 9.0

Aquest framework es sol actualitzar cada 6 mesos.

## Instal·lació

###Prerequisits:

Instal·lar [Node JS](https://nodejs.org/es/): Javascript del costat del servidor.

Instal·lant la última versió de **npm**.

```bash+theme:dark
npm install npm@latest -g    
```

###Step 1: Install the Angular CLI

Utilitzant `npm` (el gestor des paquets de NodeJs), instal·lem Angular **CLI (_Command Line Interface_)** de forma global (-g).

```bash+theme:dark
npm install -g @angular/cli
```

> **Alerta**: Cal executar-lo com a administrador.

### Step 2: Create a workspace and initial application

```bash+theme:dark
ng new my-app
```

### Step 3: Run the application

```bash+theme:dark
cd my-app
ng serve --open
```

The --open (or just -o) option automatically opens your browser to `http://localhost:4200/`.

**Més informació:**

* [Angular.io: Setting up the Local Environment and Workspace](https://angular.io/guide/setup-local)


## Estructura del projecte

Estructura mínima d'un projecte Angular:

```
|__ src
|    |_app
|    |   |__ app.component.ts
|    |   |__ app.component.html
|    |   |__ app.component.css
|    |__ index.html (SPA)
|    |__ main.ts
|    |__ styles.css
|__ package.json

```

* **package.json**: serveix per definir totes les dependències de l'aplicació. 
  * NPM buscarà aquestes dependències a internet per instal·lar-les.
* **main.ts**: Inicia l'aplicació (Bootstraping)
* **index.html**: Única pàgina de l'aplicació (SPAs) on injectarem codi html (templates)
* **app.component.ts**: component principal de l'aplicació. 
  * La nomenclatura és una convenció recomenable:	`nomComponent.component.js` 

## Creació de components

Els **components **són l'element bàsic en Angular.
* Quasi tot són components.
* Consisteixen en una agrupació de codi per ser reutilitzat.

**Crear un component amb CLI:**

```bash+theme:dark
ng generate component compoment-name
```

És equivalent fer:

```bash+theme:dark
ng g c compoment-name
```

Un component està format pel **Decorador **i la **Classe**:

**app.component.ts**
```javaScript
import { Component } from '@angular/core';

//Decorador
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
//Classe
export class AppComponent {
  title = 'First Angular App';
}

```

## Interpolació 

`{{ }}`

## Property binding

`[]= "" `

HMTL Propierty <-> Class propierty

## Event binding

`(click) = "onCrearElement()"`

## Two way binding

`[(ngModel)] = "nomPersona"`




   