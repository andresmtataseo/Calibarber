# Calibarber Frontend — Aplicación Web para Barberías

<p align="center">
  <img src="./logo.png" alt="Calibarber" width="180" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Angular-20.x-DD0031?logo=angular&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/RxJS-7.x-B7178C?logo=reactivex&logoColor=white" />
  <img src="https://img.shields.io/badge/Node.js-20%2B-339933?logo=nodedotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/HTML5-FF5722?logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/CSS3-2965F1?logo=css3&logoColor=white" />
</p>

Calibarber Frontend es la aplicación web en Angular que consume la API REST del backend. Hace parte del proyecto completo junto con el backend en Spring Boot: https://github.com/andresmtataseo/Calibarber-Backend.

## Tabla de Contenidos
- Descripción General
- Tecnologías Utilizadas
- Arquitectura y Módulos
- Funcionalidades Clave
- Configuración de Entorno
- Desarrollo
- Construcción
- Integración con el Backend

## Descripción General
Aplicación SPA (Single Page Application) construida con Angular CLI 20.x que permite a usuarios registrarse, iniciar sesión, gestionar perfiles, explorar barberías y servicios, programar citas y visualizar pagos e historial. Está diseñada para integrarse de forma segura y eficiente con la API de Calibarber Backend.

## Tecnologías Utilizadas
- Angular CLI 20.1.3
- TypeScript
- RxJS
- HTML/CSS
- Herramientas de build y scripts personalizados (`build-production.js`, `load-env.js`)

## Arquitectura y Módulos
Estructura modular por características (`feature-based`), alineada con el backend:
- `features/auth`: autenticación (sign-in, sign-up, change-password)
- `features/user`: gestión de usuarios y perfiles
- `features/barbershop`: exploración y gestión de barberías
- `features/barber`: disponibilidad y especialidades de barberos
- `features/service`: catálogo y detalles de servicios
- `features/appointment`: creación, cancelación y reprogramación de citas
- `features/payment`: registro y visualización de pagos
- `core`: configuración, interceptores, guards, servicios base y tipos
- `shared`: componentes, pipes, directivas, modelos y utilidades reutilizables

## Funcionalidades Clave
- Autenticación JWT con persistencia de sesión
- Protección de rutas con guards e interceptores
- Gestión de usuarios (perfil, roles, activación/desactivación)
- Búsqueda y filtrado de barberías y servicios
- Programación de citas con validaciones
- Manejo de estados de carga, error y vacíos
- Navegación con rutas modulares y lazy loading

## Configuración de Entorno
Usa variables de entorno para apuntar al backend y otros ajustes.

Archivos relevantes:
- `.env.example`: plantilla de variables
- `src/environments/environment.ts`: configuración por ambiente

Ejemplo de `.env`:
```
API_BASE_URL=http://localhost:8080/api/v1
APP_NAME=Calibarber
```

Ajusta `API_BASE_URL` según tu entorno y habilita CORS en el backend si es necesario.

## Desarrollo
Instalación y servidor de desarrollo:
```bash
npm install
ng serve
```

Accede a `http://localhost:4200/`. La aplicación recarga automáticamente ante cambios.

## Construcción
Genera build de producción optimizada:
```bash
ng build
```
Los artefactos quedan en `dist/`. Puedes usar `build-production.js` si tu flujo lo requiere.

## Integración con el Backend
- Backend del proyecto: https://github.com/andresmtataseo/Calibarber-Backend
- Autenticación: encabezado `Authorization: Bearer <token>` para endpoints protegidos
- Rutas y contratos: mantener consistencia con la documentación Swagger del backend
- Errores: interceptores capturan respuestas HTTP y muestran mensajes adecuados
