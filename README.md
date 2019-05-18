<p align="center">
  <h1 align="center">AngularFire</h1>
  <p align="center">La biblioteca oficial de Firebase y Angular.</p>
</p>

[![Build Status](https://travis-ci.org/angular/angularfire2.svg?branch=master)](https://travis-ci.org/angular/angularfire2) [![Join the chat at https://gitter.im/angular/angularfire2](https://badges.gitter.im/angular/angularfire2.svg)](https://gitter.im/angular/angularfire2?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## ¿Qué es AngularFire?

- **Basado en observables** -  Use el poder de RxJS, Angular y Firebase..
- **Enlaces en tiempo real** - Sincronizar datos en tiempo real.
- **Autenticación** - Inicie sesión con una variedad de proveedores y monitoree el estado de autenticación.
- **Datos sin conexión** - Almacene los datos sin conexión automáticamente con AngularFirestore.
- **Procesamiento del lado del servidor** - Genere HTML estático para mejorar el rendimiento percibido o crear sitios estáticos.
- **Amigable con ngrx** - Se integra con ngrx mediante las API basadas en acción de AngularFire.
- **Administre datos binarios** - cargue, descargue y elimine archivos binarios como imágenes, videos y otros blobs.
- **Código del servidor de llamadas** - Llame directamente a las funciones de la nube sin servidor con el contexto del usuario automáticamente pasado.
- **Notificaciones push** - Regístrese y escuche las notificaciones push
- **Modular** - incluya solo lo que se necesita. Ningún paquete de AngularFire está por encima de 3kb con la mayoría por debajo de 2kb (gzipped).

#### Enlaces rápidos
[Contribuyendo](CONTRIBUTING.md)

[Plantilla Stackblitz](https://stackblitz.com/edit/angular-1iment) - Recuerde establecer su configuración de Firebase en `app/app.module.ts`.

[¿Actualizando a v5.0? Echa un vistazo a nuestra guía.](docs/version-5-upgrade.md)

**¿Tienes problemas?** Obtenga ayuda sobre la [Lista de correo de Firebase](https://groups.google.com/forum/#!forum/firebase-talk) (oficialmente compatible), la [Comunidad de Firebase Slack](https://firebase.community/) (busque la sala `#angularfire2`), [Gitter](https://gitter.im/angular/angularfire2), or [Stack Overflow](https://stackoverflow.com/questions/tagged/angularfire2).

## Instalar

```bash
npm install firebase @angular/fire --save
```

## Ejemplo de uso:

```ts
import { Component } from '@angular/core';
import { AngularFirestore } from '@angular/fire/firestore';
import { Observable } from 'rxjs';

@Component({
  selector: 'app-root',
  template: `
  <ul>
    <li *ngFor="let item of items | async">
      {{ item.name }}
    </li>
  </ul>
  `
})
export class MyApp {
  items: Observable<any[]>;
  constructor(db: AngularFirestore) {
    this.items = db.collection('items').valueChanges();
  }
}
```

## Guía del desarrollador

### Empezando

- [Instalación y configuración](docs/install-and-setup.md)

### Interactuando con su(s) base(s) de datos.

Firebase ofrece dos soluciones de base de datos accesibles desde el cliente y basadas en la nube que admiten la sincronización de datos en tiempo real. [Conozca las diferencias entre ellos en la Documentación de Firebase .](https://firebase.google.com/docs/firestore/rtdb-vs-firestore).

#### Cloud Firestore

> `AngularFirestore` le permite trabajar con Cloud Firestore, la nueva base de datos principal para el desarrollo de aplicaciones móviles. Mejora los éxitos de Realtime Database con un nuevo modelo de datos más intuitivo. Cloud Firestore también cuenta con consultas más ricas y rápidas y escalas mejor que Realtime Database.

- [Documentos](docs/firestore/documents.md)
- [Colecciones](docs/firestore/collections.md)
- [Consultando Colecciones](docs/firestore/querying-collections.md)
- [Datos fuera de línea](docs/firestore/offline-data.md)

#### Base de datos en tiempo real

> `AngularFireDatabase` le permite trabajar con la base de datos en tiempo real, la base de datos original de Firebase. Es una solución eficiente de baja latencia para aplicaciones móviles que requieren estados sincronizados en todos los clientes en tiempo real.

- [Objetos](docs/rtdb/objects.md)
- [Listas](docs/rtdb/lists.md)
- [Consultando listas](docs/rtdb/querying-lists.md)

### Autenticar usuarios

- [Comenzando con la autenticación Firebase](docs/auth/getting-started.md)

### Subir archivos
- [Comenzando con el almacenamiento en la nube](docs/storage/storage.md)

### Enviar notificaciones push
- [Comenzando con la mensajería de Firebase](docs/messaging/messaging.md)

### Llamar directamente a las funciones de la nube
- [Primeros pasos con funciones callables](docs/functions/functions.md)

### Desplegando su aplicación

> Firebase Hosting es un alojamiento de contenido web de nivel de producción para desarrolladores. Con Hosting, puede implementar rápida y fácilmente aplicaciones web y contenido estático en una red de entrega de contenido global (CDN) con un solo comando.

- [Despliegue su aplicación Angular en Firebase Hosting](docs/deploying-angularfire-to-firebase.md)

#### Representación del lado del servidor

>Angular Universal es una tecnología que le permite ejecutar su aplicación Angular en un servidor. Esto le permite generar su HTML en un proceso llamado representación del lado del servidor (SSR). Angularfire es compatible con la representación del lado del servidor; lo que le permite aprovechar las ventajas de la optimización del motor de búsqueda, las vistas previas de los enlaces, las mejoras de rendimiento otorgadas por la tecnología y mucho más. [Aprende más sobre Angular Universal .](https://angular.io/guide/universal).

- [Empezando con Angular Universal](docs/universal/getting-started.md)
- [Despliegue de su aplicación Universal en Cloud Functions para Firebase](docs/universal/cloud-functions.md)
- [Pretender su aplicación universal](docs/universal/prerendering.md)

### Ionic

- [Instalación y configuración con Ionic CLI](docs/ionic/cli.md)
- [Usando AngularFire con Ionic 2](docs/ionic/v2.md)
- [Usando AngularFire con Ionic 3](docs/ionic/v3.md)
