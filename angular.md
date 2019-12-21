# Angular

> **Angular** is a TypeScript-based open-source web application framework led by the Angular Team at Google and by a community of individuals and corporations.

## Versions

La primera vesió d'Angular s'anomenava **AngularJS**.

* **AngularJS**: 1.0 ... 1.7 

**AngularJS** es va reescriure per l'equip desenvolupador i es va passar a dir **Angular**.

* **Angular**: 2.0 ... 9.0

Aquest framework es sol actualitzar cada 6 mesos.

## Instal·lació

###Prerequisits:

Instal·lar [Node JS](https://nodejs.org/es/): Javascript del costat del servidor.

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


   