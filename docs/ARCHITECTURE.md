# Arquitectura de Let's Translate

## 🏗️ Descripción General

Let's Translate utiliza una arquitectura moderna de tres capas:
- **Frontend**: React.js con TypeScript
- **Backend**: Node.js + Express.js
- **Database**: MongoDB

## 📊 Diagrama de Arquitectura

```
┌─────────────┐
│  Frontend   │ (React + TypeScript)
│  (Cliente)  │
└──────┬──────┘
       │ HTTP/REST
       ↓
┌─────────────────────────────────────┐
│         Backend API                 │
│  (Express.js + Node.js)             │
│  - Authentication                   │
│  - Translation Logic                │
│  - User Management                  │
└──────┬──────────────────────────────┘
       │ MongoDB Driver
       ↓
┌──────────────────────┐
│   MongoDB Database   │
│   - Users            │
│   - Translations     │
│   - History          │
└──────────────────────┘
```

## 🔄 Flujo de Traducción

1. Usuario escribe texto en el campo de entrada
2. Frontend envía petición POST a `/api/translate`
3. Backend recibe la petición y valida el token JWT
4. Backend envía la petición a la API de traducción (Google Translate / DeepL)
5. Backend recibe la respuesta y la guarda en MongoDB
6. Backend envía el resultado al frontend
7. Frontend muestra la traducción

## 📦 Componentes Principales

### Frontend
- **App.tsx**: Componente raíz
- **TranslatorPage**: Página principal de traducción
- **LanguageSelector**: Selector de idiomas
- **TranslationDisplay**: Mostrador de resultados
- **HistoryPanel**: Panel de historial

### Backend
- **authController**: Maneja autenticación y registro
- **translationController**: Maneja las traducciones
- **userController**: Maneja el perfil de usuario
- **authMiddleware**: Valida tokens JWT
- **Translation Model**: Esquema MongoDB para traducciones
- **User Model**: Esquema MongoDB para usuarios

## 🔐 Seguridad

- **JWT**: Autenticación basada en tokens
- **CORS**: Control de acceso entre dominios
- **Helmet**: Headers de seguridad HTTP
- **Bcrypt**: Hash de contraseñas
- **Rate Limiting**: Límite de peticiones

## 🚀 Escalabilidad

- **Caché de Reducciones**: Para traducciones frecuentes
- **Queue de Trabajos**: Para traducciones en lote
- **Load Balancing**: Múltiples instancias del backend
- **CDN**: Para assets estáticos del frontend

## 🔄 Ciclo de Vida de la Solicitud

```
Cliente                Backend                 MongoDB
  │                      │                        │
  ├─ POST /translate ────→│                        │
  │                      ├─ Validar token        │
  │                      ├─ Consultar cache      │
  │                      ├─ Llamar API externa   │
  │                      ├─ Guardar resultado ───→│
  │                      │                        │
  │  ← Respuesta JSON ────┤                        │
  │                      │                        │
```
