# Digital Library Fullstack

Aplicación web fullstack para la gestión y consulta de una biblioteca digital, desarrollada con **Node.js**, **Express**, **MySQL**, **HTML**, **CSS** y **JavaScript**.

El proyecto permite registrar usuarios, iniciar sesión, consultar libros disponibles y acceder a un perfil de usuario mediante autenticación con JWT. La aplicación combina un backend con API REST y un frontend estático desarrollado con tecnologías web tradicionales.

---

## Descripción del proyecto

**Digital Library Fullstack** es una aplicación web orientada a la consulta y gestión básica de una biblioteca digital.

El sistema permite que los usuarios se registren, inicien sesión, accedan a un listado de libros y consulten información asociada a su perfil. El backend se encarga de exponer endpoints, conectarse con una base de datos MySQL, validar credenciales, generar tokens JWT y proteger rutas privadas.

Desde una mirada de portfolio, este proyecto demuestra conocimientos en desarrollo fullstack con Node.js, manejo de bases de datos relacionales, autenticación, consumo de APIs desde JavaScript y construcción de interfaces web con HTML, CSS y JavaScript vanilla.

---

## Objetivo

El objetivo principal del proyecto es construir una aplicación web funcional que represente el flujo básico de una biblioteca digital.

El sistema busca demostrar conocimientos en:

- Desarrollo backend con Node.js y Express.
- Creación de endpoints REST.
- Conexión con base de datos MySQL.
- Registro e inicio de sesión de usuarios.
- Hash de contraseñas.
- Autenticación con JWT.
- Protección de rutas privadas.
- Consumo de API desde el frontend.
- Manipulación del DOM con JavaScript.
- Persistencia de sesión mediante `localStorage`.
- Organización de un proyecto fullstack simple.

---

## Funcionalidades principales

### Backend

- API REST con Express.
- Conexión a MySQL mediante `mysql2`.
- Registro de usuarios.
- Inicio de sesión.
- Hash de contraseñas con bcrypt.
- Generación de tokens JWT.
- Middleware de autenticación.
- Consulta de perfil de usuario autenticado.
- Consulta de libros.
- Configuración de CORS.
- Servido de archivos estáticos del frontend.

### Frontend

- Página principal.
- Página de registro.
- Página de inicio de sesión.
- Página de perfil.
- Página de consulta/listado de libros.
- Formularios conectados con la API.
- Almacenamiento del token en `localStorage`.
- Consumo de endpoints mediante `fetch`.
- Manipulación dinámica del DOM.
- Estilos personalizados con CSS.

---

## Tecnologías utilizadas

### Backend

- Node.js
- Express
- MySQL
- mysql2
- bcrypt
- JSON Web Token
- CORS
- dotenv
- Nodemon

### Frontend

- HTML5
- CSS3
- JavaScript
- Fetch API
- LocalStorage

### Base de datos

- MySQL

---

## Arquitectura general

El proyecto está dividido en dos partes principales:

```txt
digital-library-fullstack/
├── backend/
└── frontend/
```

El backend expone una API REST y administra la lógica de autenticación, persistencia y consulta de datos.

El frontend consume la API mediante JavaScript y presenta las pantallas de registro, login, perfil y listado de libros.

---

## Estructura del proyecto

```txt
digital-library-fullstack/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── database.js
│   │   ├── controllers/
│   │   │   └── bibliotecaControllers.js
│   │   ├── middlewares/
│   │   │   └── authMiddleware.js
│   │   ├── routes/
│   │   │   └── bibliotecaRoutes.js
│   │   └── index.js
│   ├── package.json
│   └── package-lock.json
│
├── frontend/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   ├── app.js
│   │   ├── index2.js
│   │   ├── iniciarSesion.js
│   │   ├── libro.js
│   │   ├── perfil.js
│   │   └── registro.js
│   ├── pages/
│   │   └── img/
│   ├── index.html
│   ├── index2.html
│   ├── iniciarSesion.html
│   ├── perfil.html
│   └── registro.html
│
└── README.md
```

---

## Módulos principales

### Usuarios

El sistema permite registrar usuarios e iniciar sesión.

Incluye:

- Registro de usuario.
- Inicio de sesión.
- Validación de credenciales.
- Hash de contraseña.
- Generación de token JWT.
- Almacenamiento del token en el navegador.

---

### Autenticación

El backend utiliza JWT para proteger rutas privadas.

El token se envía desde el frontend en el header `Authorization` cuando el usuario accede a recursos protegidos.

---

### Perfil de usuario

El sistema permite consultar datos del usuario autenticado.

La información se obtiene desde la base de datos y se muestra en la vista de perfil.

---

### Libros

El sistema permite consultar un listado de libros almacenados en la base de datos.

Cada libro puede contener información como:

- Identificador.
- Título.
- Autor.
- Descripción.
- Fecha de publicación.

---

## Enfoque técnico

El backend sigue una estructura simple separada por responsabilidades:

```txt
Routes → Controllers → Database
```

Las rutas reciben las solicitudes HTTP, los controladores ejecutan la lógica correspondiente y la base de datos almacena usuarios y libros.

El frontend está construido con HTML, CSS y JavaScript, utilizando `fetch` para comunicarse con el backend.

---

## Seguridad

El proyecto incorpora prácticas básicas de seguridad:

- Hash de contraseñas con bcrypt.
- Autenticación mediante JWT.
- Protección de rutas privadas.
- Validación de credenciales.
- Manejo de token desde el frontend.

---

## Instalación y ejecución

El proyecto requiere ejecutar el backend y contar con una base de datos MySQL configurada.

### Requisitos previos

- Node.js
- npm
- MySQL
- Git

---

## Backend

Ingresar a la carpeta del backend:

```bash
cd backend
```

Instalar dependencias:

```bash
npm install
```

Crear un archivo `.env` con las variables necesarias:

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=biblioteca_cac
JWT_SECRET=your_jwt_secret
```

Ejecutar el servidor:

```bash
npm start
```

El backend quedará disponible en:

```txt
http://localhost:3000
```

---

## Base de datos

El proyecto utiliza una base de datos MySQL llamada:

```txt
biblioteca_cac
```

Tablas principales esperadas:

```txt
usuarios
libros
tokenInvalido
```

Ejemplo de campos esperados para usuarios:

```txt
id_usuario
nombre
apellido
dni
telefono
correo
contrasenia
```

Ejemplo de campos esperados para libros:

```txt
id_libro
titulo
autor
descripcion
fecha_publicacion
```

---

## Endpoints principales

```txt
POST   /api/biblioteca/registro
POST   /api/biblioteca/iniciarSesion
GET    /api/biblioteca/usuarios/me
GET    /api/biblioteca/libros
```

---

## Flujo básico de uso

1. El usuario ingresa al sitio.
2. Se registra mediante el formulario.
3. Inicia sesión con correo y contraseña.
4. El backend valida los datos.
5. El sistema genera un token JWT.
6. El frontend guarda el token en `localStorage`.
7. El usuario accede al listado de libros.
8. El usuario puede consultar su perfil.

---

## Buenas prácticas aplicadas

- Separación entre backend y frontend.
- Organización de rutas y controladores.
- Uso de variables de entorno sugeridas.
- Hash de contraseñas.
- Autenticación con JWT.
- Protección de rutas privadas.
- Consumo de API desde el frontend.
- Manipulación del DOM con JavaScript.
- Uso de `localStorage` para sesión.
- Estructura simple y entendible para mantenimiento.

---

## Posibles mejoras futuras

- Centralizar completamente la configuración de base de datos mediante variables de entorno.
- Corregir duplicación de rutas.
- Agregar validaciones más robustas en backend.
- Agregar validaciones visuales en frontend.
- Implementar logout con invalidación real de token.
- Agregar roles de usuario.
- Crear panel administrativo para libros.
- Permitir alta, edición y baja de libros.
- Agregar buscador de libros.
- Agregar filtros por autor, género o fecha.
- Mejorar diseño responsive.
- Agregar paginación.
- Agregar documentación Swagger.
- Agregar tests automatizados.
- Preparar deploy del backend y frontend.

---

## Estado del proyecto

Proyecto académico funcional, desarrollado como aplicación fullstack para una biblioteca digital.

El sistema se encuentra preparado para ser presentado como parte de un portfolio profesional, demostrando conocimientos en **Node.js**, **Express**, **MySQL**, autenticación con **JWT** y frontend con **HTML, CSS y JavaScript**.

---

## Autor

**Darío Villar**  
Analista Programador | Fullstack Developer
