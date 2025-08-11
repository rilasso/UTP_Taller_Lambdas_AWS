# Taller - Funciones Lambda con Python en AWS. 

<details open>

<summary>
Prerequisitos
</summary>

## 🧰 1. Instalar Python 3.13+
**Necesario para crear y ejecutar funciones Lambda en Python**

<details>

<summary>
En Windows:
</summary>

- Descargar desde: [Python Intalación Windows](https://www.python.org/downloads/windows/)
- Durante la instalación: Marcar ✅ **"Add Python to PATH"**
- Verificar instalación:
    - `python --version`
</details>

<details>
<summary>
En macOS/Linux:
</summary>

- Con Homebrew:
    - brew install python@3.1* `* -> version de python instalada`
- O descargar desde [Python Instalación Mac](https://www.python.org/downloads/mac-osx/)
- Verficiar instalación:
    - `python3 --version`
</details>

## 🐳 2. Instalar Docker Desktop
**Requisito para emular funciones Lambda localmente**

### Descargar:
- [Instalar Docker](https://www.docker.com/products/docker-desktop)
- Verificar: 
    - `docker --version`


## 💻 3. Instalar Visual Studio Code (VS Code)
**IDE que se utilizará en este taller**
- [Instalar Visual Studio Code](https://code.visualstudio.com/)
- Recomendación: 
    - Instalar [AWS Toolkit](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.aws-toolkit-vscode)

## ⚙️ 4. Instalar AWS SAM CLI
<details>

<summary>
En Windows:
</summary>

- Descargar [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)
- Verificar: 
    - `sam --version`
</details>

<details>

<summary>
En macOS/Linux:
</summary>

- Desde la terminal: 
    - `brew tap aws/tap`
    - `brew install aws-sam-cli`
- Verificar:
    - `sam --version`
</details>

## 💡 5. (Opcional) Instalar AWS CLI – Para despliegue
- Seguir instrucciones de [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- Verificar: 
    - `aws --version`

## ☁️ 6. (Opcional) Crear una cuenta de AWS para desplegar funciones
**Solo si quieres desplegar tu Lambda a la nube real, necesitas una cuenta de AWS.**
- Crear cuenta de [AWS](https://aws.amazon.com/es/free)
    - **Requiere tarjeta de crédito o débito para verificar tu identidad (aunque no se te cobrará si usas el Free Tier).**
- Luego de crear la cuenta: 
    1. Inicia sesión en AWS Console
    2. Crea un usuario IAM o usa las credenciales raíz
    3. Ejecuta en tu terminal:
        - `aws configure`
    4. Ingresa:
        - Access Key ID
        - Secret Access key
        - Región (ej. `us-east-1`)
        - Formato de salida (opcional)
</details>

## Diapositivas, Talleres e Información Adicional
1. [Funciones Lambda con Python en AWS](Material/Taller_UTP.pptx)
2. [Taller 1](Talleres/Taller1.md)
3. [Taller 2](Talleres/Taller2.md)
4. [AWS SAM CLI command reference](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-command-reference.html)