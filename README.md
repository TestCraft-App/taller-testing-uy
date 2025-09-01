# Automatizando tu API con un agente de GenAI

## Recursos

- Cat Café API: http://catcafeproject.us-east-1.elasticbeanstalk.com/api-docs/

## Setup

### 1. Requisitos previos

- Python 3.10+ instalado
- Node 24 instalado
- Git instalado
  
### 2. Clonar el repositorio

```pwsh
git clone https://github.com/TestCraft-App/api-automation-agent.git
cd api-automation-agent
```

### 3. Crear y activar entorno virtual (recomendado)

PowerShell:
```pwsh
python -m venv .venv
./.venv/Scripts/Activate.ps1
```

Unix/macOS:
```bash
python -m venv .venv
source .venv/bin/activate
```

### 4. Instalar dependencias

```pwsh
pip install -r requirements.txt
```

### 5. Configurar variables de entorno (.env)

Abrir VS Code en el repo clonado
```pwsh
code .
```
Copiar el archivo example .env en VS Code y luego editarlo para colocar la API Key de Anthropic.

Para obtener la clave, ingresar a: // TODO

```
ANTHROPIC_API_KEY=CLAVE_REAL_AQUI
```

### 6. Listar endpoints disponibles

```pwsh
python ./main.py http://catcafeproject.us-east-1.elasticbeanstalk.com/swagger.json --list-endpoints
```

---

## Parte 1

Objetivo: Ejecutar el agente contra el endpoint `/adopters` usando un modo de generación del primer test para cada verbo del endpoint

### 1. Ejecutar el agente

```pwsh
python ./main.py http://catcafeproject.us-east-1.elasticbeanstalk.com/swagger.json --endpoints /adopters --generate models_and_first_test
```

### 2. Revisar los tests y modelos generados

### 3. Elegir una suite de tests de las generadas y agregarle los tests que crean necesarios

---

## Parte 2

Objetivo: Repetir la ejecución sobre `/adopters` generando múltiples tests

### 1. Ejecutar el agente

```pwsh
python ./main.py http://catcafeproject.us-east-1.elasticbeanstalk.com/swagger.json --endpoints /adopters
```

### 2. Revisar los tests generados y compararlos con los creados en la parte 1

---