## 🧰 1. Instalar Python 3.11+
**Necesario para crear y ejecutar funciones Lambda en Python**

### En Windows:
- Descargar desde: [Python Intalación Windows](https://www.python.org/downloads/windows/)
- Durante la instalación: Marcar ✅ **"Add Python to PATH"**
- Verificar instalación:
    - ```python --version```


### En macOS/Linux:
- Con Homebrew:
    - brew install python@3.1* ```* -> version de python instalada```
- O descargar desde [Python Instalación Mac](https://www.python.org/downloads/mac-osx/)
- Verficiar instalación:
    - ```python3 --version```


## 🐳 2. Instalar Docker Desktop
**Requisito para emular funciones Lambda localmente**

### Descargar:
- [Instalar Docker](https://www.docker.com/products/docker-desktop)
- Verificar: 
    - ```docker --version```


## 💻 3. Instalar Visual Studio Code (VS Code)
**IDE que se utilizará en este taller**
- [Instalar Visual Studio Code](https://code.visualstudio.com/)
- Recomendación: 
    - Instalar [AWS Toolkit](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.aws-toolkit-vscode)

## ⚙️ 4. Instalar AWS SAM CLI
### En Windows: 
- Descargar [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)
- Verificar: 
    - ```sam --version```

### En macOS/Linux:
- Desde la terminal: 
    - ```brew tap aws/tap```
    - ```brew install aws-sam-cli```
- Verificar:
    - ```sam --version```

## 💡 5. (Opcional) Instalar AWS CLI – Para despliegue
- Seguir instrucciones de [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- Verificar: 
    - ```aws --version```

## ☁️ 6. (Opcional) Crear una cuenta de AWS para desplegar funciones
**Solo si quieres desplegar tu Lambda a la nube real, necesitas una cuenta de AWS.**
- Crear cuenta de [AWS](https://aws.amazon.com/es/free)
    - **Requiere tarjeta de crédito o débito para verificar tu identidad (aunque no se te cobrará si usas el Free Tier).**
- Luego de crear la cuenta: 
    1. Inicia sesión en AWS Console
    2. Crea un usuario IAM o usa las credenciales raíz
    3. Ejecuta en tu terminal:
        - ```aws configure```
        1. Ingresa:
            - Access Key ID
            - Secret Access key
            - Región (ej. ```us-east-1```)
            - Formato de salida (opcional)
