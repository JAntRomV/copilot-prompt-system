# FASE 3: REQUISITOS Y SUITE DE PRUEBAS

## Objetivo
Crear documentación de requisitos y suite completa de pruebas

## 🎯 Para Copilot

Lee esta sección completamente. Crea todos los archivos en las ubicaciones indicadas.

---

## ACCIÓN 1️⃣: Crear REQUIREMENTS.md

**Ubicación**: `/REQUIREMENTS.md`

```markdown
# Requisitos del Sistema

## 📌 Requisitos Funcionales

### RF-001: Servidor API
- **Descripción**: Aplicación ejecutándose como servidor HTTP
- **Puerto**: 3000
- **Protocolo**: HTTP/REST
- **Criterios de aceptación**:
  - Servidor inicia en puerto especificado
  - Responde a requests HTTP
  - Maneja errores apropiadamente

### RF-002: Endpoint /health
- **Descripción**: Verificar estado de la aplicación
- **Método**: GET
- **Respuesta esperada**:
  ```json
  {
    "status": "OK",
    "timestamp": "2024-01-01T00:00:00Z",
    "uptime": 3600
  }
  ```

### RF-003: Endpoint /
- **Descripción**: Endpoint raíz de bienvenida
- **Método**: GET
- **Respuesta esperada**:
  ```json
  {
    "message": "¡Hola desde mi aplicación!",
    "version": "1.0.0"
  }
  ```

### RF-004: Manejo de Errores
- **Descripción**: Sistema retorna códigos HTTP apropiados
- **Códigos esperados**:
  - 200: Success
  - 404: Not Found
  - 500: Server Error

## 🔧 Requisitos Técnicos

### Versiones de Runtime
- Node.js >= 18.0.0
- npm >= 9.0.0

### Dependencias Principales
- Express.js >= 4.18.0
- dotenv >= 16.0.0

### Dependencias de Desarrollo
- Jest >= 29.0.0
- ESLint >= 8.0.0
- Prettier >= 3.0.0
- Supertest >= 6.0.0

## 🧪 Requisitos de Pruebas

### Cobertura Mínima
- **Branches**: 80%
- **Functions**: 80%
- **Lines**: 80%
- **Statements**: 80%

### Tipos de Pruebas Requeridas
1. **Pruebas Unitarias**: Funciones individuales
2. **Pruebas de Integración**: Endpoints API
3. **Pruebas de Error**: Manejo de excepciones

### Criterios de Éxito
- ✅ Todas las pruebas pasan
- ✅ Cobertura >= 80%
- ✅ Tiempo de ejecución < 30 segundos
- ✅ Sin warnings en console

## 📊 Requisitos de Calidad de Código
- ✅ ESLint sin errores
- ✅ Prettier aplicado
- ✅ Documentación de funciones
- ✅ Sin código muerto
```

**Confirmación esperada**: "✅ REQUIREMENTS.md creado"

---

## ACCIÓN 2️⃣: Crear tests/app.test.js

**Ubicación**: `/tests/app.test.js`

```javascript
const request = require('supertest');
const app = require('../src/app');

describe('🧪 Test Suite - Aplicación Express', () => {

  describe('GET /', () => {
    it('✅ Debería retornar mensaje de bienvenida', async () => {
      const response = await request(app)
        .get('/')
        .expect('Content-Type', /json/)
        .expect(200);

      expect(response.body).toHaveProperty('message');
      expect(response.body.message).toBe('¡Hola desde mi aplicación!');
      expect(response.body).toHaveProperty('version');
    });

    it('✅ Debería retornar estructura correcta', async () => {
      const response = await request(app).get('/');

      expect(response.body).toEqual(
        expect.objectContaining({
          message: expect.any(String),
          version: expect.any(String),
        })
      );
    });
  });

  describe('GET /health', () => {
    it('✅ Debería retornar status OK', async () => {
      const response = await request(app)
        .get('/health')
        .expect('Content-Type', /json/)
        .expect(200);

      expect(response.body.status).toBe('OK');
    });

    it('✅ Debería incluir timestamp', async () => {
      const response = await request(app).get('/health');

      expect(response.body).toHaveProperty('timestamp');
      expect(new Date(response.body.timestamp)).toBeInstanceOf(Date);
    });

    it('✅ Debería incluir información de uptime', async () => {
      const response = await request(app).get('/health');

      expect(response.body).toHaveProperty('uptime');
      expect(typeof response.body.uptime).toBe('number');
      expect(response.body.uptime).toBeGreaterThanOrEqual(0);
    });
  });

  describe('Rutas inexistentes', () => {
    it('✅ Debería retornar 404 para rutas no encontradas', async () => {
      const response = await request(app)
        .get('/ruta-que-no-existe')
        .expect(404);

      expect(response.body).toHaveProperty('error');
    });

    it('✅ Debería retornar JSON en error 404', async () => {
      const response = await request(app)
        .get('/api/inexistente')
        .expect('Content-Type', /json/)
        .expect(404);

      expect(response.body).toEqual(
        expect.objectContaining({
          error: expect.any(String),
        })
      );
    });
  });

  describe('Content-Type Headers', () => {
    it('✅ Debería retornar application/json en GET /', async () => {
      await request(app)
        .get('/')
        .expect('Content-Type', /json/);
    });

    it('✅ Debería retornar application/json en GET /health', async () => {
      await request(app)
        .get('/health')
        .expect('Content-Type', /json/);
    });
  });
});
```

**Confirmación esperada**: "✅ tests/app.test.js creado"

---

## ACCIÓN 3️⃣: Crear tests/config.test.js

**Ubicación**: `/tests/config.test.js`

```javascript
const config = require('../src/config');

describe('🔧 Test Suite - Configuración', () => {

  describe('Variables de Configuración', () => {
    it('✅ Debería tener propiedad port', () => {
      expect(config).toHaveProperty('port');
      expect(typeof config.port).toBe('number');
    });

    it('✅ Debería tener propiedad env', () => {
      expect(config).toHaveProperty('env');
      expect(typeof config.env).toBe('string');
    });

    it('✅ Debería tener propiedad apiUrl', () => {
      expect(config).toHaveProperty('apiUrl');
      expect(typeof config.apiUrl).toBe('string');
    });

    it('✅ Debería tener propiedad logLevel', () => {
      expect(config).toHaveProperty('logLevel');
      expect(typeof config.logLevel).toBe('string');
    });
  });

  describe('Valores por Defecto', () => {
    it('✅ Puerto por defecto debería ser 3000', () => {
      expect(config.port).toBe(3000);
    });

    it('✅ Ambiente por defecto debería ser development', () => {
      expect(config.env).toBe('development');
    });

    it('✅ apiUrl por defecto debería contener localhost', () => {
      expect(config.apiUrl).toContain('localhost');
    });
  });
});
```

**Confirmación esperada**: "✅ tests/config.test.js creado"

---

## ✅ VALIDACIÓN FASE 3

Confirma que se completó:

```
✅ FASE 3 COMPLETADA
- ✅ REQUIREMENTS.md creado
- ✅ tests/app.test.js creado con suite completa
- ✅ tests/config.test.js creado
- ✅ Cobertura de código >= 80%
- ✅ Todos los tests listos para ejecutar

🚀 Listo para FASE 4: CI/CD
```
