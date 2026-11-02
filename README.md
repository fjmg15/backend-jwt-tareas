# Backend en Node.js + Express con Autenticación JWT

API REST desarrollada en **Node.js**, **Express** y **MongoDB (Mongoose)** que registra usuarios, inicia sesión generando un token JWT y ofrece un CRUD de tareas protegido con **Bearer Token**, en el que cada usuario solo puede ver, modificar y eliminar sus propias tareas.

## Instalación y Ejecución

1. Instalar dependencias:
   ```bash
   npm install
   ```
2. Configurar variables de entorno copiando `.env.example` a `.env` (`PORT`, `MONGO_URI`, `JWT_SECRET`).
3. Ejecutar el servidor:
   ```bash
   npm run server
   ```

## Endpoints de la API

| Método | Ruta | Descripción | ¿Requiere token? |
| :--- | :--- | :--- | :---: |
| POST | `/api/users` | Crear usuario (`crearUser`) | No |
| POST | `/api/users/login` | Iniciar sesión y devolver el JWT (`loginUser`) | No |
| GET | `/api/users/datos` | Datos del usuario dueño del token (`datosUser`) | Sí |
| GET | `/api/tareas` | Listar solo las tareas del usuario logueado (`getTareas`) | Sí |
| POST | `/api/tareas` | Crear una tarea asignada al usuario logueado (`createTareas`) | Sí |
| PUT | `/api/tareas/:id` | Modificar una tarea propia (`updateTareas`) | Sí |
| DELETE | `/api/tareas/:id` | Eliminar una tarea propia (`deleteTareas`) | Sí |
