# Routing

### Afegir rutes al projecte

#### 1. Afegir el mòdul de routing al projecte

```text
> ng g module app-routing
```

#### 2. Afegir el mòdul al fitxer `app.module.ts`

```text
@NgModule({
  imports: [
    BrowserModule,
    ...
    AppRoutingModule // CLI adds AppRoutingModule to the AppModule's imports array
    ],
  providers: [],
  bootstrap: [AppComponent]
})
```

#### 3. Definir les rutes a l'array Routes a`app-routing.module.ts`

```text
const routes: Routes = [
  { path: ''; component: LoginComponent},
  { path: 'first-component', component: FirstComponent },
  { path: 'second-component', component: SecondComponent },
];
```

**Exemple fitxer de rutes**

```text
const routes: Routes = [
  { path: '', component: PersonasComponent },
  { path: 'personas', component: PersonasComponent, children: [
     
     { path: 'agregar', component: FormularioComponent },
     // http://localhost:4200/personas/agregar
     
     // Ruta amb paràmetres
     { path: ':id', component: FormularioComponent }, 
     // http://localhost:4200/personas/1
     
  ] },
  { path: '**', component: ErrorComponent}
];
```

**Més informació:** [https://angular.io/guide/router](https://angular.io/guide/router)



