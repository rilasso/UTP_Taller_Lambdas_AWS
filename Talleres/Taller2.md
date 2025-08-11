## Taller 2
**Calculadora a base de eventos**

### Prerequisitos: 
- Haber completado el [Manual de instalación](../README.md)
- Haber completado el [Taller 1](https://github.com/rilasso/UTP_Taller_Lambdas_AWS/blob/main/Talleres/Taller1.md)

### Pasos a seguir: 
<details>

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
5. Por ultimo indicaremos el nombre de nuestro proyecto `calculator`. 
```shell
Project name [sam-app]: calculator

    -----------------------
    Generating application:
    -----------------------
    Name: calculator
    Runtime: python3.13
    Architectures: x86_64
    Dependency Manager: pip
    Application Template: hello-world
    Output Directory: .
    Configuration file: calculator/samconfig.toml

    Next steps can be found in the README file at calculator\README.md


Commands you can use next
=========================
[*] Create pipeline: cd calculator && sam pipeline init --bootstrap
[*] Validate SAM template: cd calculator && sam validate
[*] Test Function in the Cloud: cd calculator && sam sync --stack-name {stack-name} --watch
```
6. Esta acción creará una carpeta llamada como el nombre de tu proyecto con carpetas events, calculator y tests. Adicional información de samconfig, templates de cloudformation y demás. Tomemos un tiempo en revisarlas y aprendarmos qué hace cada archivo.

</details>

#### **Inicio del Taller 2**
1. Crear una nueva función
2. Modificar el evento para que contenga lo siguiente: 
    - Evento: 
```
{
    "numero1": 0,
    "numero2": 0,
    "funcion": "" -- suma/resta/multiplicación/división (No se usarán tildes en el request)
}
```
3. Modificar la lambda para que lea este evento y haga los calculos necesarios dependiendo de la función que se le envie.
    - Prueba y ejecuta la función con: `sam local invoke --event events/event.json`
4. Modificar la respuesta de la lambda para que devuelva: 
    - `{"statusCode": 200, "body": "{\"resultado\": \"RESPUESTA\"}"}`
5. Reto:
    - Tu lambda debe poder aceptar un numero en formato string y convertirlo a un entero
    - Mensaje de error en caso de que alguna función no este soportada.


### Al finalizar:
- Subir cambios 
    - `git add .`
    - `git commit -am "Mensaje"`
    - `git push origin wb-nombre-apellido`