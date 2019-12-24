# Binding en Angular


> El **Binding** permet enllaçar les dades amb la vista (HTML) fent actualitzar la pàgina.

Cada vegada que canviï el model també es canviarà la vista.

En Angular hi ha diversos **tipus de binding**:

* Del model a la vista --> `[]`
* De la vista al model --> `()`
* Bidireccional o en dos sentits --> `[()]`

## Interpolació 
 En Angular, el que es col·loca entre les dobles claus són anomenades expressions. 

Angular les avaluarà abans de bolcar el resultat dins el template.

`{{ 1+ 1 }}`

`{{ ! valorBolea }}`

Una expressió pot ser una cosa tan simple com una **propietat del component.**

`{{ nomPropietat }}`

## Property binding

> El **property binding** serveix per assignar un valor a una propietat d'un element d'un template.

Connectem una **propietat HTML** amb una **propietat de la Classe** que implementa el component:

**HMTL Propierty <---> Class propierty**

`<img [src]="rutaImatge">`

`<button [disabled]="estatBoto">Estic activat o desactivat</button>`

Al posar els claudàtors, els atributs HTML deixen de ser atributs de l'HTML per passar a ser propietats del template d'Angular.

> Si la propietat del component canvia, actualitza la pàgina (el DOM).

## Event binding

> L'**esdeveniment** es col·loca entre parèntesi i després cal assignar-li una sentència a executar (_**statement**_) com a resposta a aquest esdeveniment.

`(click) = "processarEvent($event)"`

* L'objecte `$event`ens ofereix informació sobre l'esdeveniment que s'acaba de produir.

**Exemples d'altres events:**

* `<div (mouseover)="call()">`
* `<input (blur)="call()">`
* `<input (focus)="call()">`
* `<input type="text" (keydown)="call()">`
* `<form (submit)="call()">`

**Events amb tecles:**

```csharp
//Vista
<input type="text" (keydown)="showKey($event)">

//Model
showKey(event){
   alert(event.keyCode);
}
```

## Two way binding

> En el **two way binding** (a dos sentits) la informació flueix en tots dos sentits, des del model a la vista i des de la vista a el model.

S'utilitza en els **formularis** i s''expressa entre claudàtors i parèntesis. 

`[(ngModel)] = "nomPersona"`

`<input type="text" [(ngModel)]="nomPersona">`

Per utilitzar-lo és necessari importar `FormModule`

**angular.js**
```csharp
importem FormModule

import { FormsModule } from '@angular/forms';
...
...
@NgModule({
  imports: [ BrowserModule, FormsModule ],
...
```

## Resum

**Flux de la informació de la vista al model i del model a la vista:**

![](/assets/angular-binding.png)


