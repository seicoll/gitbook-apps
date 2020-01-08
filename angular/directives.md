# Directives

> El concepte de **directiva **està relacionat amb la modificació del DOM de la nostra pàgina.



## ngIf

```csharp
<p *ngIf="personaCreada; else sinPersona">{{agregarPersonaStatus}} con título {{tituloPersona}}</p>
<ng-template #sinPersona>
    <p>No se ha agregado ninguna persona.</p>
</ng-template>
```

## ngFor

```csharp
<div *ngFor="let persona of personas, let i = index">
    {{i+1}}: {{persona.nombre}} {{persona.apellido}}
</div>
```