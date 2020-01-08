# Directives

> El concepte de **directiva **està relacionat amb la modificació del DOM de la nostra pàgina.



## ngIf

```
<p *ngIf="personaCreada; else sinPersona">{{agregarPersonaStatus}} con título {{tituloPersona}}</p>
<ng-template #sinPersona>
    <p>No se ha agregado ninguna persona.</p>
</ng-template>
```

## ngFor