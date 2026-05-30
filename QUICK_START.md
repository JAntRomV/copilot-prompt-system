# ⚡ INICIO RÁPIDO (5 minutos)

## Paso 1: Preparación

```bash
# Crear carpeta del proyecto
mkdir mi-proyecto
cd mi-proyecto

# Inicializar Git
git init

# Copiar archivos .copilot/ de este repositorio
# (O copiar manualmente los 7 archivos .md)
```

## Paso 2: Abrir en Editor

- Abre VS Code (u otro editor)
- Abre la carpeta `mi-proyecto`
- Instala extensión GitHub Copilot

## Paso 3: Ejecutar Prompt

**En VS Code:**
1. Presiona `Cmd+Shift+I` (Mac) o `Ctrl+Shift+I` (Windows)
2. Se abre Copilot Chat
3. Pega este prompt exacto:

```
@copilot Eres experto en Node.js, Express, CI/CD, Travis CI y GitHub Actions.

Lee estos archivos en ORDEN EXACTO:
1. .copilot/setup-environment.md
2. .copilot/github-config.md
3. .copilot/test-requirements.md
4. .copilot/ci-cd-config.md

Para CADA archivo:
- Lee toda la sección
- Crea TODOS los archivos especificados
- DESPUÉS de completar, muestra: "✅ FASE COMPLETADA"

Al final, muestra lista de todos los archivos creados.
```

4. Presiona Enter
5. Espera a que complete (2-5 minutos)

## Paso 4: Validar

```bash
# Instalar dependencias
npm install

# Ejecutar pruebas
npm test

# Validar código
npm run lint
```

Deberías ver:
- ✅ Todos los tests pasando
- ✅ Cobertura >= 80%
- ✅ Sin errores de linting

## Paso 5: Primer Commit

```bash
git add .
git commit -m "chore: setup inicial con Copilot"
```

## 🎉 ¡Listo!

Tu proyecto está completamente configurado con:
- ✅ Express.js
- ✅ Jest Testing
- ✅ ESLint + Prettier
- ✅ Travis CI/CD
- ✅ GitHub Actions
- ✅ Documentación profesional

## 📖 Próximos Pasos

1. **Subir a GitHub**: 
   ```bash
   git remote add origin https://github.com/tu-usuario/mi-proyecto
   git push -u origin main
   ```

2. **Activar Travis CI**: https://travis-ci.com

3. **Proteger rama main**: Settings → Branches

4. **¡A programar!** 🚀

## ❓ ¿Necesitas Ayuda?

- Lee **execution-guide.md** para guía detallada
- Copia prompts de **quick-prompts.txt**
- Consulta **prompts.md** para contexto

¡Disfruta! 🎉
