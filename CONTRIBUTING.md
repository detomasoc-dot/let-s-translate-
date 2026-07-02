# Guía de Contribuciones

¡Gracias por tu interés en contribuir a Let's Translate! 🎉

## 📋 Código de Conducta

Este proyecto y todos aquellos que participen en él están regidos por nuestro [Código de Conducta](CODE_OF_CONDUCT.md). Al participar, se espera que mantengas este código.

## 🚀 Cómo Contribuir

### Reportar Bugs

Antes de reportar un bug:
1. Verifica que no se haya reportado antes
2. Recopila toda la información posible
3. Proporciona código de ejemplo si es posible

**Formato para reportar:**
- Descripción clara del problema
- Pasos exactos para reproducir
- Comportamiento esperado vs actual
- Tu entorno (OS, navegador, versión de Node)
- Screenshots o logs si aplica

### Sugerir Mejoras

1. Usa un título claro y descriptivo
2. Proporciona descripción detallada de la mejora
3. Explica por qué sería útil
4. Lista algunos ejemplos de cómo se usaría

### Pull Requests

1. **Fork el repositorio**
   ```bash
   git clone https://github.com/tu-usuario/let-s-translate-.git
   cd let-s-translate-
   ```

2. **Crea una rama**
   ```bash
   git checkout -b feature/descripcion-feature
   # o
   git checkout -b fix/descripcion-fix
   ```

3. **Realiza tus cambios**
   - Sigue el estilo de código existente
   - Escribe mensajes de commit claros
   - Incluye comentarios cuando sea necesario

4. **Commits Semánticos**
   ```bash
   git commit -m "feat: agregar nueva característica"
   git commit -m "fix: corregir bug en traductor"
   git commit -m "docs: actualizar documentación"
   git commit -m "style: formatear código"
   git commit -m "refactor: refactorizar componente"
   git commit -m "test: agregar tests"
   ```

5. **Push a tu fork**
   ```bash
   git push origin feature/descripcion-feature
   ```

6. **Abre un Pull Request**
   - Describe claramente los cambios
   - Referencia issues relacionados (#123)
   - Incluye screenshots si es UI

## 📝 Estándares de Código

### Frontend (React + TypeScript)
```typescript
// Usar componentes funcionales
const MyComponent: React.FC<Props> = ({ prop1, prop2 }) => {
  return (
    <div className="flex items-center">
      {prop1}
    </div>
  );
};

export default MyComponent;
```

### Backend (Express + TypeScript)
```typescript
// Controllers
app.post('/api/endpoint', authMiddleware, async (req, res) => {
  try {
    // lógica
    res.json({ success: true, data });
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
});
```

## 🧪 Testing

- Escribe tests para nuevas características
- Ejecuta tests antes de hacer commit
- Mantén una cobertura > 80%

```bash
# Frontend
cd frontend && npm test

# Backend
cd backend && npm test
```

## 📦 Estructura de Directorios

```
let-s-translate-/
├── frontend/
│   ├── src/
│   │   ├── components/   # Componentes reutilizables
│   │   ├── pages/        # Páginas/vistas
│   │   ├── services/     # Llamadas a API
│   │   ├── hooks/        # Custom hooks
│   │   └── types/        # TypeScript types
│   └── ...
├── backend/
│   ├── src/
│   │   ├── controllers/  # Lógica de rutas
│   │   ├── models/       # Esquemas MongoDB
│   │   ├── routes/       # Definición de rutas
│   │   ├── middleware/   # Middleware Express
│   │   └── services/     # Lógica de negocio
│   └── ...
└── docs/  # Documentación
```

## ✅ Checklist Antes de PR

- [ ] El código sigue los estándares del proyecto
- [ ] He ejecutado `npm test` y todo pasa
- [ ] He actualizado la documentación
- [ ] He incluido tests para nuevas características
- [ ] He verificado que no hay conflictos con `main`
- [ ] He escrito commits descriptivos
- [ ] No hay console.log ni comentarios de debug

## 🎯 Áreas de Enfoque

Especialmente buscamos ayuda en:
- [ ] Implementar más idiomas
- [ ] Mejorar la UI/UX
- [ ] Optimizar rendimiento
- [ ] Agregar tests
- [ ] Documentación
- [ ] Internacionalización (i18n)
- [ ] Accesibilidad (a11y)

## 📞 Preguntas?

- Abre un issue para preguntas
- Revisa la documentación en `/docs`
- Contacta a los maintainers

## 🙏 Gracias

¡Tu contribución hace Let's Translate mejor! 🚀
