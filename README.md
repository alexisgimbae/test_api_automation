# 🚀 Automatización de APIs con Postman y Newman

## 📋 Descripción del Proyecto
Proyecto de automatización de pruebas API utilizando Postman Collections y Newman, integrado con GitHub Actions para CI/CD.

## ✨ Características
- ✅ Pruebas automatizadas de APIs
- ✅ Integración con GitHub Actions
- 📊 Reportes HTML detallados
- ⚙️ Variables de entorno configurables
- 🧪 Múltiples casos de prueba

## 🛠️ Tecnologías
- **Postman** - Creación de colecciones de pruebas
- **Newman** - Ejecutor de colecciones por CLI
- **GitHub Actions** - Pipeline de CI/CD
- **Node.js** - Entorno de ejecución
- **HTML Extra Reporter** - Generador de reportes

## 📁 Estructura del Proyecto
├── .github/
│ └── workflows/
│ └── api-tests.yml
├── NewCollection.postman_collection.json
└── README.md


## 🧪 Casos de Prueba
| ID | Descripción | Método | Endpoint |
|----|-------------|--------|----------|
| TC_001 | Registrar nombre del cliente | POST | /post |
| TC_002 | Registrar nombre del padre | POST | /post |
| TC_003 | Registrar nombre de la madre | POST | /post |
| TC_004 | Registrar nombre de mascota | POST | /post |
| TC_005 | Registrar celular del cliente | POST | /post |

## ⚙️ Configuración

### 🔧 Instalación
```bash
npm install -g newman newman-reporter-htmlextra

🏃‍♂️ Ejecución Local
# Ejecutar pruebas
newman run NewCollection.postman_collection.json

# Con reporte HTML
newman run NewCollection.postman_collection.json -r htmlextra --reporter-htmlextra-export report.html

🔄 Pipeline CI/CD
El workflow se ejecuta automáticamente en:

    📤 Push a rama main

    🔄 Pull requests a main

    👆 Ejecución manual

📊 Flujo

    📥 Checkout del código

    🏗️ Setup de Node.js

    📦 Instalación de dependencias

    🧪 Ejecución de pruebas con Newman

    📄 Generación de reporte HTML

    ☁️ Upload del reporte como artifact

📊 Reportes

Los reportes HTML están disponibles en GitHub Actions como artifacts después de cada ejecución.
🔧 Variables

    url_test: https://httpbin.org (API de testing)

Estado: ✅ Activo
Última ejecución: 👀 Ver GitHub Actions
