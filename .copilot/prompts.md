# GitHub Copilot - Sistema Completo de Prompts

## 🎯 PROPÓSITO

Sistema automatizado que permite a GitHub Copilot generar un proyecto Node.js profesional con:
- Express.js
- Travis CI/CD
- GitHub Actions
- Jest Testing
- ESLint + Prettier
- Estructura profesional

## 📌 MODO DE OPERACIÓN

Este sistema usa archivos Markdown como "recetas" que Copilot lee y ejecuta secuencialmente.

### Archivos del Sistema:
1. **prompts.md** (este archivo) - Contexto general
2. **setup-environment.md** - Fase 1: Estructura base
3. **github-config.md** - Fase 2: Configuraciones
4. **test-requirements.md** - Fase 3: Pruebas
5. **ci-cd-config.md** - Fase 4: CI/CD
6. **execution-guide.md** - Guía de uso
7. **quick-prompts.txt** - Prompts rápidos

---

## ⚡ INICIO RÁPIDO

### Para ejecutar TODO automáticamente:

```
@copilot Eres experto en Node.js y CI/CD.

Lee estos archivos en orden:
1. .copilot/setup-environment.md
2. .copilot/github-config.md
3. .copilot/test-requirements.md
4. .copilot/ci-cd-config.md

Ejecuta TODAS las acciones de cada archivo.

Para cada archivo, crea los archivos y carpetas especificados.

Después de cada fase, muestra:
- Lista de archivos creados ✅
- Confirmación de completitud

Al final, muestra reporte completo.
```

---

## 🔧 VARIABLES DE CONFIGURACIÓN

Personaliza estos valores:

| Variable | Valor | Ubicación |
|----------|-------|----------|
| {PROJECT_NAME} | tu-proyecto | En prompts |
| {GITHUB_USER} | tu-usuario | En README.md |
| {NODE_VERSION} | 18, 20 | En .travis.yml |
| {COVERAGE_THRESHOLD} | 80 | En jest.config.js |
| {PORT} | 3000 | En config.js |

---

## 📂 ESTRUCTURA DEL PROYECTO GENERADO

```
tu-proyecto/
├── src/
│   ├── index.js           ← Entrada principal
│   ├── app.js             ← Configuración Express
│   └── config.js          ← Variables de entorno
├── tests/
│   ├── app.test.js        ← Tests de endpoints
│   └── config.test.js     ← Tests de configuración
├── .github/
│   ├── workflows/
│   │   ├── pr-checks.yml  ← Validación en PRs
│   │   └── deploy.yml     ← Deploy automático
│   ├── CODEOWNERS         ← Propietarios de código
│   └── dependabot.yml     ← Actualización automática
├── .copilot/              ← Sistema de prompts
├── package.json           ← Dependencias
├── .travis.yml            ← Travis CI config
├── .eslintrc.json         ← ESLint config
├── .prettierrc             ← Prettier config
├── jest.config.js         ← Jest config
├── .gitignore             ← Git ignore
├── .env.example           ← Variables de ejemplo
├── README.md              ← Documentación
├── REQUIREMENTS.md        ← Especificaciones
├── CONTRIBUTING.md        ← Guía de contribución
└── CHANGELOG.md           ← Registro de cambios
```

---

## ✅ CHECKLIST DE EJECUCIÓN

- [ ] Tengo GitHub Copilot instalado
- [ ] He descargado/copiado los archivos .copilot/
- [ ] He abierto la carpeta en mi editor
- [ ] He copiado el prompt principal
- [ ] He pegado en GitHub Copilot
- [ ] Copilot ha generado todos los archivos
- [ ] He validado con `npm test`
- [ ] He hecho commit inicial

---

## 🆘 SOPORTE

Si algo no funciona:
1. Revisa **execution-guide.md**
2. Consulta **quick-prompts.txt**
3. Intenta ejecutar por fases (Prompt 2, 3, 4, 5)

---

## 📝 Próximos Pasos

1. Descarga/clona estos archivos
2. Copia carpeta `.copilot/` a tu proyecto
3. Abre GitHub Copilot
4. Ejecuta el prompt principal
5. Valida con `npm install && npm test`
6. ¡A programar! 🚀
