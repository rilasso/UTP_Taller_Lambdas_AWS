## Taller 1
**Inicialización del proyecto y aprendiendo a usar eventos**

### Prerequisitos:
- Haber completado el [Manual de instalación](../README.md)
- Crear un fork del repositorio: 
    - [UTP_Taller_Lambdas_AWS](https://github.com/rilasso/UTP_Taller_Lambdas_AWS)

### Pasos a seguir: 
<details open>
<summary>
Inicialización inicial
</summary>

<br>

1. Inicializar el proyecto:
    -  Abrimos una nueva terminal en la linea de comandos y utilizamos el comando ```sam init``` para iniciar el wizard 
```shell
You can preselect a particular runtime or package type when using the `sam init` experience.
Call `sam init --help` to learn more.

Which template source would you like to use?
        1 - AWS Quick Start Templates
        2 - Custom Template Location
Choice: 
```
2. Escribimos 1 y presionamos enter.
```shell 
Choice: 1

Choose an AWS Quick Start application template
        1 - Hello World Example
        2 - Data processing
        3 - Hello World Example with Powertools for AWS Lambda
        4 - Multi-step workflow
        5 - Scheduled task
        6 - Standalone function
        7 - Serverless API
        8 - Infrastructure event management
        9 - Lambda Response Streaming
        10 - Serverless Connector Hello World Example
        11 - Multi-step workflow with Connectors
        12 - GraphQLApi Hello World Example
        13 - Full Stack
        14 - Lambda EFS example
        15 - DynamoDB Example
        16 - Machine Learning
```
3. Escribimos 1 y presionamos enter.
    - Ya que estaremos utilizando el template de "Hello World Example"
4. En el siguiente paso utilizaremos las siguientes opciones: y, n, n, n. Estas opciones indicará a SAM que utilice python como lenguaje y que no active las opciones de tracking y logeo para nuestros proyecto.
```shell
Use the most popular runtime and package type? (Python and zip) [y/N]: y

Would you like to enable X-Ray tracing on the function(s) in your application?  [y/N]: n

Would you like to enable monitoring using CloudWatch Application Insights?
For more info, please view https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch-application-insights.html [y/N]: n

Would you like to set Structured Logging in JSON format on your Lambda functions?  [y/N]: n

```
5. Por ultimo indicaremos el nombre de nuestro proyecto `helloworld`. 
```shell
Project name [sam-app]: helloworld

    -----------------------
    Generating application:
    -----------------------
    Name: helloworld
    Runtime: python3.13
    Architectures: x86_64
    Dependency Manager: pip
    Application Template: hello-world
    Output Directory: .
    Configuration file: helloworld/samconfig.toml

    Next steps can be found in the README file at helloworld\README.md


Commands you can use next
=========================
[*] Create pipeline: cd helloworld && sam pipeline init --bootstrap
[*] Validate SAM template: cd helloworld && sam validate
[*] Test Function in the Cloud: cd helloworld && sam sync --stack-name {stack-name} --watch
```
6. Esta acción creará una carpeta llamada como el nombre de tu proyecto con carpetas events, helloworld y tests. Adicional información de samconfig, templates de cloudformation y demás. Tomemos un tiempo en revisarlas y aprendarmos qué hace cada archivo.

</details>

#### **Inicio del Taller 1**

1. Ejecutemos nuestra primera función lambda en Python con el comando `sam local invoke --event events/event.json`. ¿Qué ocurre al utilizar el comando? ¿Notas algo extraño en tu Docker Desktop?

2. Modificar la lambda para que utilice eventos. 
    - Recomendación: 
        - Actualiza el events/events.json e imprime los eventos que llegan a el lambda_handler. 
    - En este caso agregaremos el siguiente campo al archivo de events.json
    `"name": "Tu Nombre",`
    - En la funcion `lambda_handler` en el app.py pondermos lo siguiente:
        `shell 
        print(f'Name: {event['name']}')
        `
3. Reto:
    - Hacer que la lambda envez de responder: 
        - `{"statusCode": 200, "body": "{\"message\": \"hello world\"}"}`
    - Retorne:
        - `{"statusCode": 200, "body": "{\"message\": \"hello Tu Nombre\"}"}`

### Al finalizar:
- Crear rama: 
    - `git checkout main` (En el caso que no estes)
    - `git checkout -b wb-nombre-apellido` 
        - Reemplazar `nombre` por su primer nombre
        - Reemplazar `apellido` por su apellido
- Subir cambios 
    - `git add .`
    - `git commit -am "Mensaje"`
    - `git push origin wb-nombre-apellido`