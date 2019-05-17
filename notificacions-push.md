# Enviar notificacions 

## Notificacions vs Notificacion push

**Notificacions**

* Consisteix en mostrar un Toast a la pantalla.
* Només funcionen mentre l'usuari està utilitzant l'app.

**Notificacions push**

* Funcionen encara que l'usuari no estigui utilitzant l'app

## Notificacions push

Poden ser persistents o no persistents.

### Notificacions push no persistents

No estan associades a un Service Worker.

Els navegadors que soporten notificacions push disposen d'un classe `Notification`.

```js
// Solicitar permiso al cargar la página
document.addEventListener('DOMContentLoaded', function () {
  if (!Notification) {
    alert('Tu navegador no soporta notificaciones'); 
    return;
  }
  
  if (Notification.permission === 'granted') {
    mostrarNotificacion();
  } 

  if (Notification.permission !== "granted")
    Notification.requestPermission().then( p => {
      if(p === 'granted') mostrarNotificacion();
    });
});

//Mostrar la notificació
function mostrarNotificacion() {
    var notification = new Notification('Título de la notificación', {
      icon: './logo.jpg',
      body: "Este es el cuerpo de la notificación",
    });

    notification.onclick = function () {
      window.open("https://openwebinars.net/");      
    };

    notification.close();
  }
}```

### Notificacions push persistents

* Estàs associades a un Service Worker.
* Tenen unes accions associades que podrà fer l'usuari.

```js
if (Notification.permission === 'granted') {
  mostrarNotificacion();
} 

if (Notification.permission !== 'denied') {
  Notification.requestPermission().then( p => {
    if(p === 'granted') mostrarNotificacion();
  });
} 

function mostrarNotificacion() {
  self.registration.showNotification('Título de la notificación',{
    body: 'Texto del notificación',
    badge: '',
    icon: '',
    image: '',
    tag: 'etiqueta',
    renotify: false,
    data: {  },
    requireInteraction: false,
    actions: [{
        action: 'identificador',
        title: 'Action Title',
        icon: 'path/icono'
    }],
    silent: false,
    sound: '/path/to/adiofile',
    vibrate: [200, 100, 200],
    dir: 'ltr',
    lang: 'es-ES',
    timestamp: Date.now(),
  });

  self.addEventListener('notificationclick', evento => {
    if(!evento.action){
      console.log('El usuario hizo click en el body');
      return;
    }
    switch(evento.action) {
      case 'view':
        //...
        break;
      case 'buy':
        //...
        break;
      default: 
        console.warn(`${evento.action} clicked`);
        break;
    }
  });

  self.addEventListener('notificationclose', evento => {
    console.log('El usuario ha cerrado la notificación con la x');
  });

  
}
```


