# FASE 1: CONFIGURACIÓN DEL ENTORNO

## Objetivo
Crear estructura base completa del proyecto

## 🎯 Para Copilot

**Lee esta sección completamente antes de empezar.**

Debes crear todos los archivos especificados a continuación en las ubicaciones indicadas. Para cada archivo, proporciona el contenido exacto entre los bloques de código.

---

## ACCIÓN 1️⃣: Crear carpetas

```
Crea estas carpetas en la raíz del proyecto:
- src/
- tests/
- .github/workflows/
- .copilot/
```

**Confirmación esperada**: "✅ Carpetas creadas"

---

## ACCIÓN 2️⃣: Crear package.json

**Ubicación**: `/package.json`

```json
{
  "name": "mi-proyecto",
  "version": "1.0.0",
  "description": "Proyecto con integración Travis CI/CD y GitHub Actions",
  "main": "src/index.js",
  "scripts": {
    "start": "node src/index.js",
    "dev": "node --watch src/index.js",
    "test": "jest --coverage",
    "test:watch": "jest --watch",
    "lint": "eslint src/ tests/",
    "lint:fix": "eslint src/ tests/ --fix",
    "format": "prettier --write src/ tests/ .github/",
    "coverage": "jest --coverage --coverageReporters=text-lcov",
    "build": "echo 'Build process completed'"
  },
  "keywords": [
    "ci-cd",
    "travis",
    "testing",
    "express"
  ],
  "author": "Tu Nombre",
  "license": "ISC",
  "dependencies": {
    "express": "^4.18.2",
    "dotenv": "^16.3.1"
  },
  "devDependencies": {
    "jest": "^29.7.0",
    "supertest": "^6.3.3",
    "eslint": "^8.50.0",
    "prettier": "^3.0.3"
  }
}
```

**Confirmación esperada**: "✅ package.json creado con todos los scripts"

---

## ACCIÓN 3️⃣: Crear .gitignore

**Ubicación**: `/.gitignore`

```
node_modules/
.env
.env.local
.env.*.local
.DS_Store
dist/
build/
coverage/
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.idea/
.vscode/*
!.vscode/settings.json
*.swp
*.swo
*~
.coverage
.nyc_output/
```

**Confirmación esperada**: "✅ .gitignore creado"

---

## ACCIÓN 4️⃣: Crear .env.example

**Ubicación**: `/.env.example`

```
PORT=3000
NODE_ENV=development
API_URL=http://localhost:3000
LOG_LEVEL=info
```

**Confirmación esperada**: "✅ .env.example creado"

---

## ACCIÓN 5️⃣: Crear src/config.js

**Ubicación**: `/src/config.js`

```javascript
require('dotenv').config();

module.exports = {
  port: process.env.PORT || 3000,
  env: process.env.NODE_ENV || 'development',
  apiUrl: process.env.API_URL || 'http://localhost:3000',
  logLevel: process.env.LOG_LEVEL || 'info',
};
```

**Confirmación esperada**: "✅ src/config.js creado"

---

## ACCIÓN 6️⃣: Crear src/app.js

**Ubicación**: `/src/app.js`

```javascript
const express = require('express');

const app = express();

// Middlewares
app.use(express.json());

// Health check endpoint
app.get('/health', (req, res) => {
  res.json({
    status: 'OK',
    timestamp: new Date().toISOString(),
    uptime: process.uptime(),
  });
});

// Root endpoint
app.get('/', (req, res) => {
  res.json({
    message: '¡Hola desde mi aplicación!',
    version: '1.0.0',
  });
});

// 404 handler
app.use((req, res) => {
  res.status(404).json({ error: 'Ruta no encontrada' });
});

// Error handler
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({
    error: 'Error interno del servidor',
    message: err.message,
  });
});

module.exports = app;
```

**Confirmación esperada**: "✅ src/app.js creado"

---

## ACCIÓN 7️⃣: Crear src/index.js

**Ubicación**: `/src/index.js`

```javascript
const app = require('./app');
const config = require('./config');

const PORT = config.port;

app.listen(PORT, () => {
  console.log(`✅ Servidor ejecutando en puerto ${PORT}`);
  console.log(`📍 Ambiente: ${config.env}`);
});

module.exports = app;
```

**Confirmación esperada**: "✅ src/index.js creado"

---

## ✅ VALIDACIÓN FASE 1

Confirma que se completó:

```
✅ FASE 1 COMPLETADA
- ✅ Carpetas creadas (src/, tests/, .github/workflows/, .copilot/)
- ✅ package.json configurado
- ✅ .gitignore creado
- ✅ .env.example creado
- ✅ src/config.js creado
- ✅ src/app.js creado
- ✅ src/index.js creado

🚀 Listo para FASE 2: Configuración de GitHub
```

Si todo está bien, continúa con la siguiente fase.
