# 🚌 Sistema de Gestión de Rutas y Transporte – LACOMBI

<img src="https://lacombi.vercel.app/combi-uees-logo.png" width="200" alt="Logo del proyecto">


## 📌 Descripción General

Este proyecto es una plataforma completa para la gestión de rutas de transporte, diseñada para tres tipos de usuarios:
- Administrador
- Motorista
- Pasajero (no autenticado)

La aplicación permite administrar:

- Rutas
- Horarios de ruta
- Viajes
- Motoristas
- Anuncios y comentarios
- Autenticación con roles

El sistema está compuesto por:

1. Frontend: React + Vite
2. Backend: Laravel 11 + Sanctum + Spatie Permission
3. Base de Datos: MySQL
4. Documentación automática: Swagger (OpenAPI)
5. Deploy: Railway (db), Render (backend), Vercel (frontend)


## 🎨 Frontend – React

![Frontend](https://lacombi.vercel.app/anuncios.png)

El frontend está construido con React + Vite, usando:
- React Router
- Axios para consumir la API
- Context/Auth Provider
- Bootstrap

### Funcionalidades Principales

#### 👥 Usuario General (sin login)
- Ver rutas disponibles
- Ver horarios por ruta
- Ver anuncios
- Comentar anuncios
- Crear una solicitud de viaje (POST /viajes)

![Invitado](https://lacombi.vercel.app/rutas.png)

#### 👷 Motorista
- Ver viajes asignados
- Actualizar estado de un viaje (ej. completado)
- Eliminar un viaje

![Motorista](https://lacombi.vercel.app/motorista.png)

#### 🛠 Administrador
- CRUD de rutas
- CRUD de horarios
- CRUD de motoristas/usuarios
- CRUD de anuncios

![Admin](https://lacombi.vercel.app/admin.png)


## ⚙️ Backend – Laravel (API REST)

El backend está construido en Laravel 11, implementando:
- Sanctum → Autenticación por tokens
- Spatie Permissions → Control de roles (administrador, motorista)
- Resource Controllers → Endpoints RESTful
- Swagger → Documentación pública en /api/documentation

![Backend](https://lacombi.vercel.app/backend.png)

## 🔐 Autenticación

![Autenticación](https://lacombi.vercel.app/login.png)

La autenticación se realiza mediante:
POST /auth/login
Retorna un token de Sanctum.

Rutas protegidas usan:
middleware: auth:sanctum
middleware: role:administrador | motorista

Si el usuario intenta entrar sin token:
GET /token → { "message": "Necesitas un token" }


## 🗄️ Base de Datos (Resumen)

![DB](https://lacombi.vercel.app/database.png)

### Tablas principales:
- users
- rutas
- horarios
- viajes
- anuncios
- comentarios

### Tablas de roles (Spatie):
- roles
- permissions
- role_has_permissions
- model_has_roles


## 🚀 Deploy

Usado en Railway:
- PHP 8.x
- Laravel 11
- MySQL
- Deploy con Dockerfile y entrypoint personalizado
- Port 8000 expuesto usando php artisan serve


## 🌐 Enlaces 

- API → https://la-combi-backend.onrender.com
- LACOMBI → https://lacombi.vercel.app/


## 👥 Creadores

1. Josué Mauricio → https://github.com/JosuMelara21
2. Luis Martínez → https://github.com/BlckXI
3. Steven Trujillo → https://github.com/imTrujillo

