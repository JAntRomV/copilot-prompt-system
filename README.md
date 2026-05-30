# 📦 SISTEMA COMPLETO DE PROMPTS PARA GITHUB COPILOT

> Automatiza la creación de un proyecto Node.js profesional con GitHub Copilot

## 🎯 ¿Qué Es?

Sistema de archivos Markdown que contiene "recetas" que GitHub Copilot puede leer y ejecutar automáticamente para generar:

- ✅ Proyecto Node.js con Express.js
- ✅ Configuración profesional completa
- ✅ Travis CI/CD integrado
- ✅ GitHub Actions workflows
- ✅ Suite de pruebas con Jest (80%+ cobertura)
- ✅ ESLint + Prettier automático
- ✅ Documentación completa
- ✅ Guías de contribución
- ✅ Protección de ramas

## 🚀 ¿Cómo Funciona?

1. 📄 Descarga/clona los archivos `.copilot/`
2. 🤖 Copia un prompt a GitHub Copilot
3. ⚙️ Copilot genera todos los archivos automáticamente
4. ✅ Valida con `npm test`
5. 🎉 ¡Proyecto listo!

## 📂 Contenido

```
.copilot/
├── prompts.md              # Contexto principal y objetivo
├── setup-environment.md    # Fase 1: Estructura base
├── github-config.md        # Fase 2: Configuraciones
├── test-requirements.md    # Fase 3: Pruebas
├── ci-cd-config.md         # Fase 4: CI/CD
├── execution-guide.md      # Guía detallada de uso
└── quick-prompts.txt       # Prompts listos para copiar
```

## ⚡ INICIO RÁPIDO

### Opción 1: Automática (5 minutos)

Copia este prompt en GitHub Copilot:

```
@copilot Lee estos archivos en orden: .copilot/setup-environment.md, 
.copilot/github-config.md, .copilot/test-requirements.md, 
.copilot/ci-cd-config.md

Para CADA archivo, crea TODOS los archivos especificados en las ubicaciones exactas.
Confirma cada archivo creado. Al final, muestra lista completa de archivos creados.
```

### Opción 2: Por Fases (Revisable)

Lee **execution-guide.md** para instrucciones paso a paso.

## ✅ Contenido Generado

Después de ejecutar, obtendrás:

```
tu-proyecto/
├── src/
│   ├── index.js
│   ├── app.js
│   └── config.js
├── tests/
│   ├── app.test.js
│   └── config.test.js
├── .github/
│   ├── workflows/
│   │   ├── pr-checks.yml
│   │   └── deploy.yml
│   ├── CODEOWNERS
│   └── dependabot.yml
├── package.json
├── .travis.yml
├── .eslintrc.json
├── .prettierrc
├── jest.config.js
├── .gitignore
├── README.md
├── REQUIREMENTS.md
├── CONTRIBUTING.md
└── CHANGELOG.md
```

## 🔧 Requisitos

- Node.js >= 18
- npm >= 9
- GitHub Copilot instalado
- Editor compatible (VS Code, IntelliJ, etc.)

## 📖 Documentación

- **QUICK_START.md** - Guía rápida de inicio
- **execution-guide.md** - Guía detallada
- **quick-prompts.txt** - Prompts listos para copiar
- **prompts.md** - Contexto y objetivos

## 🆘 Solución de Problemas

Si algo no funciona:

1. Verifica que Copilot esté instalado
2. Abre la carpeta del proyecto
3. Intenta con **PROMPT 2, 3, 4, 5** (por fases) en lugar de Todo
4. Lee **execution-guide.md**

## 🎓 Aprendizaje

Después de usar este sistema, aprendiste:

- ✅ Cómo usar Copilot para generar código
- ✅ Estructura profesional de proyectos Node.js
- ✅ Configuración de CI/CD
- ✅ Testing con Jest
- ✅ ESLint + Prettier
- ✅ GitHub Actions
- ✅ Travis CI

## 📚 Recursos

- [Jest Documentation](https://jestjs.io)
- [ESLint Documentation](https://eslint.org)
- [GitHub Actions](https://github.com/features/actions)
- [Travis CI](https://travis-ci.com)
- [Express.js](https://expressjs.com)

## 💡 Tips

1. **Copia prompts desde quick-prompts.txt**
2. **Usa PROMPT 1 para ejecución automática**
3. **Usa prompts individuales para agregar funcionalidad**
4. **Revisa ejecución con `npm test`**
5. **Consulta execution-guide.md para dudas**

## 📝 Licencia

MIT - Libre para usar en tus proyectos

## 🤝 Contribuciones

Este es un sistema de prompts. Siéntete libre de:
- Modificar archivos .md
- Agregar nuevas fases
- Adaptar a tus necesidades
- Compartir mejoras

---

**Hecho por la comunidad de GitHub Copilot**

¡Convierte horas de configuración en minutos! ⚡🚀
