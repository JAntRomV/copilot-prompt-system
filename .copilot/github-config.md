# FASE 2: CONFIGURACIÓN DE GITHUB

## Objetivo
Crear archivos de configuración para GitHub, ESLint, Prettier y Jest

## 🎯 Para Copilot

Lee esta sección completamente. Debes crear todos los archivos especificados en las ubicaciones exactas indicadas.

---

## ACCIÓN 1️⃣: Crear .eslintrc.json

**Ubicación**: `/.eslintrc.json`

```json
{
  "env": {
    "node": true,
    "es2021": true,
    "jest": true
  },
  "extends": "eslint:recommended",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "rules": {
    "indent": ["error", 2],
    "linebreak-style": ["error", "unix"],
    "quotes": ["error", "single"],
    "semi": ["error", "always"],
    "no-unused-vars": ["error", { "argsIgnorePattern": "^_" }],
    "no-console": "warn",
    "eqeqeq": ["error", "always"],
    "curly": ["error", "all"]
  }
}
```

**Confirmación esperada**: "✅ .eslintrc.json creado"

---

## ACCIÓN 2️⃣: Crear .prettierrc

**Ubicación**: `/.prettierrc`

```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "arrowParens": "always",
  "bracketSpacing": true,
  "endOfLine": "lf"
}
```

**Confirmación esperada**: "✅ .prettierrc creado"

---

## ACCIÓN 3️⃣: Crear jest.config.js

**Ubicación**: `/jest.config.js`

```javascript
module.exports = {
  testEnvironment: 'node',
  coveragePathIgnorePatterns: ['/node_modules/'],
  testMatch: ['**/tests/**/*.test.js'],
  collectCoverageFrom: [
    'src/**/*.js',
    '!src/index.js',
  ],
  coverageThreshold: {
    global: {
      branches: 80,
      functions: 80,
      lines: 80,
      statements: 80,
    },
  },
  verbose: true,
  bail: false,
};
```

**Confirmación esperada**: "✅ jest.config.js creado"

---

## ACCIÓN 4️⃣: Crear .travis.yml

**Ubicación**: `/.travis.yml`

```yaml
language: node_js

node_js:
  - "18"
  - "20"

cache:
  directories:
    - node_modules

before_install:
  - npm install -g npm@latest

install:
  - npm ci

before_script:
  - npm run lint

script:
  - npm run test

after_success:
  - npm run coverage
  - npm run build

notifications:
  email:
    on_success: change
    on_failure: always

branches:
  only:
    - main
    - develop
```

**Confirmación esperada**: "✅ .travis.yml creado"

---

## ACCIÓN 5️⃣: Crear .github/workflows/pr-checks.yml

**Ubicación**: `/.github/workflows/pr-checks.yml`

```yaml
name: PR Checks

on:
  pull_request:
    branches: [ main, develop ]

jobs:
  checks:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [18.x, 20.x]

    steps:
    - uses: actions/checkout@v4

    - name: Setup Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'

    - name: Instalar dependencias
      run: npm ci

    - name: Linting
      run: npm run lint

    - name: Ejecutar pruebas
      run: npm run test

    - name: Generar reporte de cobertura
      run: npm run coverage
```

**Confirmación esperada**: "✅ .github/workflows/pr-checks.yml creado"

---

## ACCIÓN 6️⃣: Crear .github/workflows/deploy.yml

**Ubicación**: `/.github/workflows/deploy.yml`

```yaml
name: Deploy

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v4

    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20'
        cache: 'npm'

    - name: Instalar dependencias
      run: npm ci

    - name: Linting
      run: npm run lint

    - name: Ejecutar pruebas
      run: npm run test

    - name: Build
      run: npm run build

    - name: Deploy notification
      run: echo "✅ Deployment process completed"
```

**Confirmación esperada**: "✅ .github/workflows/deploy.yml creado"

---

## ACCIÓN 7️⃣: Crear README.md

**Ubicación**: `/README.md`

```markdown
# Mi Proyecto

[![Build Status](https://travis-ci.com/TU_USUARIO/mi-proyecto.svg?branch=main)](https://travis-ci.com/TU_USUARIO/mi-proyecto)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D18-brightgreen)](https://nodejs.org)

Proyecto profesional con integración continua usando Travis CI/CD y GitHub Actions.

## 📋 Tabla de Contenidos

- [Instalación](#instalación)
- [Scripts](#scripts-disponibles)
- [Pruebas](#pruebas)
- [CI/CD](#cicd)
- [Requisitos](#requisitos)

## ⚙️ Instalación

```bash
git clone https://github.com/TU_USUARIO/mi-proyecto.git
cd mi-proyecto
npm install
```

## 🔧 Scripts Disponibles

- **npm start** - Inicia la aplicación en producción
- **npm run dev** - Inicia en modo desarrollo con recarga automática
- **npm test** - Ejecuta suite de pruebas con cobertura
- **npm run lint** - Valida código con ESLint
- **npm run lint:fix** - Corrige automáticamente errores de lint
- **npm run format** - Formatea código con Prettier
- **npm run coverage** - Genera reporte de cobertura
- **npm run build** - Compila la aplicación

## 🧪 Pruebas

```bash
npm test
```

Cobertura mínima requerida: **80%**

## 🚀 CI/CD

El proyecto usa:

- **Travis CI**: Para integración continua
- **GitHub Actions**: Para validación en PRs y despliegue automático

### Proceso Automático:
1. Cada push ejecuta linting y pruebas
2. Cada PR valida código en múltiples versiones de Node
3. Solo se permite merge si todas las pruebas pasan
4. Deploy automático en rama main

## 📋 Requisitos

- Node.js >= 18.0.0
- npm >= 9.0.0

## 📝 Licencia

ISC
```

**Confirmación esperada**: "✅ README.md creado"

---

## ✅ VALIDACIÓN FASE 2

Confirma que se completó:

```
✅ FASE 2 COMPLETADA
- ✅ .eslintrc.json configurado
- ✅ .prettierrc configurado
- ✅ jest.config.js configurado
- ✅ .travis.yml configurado
- ✅ .github/workflows/pr-checks.yml creado
- ✅ .github/workflows/deploy.yml creado
- ✅ README.md creado

🚀 Listo para FASE 3: Requisitos y Pruebas
```
