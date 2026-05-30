# FASE 4: CONFIGURACIÓN CI/CD

## Objetivo
Crear configuraciones avanzadas de CI/CD, documentación y workflows

## 🎯 Para Copilot

Lee esta sección completamente. Crea todos los archivos especificados.

---

## ACCIÓN 1️⃣: Crear .github/dependabot.yml

**Ubicación**: `/.github/dependabot.yml`

```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
    open-pull-requests-limit: 10
    reviewers:
      - "tu-usuario"
```

**Confirmación esperada**: "✅ .github/dependabot.yml creado"

---

## ACCIÓN 2️⃣: Crear .github/CODEOWNERS

**Ubicación**: `/.github/CODEOWNERS`

```
# Propietarios de código

# Archivos de configuración
*.json @JAntRomV
*.yml @JAntRomV
*.yaml @JAntRomV

# Tests
/tests/ @JAntRomV

# Source
/src/ @JAntRomV

# Documentación
*.md @JAntRomV
```

**Confirmación esperada**: "✅ .github/CODEOWNERS creado"

---

## ACCIÓN 3️⃣: Crear .github/ISSUE_TEMPLATE/bug_report.md

**Ubicación**: `/.github/ISSUE_TEMPLATE/bug_report.md`

```markdown
---
name: 🐛 Bug Report
about: Reportar un error encontrado
title: '[BUG] '
labels: 'bug'
assignees: ''

---

## Descripción del Bug
<!-- Describe claramente el bug -->

## Pasos para Reproducir
1. Paso 1...
2. Paso 2...
3. Paso 3...

## Comportamiento Esperado
<!-- ¿Qué debería pasar? -->

## Comportamiento Actual
<!-- ¿Qué pasó realmente? -->

## Información del Ambiente
- Node.js version: 
- npm version: 
- OS: 

## Logs/Screenshots
<!-- Adjunta logs o screenshots -->
```

**Confirmación esperada**: "✅ bug_report.md creado"

---

## ACCIÓN 4️⃣: Crear .github/ISSUE_TEMPLATE/feature_request.md

**Ubicación**: `/.github/ISSUE_TEMPLATE/feature_request.md`

```markdown
---
name: ✨ Feature Request
about: Sugerir una nueva funcionalidad
title: '[FEATURE] '
labels: 'enhancement'
assignees: ''

---

## Descripción de la Funcionalidad
<!-- Describe la funcionalidad deseada -->

## Problema que Resuelve
<!-- Describe el problema -->

## Solución Propuesta
<!-- Tu idea de la solución -->

## Alternativas Consideradas
<!-- Otras opciones -->
```

**Confirmación esperada**: "✅ feature_request.md creado"

---

## ACCIÓN 5️⃣: Crear CONTRIBUTING.md

**Ubicación**: `/CONTRIBUTING.md`

```markdown
# Guía de Contribución

¡Gracias por interés en contribuir!

## 📋 Proceso de Contribución

### 1. Fork del Proyecto

\`\`\`bash
git clone https://github.com/TU_USER/mi-proyecto.git
cd mi-proyecto
\`\`\`

### 2. Crear Rama de Feature

\`\`\`bash
git checkout -b feature/descripcion-feature
\`\`\`

**Naming convention**:
- `feature/nombre-feature` - Nuevas funcionalidades
- `bugfix/descripcion-bug` - Correcciones
- `docs/descripcion-docs` - Documentación

### 3. Hacer Cambios

\`\`\`bash
npm install
npm run dev
npm test
npm run format
npm run lint
\`\`\`

### 4. Commit con Mensajes Claros

\`\`\`bash
git add .
git commit -m "feat: descripción clara"
\`\`\`

**Formato**:
- `feat:` - Nueva funcionalidad
- `fix:` - Corrección de bug
- `docs:` - Documentación
- `style:` - Cambios de estilo
- `test:` - Tests

### 5. Push y Pull Request

\`\`\`bash
git push origin feature/descripcion-feature
\`\`\`

### 6. Requisitos antes de PR

- ✅ `npm run format`
- ✅ `npm run lint`
- ✅ `npm test` (cobertura >= 80%)
- ✅ Documentación actualizada

---

¡Gracias por tu contribución! 🎉
```

**Confirmación esperada**: "✅ CONTRIBUTING.md creado"

---

## ACCIÓN 6️⃣: Crear CHANGELOG.md

**Ubicación**: `/CHANGELOG.md`

```markdown
# Changelog

Todos los cambios notables en este proyecto se documentarán aquí.

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/)

## [1.0.0] - 2024-01-01

### Added
- Proyecto inicial configurado
- Servidor Express básico
- Endpoints /health y /
- Suite de pruebas con Jest
- Integración con Travis CI/CD
- GitHub Actions workflows
- ESLint y Prettier configurados
- Documentación completa

### Changed
- N/A

### Deprecated
- N/A

### Removed
- N/A

### Fixed
- N/A

### Security
- N/A
```

**Confirmación esperada**: "✅ CHANGELOG.md creado"

---

## ACCIÓN 7️⃣: Crear .env.local (ejemplo)

**Ubicación**: `/.env.local` (para desarrollo local)

```
PORT=3000
NODE_ENV=development
API_URL=http://localhost:3000
LOG_LEVEL=info
```

**Confirmación esperada**: "✅ .env.local creado (usar solo localmente)"

---

## ✅ VALIDACIÓN FINAL - FASE 4

Confirma que se completó:

```
✅ FASE 4 COMPLETADA
- ✅ .github/dependabot.yml creado
- ✅ .github/CODEOWNERS creado
- ✅ Issue templates creados
- ✅ CONTRIBUTING.md creado
- ✅ CHANGELOG.md creado
- ✅ .env.local creado

🎉 PROYECTO COMPLETAMENTE CONFIGURADO

Próximos pasos:
1. npm install
2. npm test
3. npm run lint
4. git add . && git commit -m "chore: setup inicial"
5. Configurar Travis CI en travis-ci.com
```
