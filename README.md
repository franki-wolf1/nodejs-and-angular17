# nodejs-and-angular17
un paso a paso básico para crear el backend de una aplicación utilizando Angular para el frontend y Node.js para el backend. En este ejemplo, utilizaré Express.js como framework de servidor en Node.js y MongoDB como base de datos. Además, asumiré que ya tienes Node.js y npm instalados en tu sistema.

Paso 1: Inicializar el Proyecto Node.js
Crea un nuevo directorio para tu proyecto y abre una terminal en ese directorio.

Ejecuta el siguiente comando para inicializar un nuevo proyecto Node.js:

bash
Copy code
npm init -y
Instala Express.js para gestionar las rutas y la lógica del servidor:

bash
Copy code
npm install express
Paso 2: Configurar Express.js
Crea un archivo index.js en el directorio de tu proyecto.

Abre index.js y configura tu servidor Express básico:

javascript
Copy code
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.get('/', (req, res) => {
    res.send('¡Hola desde el servidor Express!');
});

app.listen(PORT, () => {
    console.log(`Servidor escuchando en el puerto ${PORT}`);
});
Paso 3: Implementar Rutas y Lógica del Servidor
Agrega rutas y lógica del servidor en index.js. Por ejemplo, podrías agregar rutas para manejar solicitudes relacionadas con usuarios:

javascript
Copy code
const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

// Rutas
app.get('/', (req, res) => {
    res.send('¡Hola desde el servidor Express!');
});

app.get('/api/usuarios', (req, res) => {
    // Lógica para obtener y devolver la lista de usuarios desde la base de datos
    res.json({ usuarios: [] });
});

// Agrega más rutas según sea necesario

app.listen(PORT, () => {
    console.log(`Servidor escuchando en el puerto ${PORT}`);
});
Paso 4: Conectar a la Base de Datos
Instala el módulo mongoose para conectarte a MongoDB:

bash
Copy code
npm install mongoose
En index.js, configura la conexión a MongoDB utilizando mongoose:

javascript
Copy code
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost:27017/nombre-de-tu-base-de-datos', {
    useNewUrlParser: true,
    useUnifiedTopology: true,
});

const db = mongoose.connection;

db.on('error', console.error.bind(console, 'Error de conexión a MongoDB:'));
db.once('open', () => {
    console.log('Conectado a MongoDB');
});
Paso 5: Configurar el Frontend con Angular
Crea un nuevo directorio para el frontend de tu aplicación.

En la terminal, navega al directorio del frontend y ejecuta el siguiente comando para crear un nuevo proyecto Angular:

bash
Copy code
ng new nombre-de-tu-proyecto-frontend
Sigue las instrucciones para configurar tu proyecto Angular.

Una vez que se haya creado el proyecto Angular, abre el archivo src/app/app.component.ts y realiza las modificaciones necesarias para consumir datos desde el backend.

Paso 6: Integrar Frontend y Backend
En el frontend, utiliza Angular para hacer solicitudes HTTP al backend. Por ejemplo, en app.component.ts:

typescript
Copy code
import { Component, OnInit } from '@angular/core';
import { HttpClient } from '@angular/common/http';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent implements OnInit {
  usuarios: any[] = [];

  constructor(private http: HttpClient) {}

  ngOnInit() {
    this.http.get<any[]>('http://localhost:3000/api/usuarios').subscribe(data => {
      this.usuarios = data.usuarios;
    });
  }
}
Asegúrate de tener HttpClientModule importado en tu módulo Angular y configurado en imports.

Ejecuta tanto el servidor Node.js como la aplicación Angular.

Con estos pasos, has creado un backend simple con Node.js y Express, conectado a MongoDB y configurado un frontend básico con Angular. Ten en cuenta que este es un ejemplo básico y la configuración real dependerá de los requisitos específicos de tu aplicación. Además, se recomienda implementar medidas de seguridad y considerar aspectos como la gestión de usuarios, autenticación y autorización.

<h3 align="center">
  
  ![header](https://firebasestorage.googleapis.com/v0/b/franki-briones.appspot.com/o/sofware%20developer%20fb.gif?alt=media&token=59c7e78f-508f-42ce-a94e-709d69210163) 
  
 # Welcome I'm Franki Briones !

</h3> 
<br></br>

<div>

<img align="right" width="400" alt="Shimarin" src="https://firebasestorage.googleapis.com/v0/b/franki-briones.appspot.com/o/dev%20metod.gif?alt=media&token=a3c328cf-ad9b-49f5-a45d-bb84b79f4fbe"/>

<h2> - / about me /</h2>
👨‍💻 Web Developer
<br></br>
🖥️ Creator of Desktop Systems
<br></br>
🔍 Researcher of New Technologies
<br></br>
☁️ Cloud Computing Enthusiast
<br></br>
💬 Ask me about Firebase, Python, Node.js, MongoDB, JS libraries, Java ...
<br></br>****
