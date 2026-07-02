# Let's Translate - Aplicación de Traducción en Tiempo Real

## 🎯 Descripción

Let's Translate es una aplicación web moderna diseñada para estudiantes y personas extranjeras que desean traducir texto en tiempo real. La aplicación proporciona traducciones precisas y rápidas entre múltiples idiomas.

## ✨ Características Principales

- **Traducción en Tiempo Real**: Traduce mientras escribes
- **Múltiples Idiomas**: Soporta 50+ idiomas
- **Interfaz Intuitiva**: Diseño limpio y fácil de usar
- **Historial de Traducciones**: Guarda tus traducciones recientes
- **Pronunciación**: Escucha la pronunciación correcta
- **Offline Mode**: Funciona sin conexión a internet (limitado)
- **Responsive Design**: Compatible con dispositivos móviles y de escritorio

## 🛠️ Tecnologías

- **Frontend**: React.js, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Translation API**: Google Translate API / DeepL API
- **Authentication**: JWT, OAuth 2.0

## 📋 Requisitos Previos

- Node.js v16+
- npm o yarn
- MongoDB
- Variables de entorno configuradas

## 🚀 Instalación

### 1. Clonar el Repositorio
```bash
git clone https://github.com/detomasoc-dot/let-s-translate-.git
cd let-s-translate-
```

### 2. Instalar Dependencias

**Frontend:**
```bash
cd frontend
npm install
```

**Backend:**
```bash
cd backend
npm install
```

### 3. Configurar Variables de Entorno

Crea archivos `.env` en las carpetas `frontend` y `backend`:

**Backend `.env`:**
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/lets-translate
JWT_SECRET=tu_clave_secreta
GOOGLE_TRANSLATE_API_KEY=tu_api_key
NODE_ENV=development
```

**Frontend `.env.local`:**
```
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENVIRONMENT=development
```

### 4. Ejecutar la Aplicación

**Backend:**
```bash
cd backend
npm run dev
```

**Frontend (en otra terminal):**
```bash
cd frontend
npm start
```

La aplicación estará disponible en `http://localhost:3000`

## 📁 Estructura del Proyecto

```
let-s-translate-/
├── frontend/                 # Aplicación React
│   ├── src/
│   │   ├── components/      # Componentes reutilizables
│   │   ├── pages/           # Páginas principales
│   │   ├── services/        # Servicios API
│   │   ├── context/         # Context API
│   │   ├── hooks/           # Custom hooks
│   │   ├── styles/          # Estilos globales
│   │   └── App.tsx
│   ├── public/
│   └── package.json
├── backend/                  # Servidor Express
│   ├── src/
│   │   ├── controllers/     # Controladores
│   │   ├── routes/          # Rutas API
│   │   ├── models/          # Modelos MongoDB
│   │   ├── middleware/      # Middleware
│   │   ├── services/        # Lógica de negocio
│   │   └── server.ts
│   ├── .env
│   └── package.json
├── docs/                     # Documentación
├── .gitignore
└── README.md
```

## 🔗 API Endpoints

### Autenticación
- `POST /api/auth/register` - Registrar usuario
- `POST /api/auth/login` - Iniciar sesión
- `POST /api/auth/logout` - Cerrar sesión

### Traducción
- `POST /api/translate` - Realizar traducción
- `GET /api/translate/history` - Obtener historial
- `GET /api/languages` - Listar idiomas disponibles

### Usuarios
- `GET /api/users/profile` - Obtener perfil
- `PUT /api/users/profile` - Actualizar perfil
- `DELETE /api/users/:id` - Eliminar usuario

## 🎨 Diseño

- **Color Primario**: #3B82F6 (Azul)
- **Color Secundario**: #10B981 (Verde)
- **Fondo**: #F3F4F6 (Gris claro)
- **Tipografía**: Segoe UI, Roboto, sans-serif

## 🧪 Testing

```bash
# Frontend
cd frontend
npm test

# Backend
cd backend
npm test
```

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor:
1. Fork el proyecto
2. Crea una rama para tu característica (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📝 Licencia

Este proyecto está bajo la licencia MIT. Ver `LICENSE` para más detalles.

## 📧 Contacto

Para preguntas o sugerencias, contáctanos en: info@letstranslate.com

## 🐛 Reporte de Bugs

Si encuentras un bug, por favor abre un issue con:
- Descripción del problema
- Pasos para reproducirlo
- Comportamiento esperado vs actual
- Screenshots (si aplica)

---

**Hecho con ❤️ para facilitar la traducción global**
