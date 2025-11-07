# 🚀 Automatización de APIs con Postman y Newman
<img width="1536" height="1024" alt="ChatGPT Image 7 nov 2025, 11_03_26 a m" src="https://github.com/user-attachments/assets/5bb1bc70-132d-4104-8273-754d24da0ed8" />

## 📋 Descripción del Proyecto
Sistema de pruebas automatizadas para APIs que ejecuta colecciones de Postman mediante Newman en un pipeline de CI/CD con GitHub Actions. Incluye validaciones de endpoints, reportes HTML y ejecución continua.

## 🏗️ ¿Cómo Funciona?

### 🔄 Flujo Completo del Sistema

<img width="6691" height="2653" alt="deepseek_mermaid_20251106_b744bd" src="https://github.com/user-attachments/assets/6d792938-08e2-4049-8095-e0efd8e65d56" />



### 📊 Proceso Detallado

1. **Creación de Pruebas**: Se diseñan tests en Postman con validaciones JavaScript
2. **Exportación**: La colección se guarda como JSON en el repositorio
3. **Ejecución Automática**: GitHub Actions detecta cambios y ejecuta el pipeline
4. **Validación**: Newman ejecuta los requests y verifica las respuestas
5. **Reporte**: Se genera un dashboard HTML con resultados
6. **Almacenamiento**: El reporte se guarda como artifact en GitHub

## ✨ Características
- ✅ **Pruebas automatizadas** de APIs REST
- ✅ **Integración continua** con GitHub Actions
- 📊 **Reportes HTML interactivos** con Newman HTML Extra
- ⚙️ **Configuración flexible** mediante variables de entorno
- 🧪 **5 casos de prueba** para endpoints de registro
- 🔄 **Ejecución en múltiples triggers** (push, PR, manual)

## 🛠️ Tecnologías
- **Postman** - Creación y gestión de colecciones de pruebas
- **Newman** - Ejecutor CLI para colecciones Postman
- **GitHub Actions** - Plataforma de CI/CD
- **Node.js** - Entorno de ejecución (v18)
- **HTML Extra Reporter** - Generador de reportes visuales
- **HTTP Bin** - API de testing para validaciones

## 📁 Estructura del Proyecto
**Archivos principales:**
- `.github/workflows/api-tests.yml` → Pipeline de GitHub Actions
- `NewCollection.postman_collection.json` → Colección de pruebas Postman
- `README.md` → Esta documentación


## 🧪 Casos de Prueba
| ID | Descripción | Método | Endpoint | Validaciones |
|----|-------------|--------|----------|--------------|
| TC_001 | Registrar nombre del cliente | POST | /post | Nombre + Status 200 |
| TC_002 | Registrar nombre del padre | POST | /post | Nombre del padre |
| TC_003 | Registrar nombre de la madre | POST | /post | Nombre de la madre |
| TC_004 | Registrar nombre de mascota | POST | /post | Nombre de mascota |
| TC_005 | Registrar celular del cliente | POST | /post | Número de celular |

## ⚙️ Configuración

### 🔧 Instalación de Dependencias
```bash
# Instalar Newman y el reporter HTML globalmente
npm install -g newman newman-reporter-htmlextra

🏃‍♂️ Ejecución Local
bash

# Ejecutar pruebas básicas (solo consola)
newman run NewCollection.postman_collection.json

# Ejecutar con reporte HTML detallado
newman run NewCollection.postman_collection.json -r htmlextra --reporter-htmlextra-export report.html

# Ejecutar con variables específicas
newman run NewCollection.postman_collection.json --env-var "url_test=https://mi-api.com"

🔄 Pipeline CI/CD
🚀 Triggers de Ejecución

    📤 Push a rama main - Ejecución automática en cada commit

    🔄 Pull requests a main - Validación antes de merge

    👆 Ejecución manual - Desde la pestaña GitHub Actions

📊 Flujo del Pipeline

    📥 Checkout del código - Descarga el repositorio

    🏗️ Setup de Node.js - Configura ambiente Node.js v18

    📦 Instalación de dependencias - Newman y HTML reporter

    🧪 Ejecución de pruebas - Newman ejecuta la colección

    📄 Generación de reporte HTML - Crea dashboard interactivo

    ☁️ Upload del artifact - Guarda reporte en GitHub

📊 Reportes y Resultados
🎯 Acceso a Reportes

    Navegar a Actions → Workflows en GitHub

    Seleccionar la ejecución deseada

    Descargar el artifact "newman-report"

    Abrir newman-report.html en el navegador

📈 Contenido del Reporte

    Dashboard resumen con métricas generales

    Detalles por test case con requests/responses

    Tiempos de ejecución y performance

    Resultados de assertions (passed/failed)

    Variables de entorno utilizadas

🔧 Variables de Configuración
🌐 Variables de Entorno

    url_test: https://httpbin.org (API de testing por defecto)

⚙️ Personalización
bash

# Cambiar URL de testing
newman run collection.json --env-var "url_test=https://api.midominio.com"

# Agregar más variables
newman run collection.json --env-var "api_key=mi_token_secreto"

🚀 Ejemplo de Test en Postman
javascript

// Validación típica en los tests
pm.test("Validar nombre del cliente", function () {
    var responseData = pm.response.json().json;
    pm.expect(responseData.FirstName).to.eql("Juan Peréz");
});

pm.test("Validar status code", function () {
    pm.response.to.have.status(200);
});

Estado: ✅ Activo
Última ejecución: 👀 Ver GitHub Actions
Coverage: 5 endpoints de API validados
Performance: 12.4s por request (promedio)
