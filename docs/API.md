# API Documentation - Let's Translate

## Base URL
```
http://localhost:5000/api
```

## Autenticación

Todas las rutas protegidas requieren un JWT en el header:
```
Authorization: Bearer <token>
```

---

## 🔐 Endpoints de Autenticación

### Registro de Usuario
**POST** `/auth/register`

```json
{
  "email": "user@example.com",
  "password": "password123",
  "name": "John Doe"
}
```

**Response (201)**
```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "64a1b2c3d4e5f6g7h8i9",
    "email": "user@example.com",
    "name": "John Doe"
  }
}
```

---

### Login
**POST** `/auth/login`

```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response (200)**
```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "64a1b2c3d4e5f6g7h8i9",
    "email": "user@example.com",
    "name": "John Doe"
  }
}
```

---

### Logout
**POST** `/auth/logout`

Requiere autenticación ✓

**Response (200)**
```json
{
  "success": true,
  "message": "Sesión cerrada correctamente"
}
```

---

## 🌍 Endpoints de Traducción

### Realizar Traducción
**POST** `/translate`

Requiere autenticación ✓

```json
{
  "text": "Hola, ¿cómo estás?",
  "sourceLanguage": "es",
  "targetLanguage": "en"
}
```

**Response (200)**
```json
{
  "success": true,
  "translation": {
    "id": "64a1b2c3d4e5f6g7h8i9",
    "originalText": "Hola, ¿cómo estás?",
    "translatedText": "Hello, how are you?",
    "sourceLanguage": "es",
    "targetLanguage": "en",
    "createdAt": "2024-01-15T10:30:00Z"
  }
}
```

---

### Obtener Historial de Traducciones
**GET** `/translate/history?limit=10&offset=0`

Requiere autenticación ✓

**Response (200)**
```json
{
  "success": true,
  "history": [
    {
      "id": "64a1b2c3d4e5f6g7h8i9",
      "originalText": "Hola",
      "translatedText": "Hello",
      "sourceLanguage": "es",
      "targetLanguage": "en",
      "createdAt": "2024-01-15T10:30:00Z"
    }
  ],
  "total": 45,
  "limit": 10,
  "offset": 0
}
```

---

### Listar Idiomas Disponibles
**GET** `/languages`

No requiere autenticación

**Response (200)**
```json
{
  "success": true,
  "languages": [
    {
      "code": "es",
      "name": "Español",
      "nativeName": "Español"
    },
    {
      "code": "en",
      "name": "English",
      "nativeName": "English"
    },
    {
      "code": "fr",
      "name": "Français",
      "nativeName": "Français"
    }
  ]
}
```

---

## 👤 Endpoints de Usuarios

### Obtener Perfil
**GET** `/users/profile`

Requiere autenticación ✓

**Response (200)**
```json
{
  "success": true,
  "user": {
    "id": "64a1b2c3d4e5f6g7h8i9",
    "email": "user@example.com",
    "name": "John Doe",
    "createdAt": "2024-01-01T00:00:00Z"
  }
}
```

---

### Actualizar Perfil
**PUT** `/users/profile`

Requiere autenticación ✓

```json
{
  "name": "Jane Doe",
  "email": "jane@example.com"
}
```

**Response (200)**
```json
{
  "success": true,
  "user": {
    "id": "64a1b2c3d4e5f6g7h8i9",
    "email": "jane@example.com",
    "name": "Jane Doe"
  }
}
```

---

### Cambiar Contraseña
**POST** `/users/change-password`

Requiere autenticación ✓

```json
{
  "currentPassword": "oldpassword123",
  "newPassword": "newpassword123"
}
```

**Response (200)**
```json
{
  "success": true,
  "message": "Contraseña actualizada correctamente"
}
```

---

### Eliminar Cuenta
**DELETE** `/users/:id`

Requiere autenticación ✓

**Response (200)**
```json
{
  "success": true,
  "message": "Cuenta eliminada correctamente"
}
```

---

## ⚠️ Códigos de Error

| Código | Descripción |
|--------|-------------|
| 200 | OK - Solicitud exitosa |
| 201 | Created - Recurso creado |
| 400 | Bad Request - Datos inválidos |
| 401 | Unauthorized - Token inválido o no autenticado |
| 403 | Forbidden - Permisos insuficientes |
| 404 | Not Found - Recurso no encontrado |
| 409 | Conflict - Recurso ya existe |
| 500 | Internal Server Error - Error del servidor |

---

## 🧪 Ejemplo de Flujo Completo

```bash
# 1. Registrarse
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "user@example.com",
    "password": "password123",
    "name": "John Doe"
  }'

# 2. Obtener traducciones disponibles
curl http://localhost:5000/api/languages

# 3. Traducir texto
curl -X POST http://localhost:5000/api/translate \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "text": "Hola",
    "sourceLanguage": "es",
    "targetLanguage": "en"
  }'

# 4. Ver historial
curl http://localhost:5000/api/translate/history \
  -H "Authorization: Bearer <token>"
```
