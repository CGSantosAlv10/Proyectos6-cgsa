# Proyecto Integrador: Automatización de Pruebas Web con Serenity BDD y Screenplay

## 1. Descripción del proyecto

Este proyecto consiste en la automatización de pruebas funcionales de la plataforma web [DemoBlaze](https://www.demoblaze.com/), utilizando el patrón de diseño Screenplay y el enfoque de desarrollo guiado por comportamiento (BDD).

Se implementaron escenarios automatizados para validar las principales funcionalidades de la plataforma, desde el registro e inicio de sesión hasta la selección de productos y su incorporación al carrito de compras.

## 2. Tecnologías utilizadas

- **Java 21:** lenguaje de programación.
- **Maven:** gestión de dependencias y construcción del proyecto.
- **Serenity BDD 4.0.3:** generación de reportes de pruebas automatizadas.
- **Selenium WebDriver:** interacción automatizada con el navegador.
- **Cucumber:** definición y ejecución de escenarios BDD.
- **Screenplay:** patrón de diseño para organizar las pruebas.
- **JUnit 4:** ejecución de pruebas.
- **PMD y CPD:** análisis de calidad y detección de código duplicado.
- **SpotBugs y FindSecBugs:** análisis de posibles errores y vulnerabilidades.

## 3. Estructura del proyecto

```text
AutoWeb_SantosAlvarez/
│
├── src/
│   ├── main/
│   │   ├── java/org/example/
│   │   │   ├── Pages/
│   │   │   │   ├── CartPage.java
│   │   │   │   ├── HomePage.java
│   │   │   │   └── ProductPage.java
│   │   │   │
│   │   │   ├── Questions/
│   │   │   │   ├── CartDetails.java
│   │   │   │   ├── ProductDetails.java
│   │   │   │   └── ResponseCode.java
│   │   │   │
│   │   │   ├── Tasks/
│   │   │   │   ├── AddProductToCart.java
│   │   │   │   ├── LogIn.java
│   │   │   │   ├── NavigateHome.java
│   │   │   │   ├── NavigateToCart.java
│   │   │   │   └── NavigateToProduct.java
│   │   │   │
│   │   │   ├── Utils/
│   │   │   │   ├── Parameters.java
│   │   │   │   ├── PreAndProsCondition.java
│   │   │   │   ├── ScreenShot.java
│   │   │   │   └── TestData.java
│   │   │   │
│   │   │   └── Main.java
│   │   │
│   │   └── resources/
│   │
│   └── test/
│       ├── java/org/example/
│       │   ├── StepDefinitions/
│       │   │   ├── AgregarAlCarrito.java
│       │   │   ├── IniciarSesion.java
│       │   │   ├── ParameterDefinition.java
│       │   │   ├── RegistrarUsuario.java
│       │   │   └── SeleccionarProducto.java
│       │   │
│       │   └── RunnerTest.java
│       │
│       └── resources/
│           ├── features/
│           │   ├── 01_registrar_new.feature
│           │   ├── 02_login.feature
│           │   ├── 03_seleccionar_producto.feature
│           │   └── 04_agregar_carrito.feature
│           │
│           └── serenity.conf
│
├── pom.xml
└── README.md
```

## 4. Funcionalidades automatizadas

El proyecto contempla cuatro escenarios principales:

### 4.1. Registro de usuario
Se verifica el proceso de registro de un nuevo usuario en la plataforma, ingresando las credenciales correspondientes y comprobando el mensaje de respuesta.

### 4.2. Inicio de sesión
Se automatiza el acceso a la plataforma mediante las credenciales de un usuario y se comprueba que el inicio de sesión se realice correctamente.

### 4.3. Selección de productos
Se navega por la categoría Laptops, se selecciona el producto Sony vaio i5 y se verifican sus datos principales: nombre, precio y descripción.

### 4.4. Agregar productos al carrito
Se selecciona el producto Sony vaio i5, se incorpora al carrito de compras y se comprueba tanto el mensaje de confirmación como la presencia del producto en el carrito.

## 5. Requisitos previos

Para ejecutar el proyecto se necesita:

- JDK 17 o superior (el proyecto fue desarrollado y probado con Java 21).
- Apache Maven.
- Navegador web compatible con Selenium.
- Conexión a Internet.

## 6. Ejecución del proyecto

Para ejecutar todas las pruebas automatizadas, utilizar el siguiente comando desde la raíz del proyecto:

```bash
mvn clean verify
```

Para ejecutar una funcionalidad específica, se puede utilizar el filtrado por etiquetas:

```bash
mvn clean verify "-Dcucumber.filter.tags=@RegistrarNew"
```

También se pueden utilizar las etiquetas `@Login`, `@SeleccionarProducto` y `@AgregarCarrito`.

## 7. Reportes y evidencias

Serenity BDD genera un reporte HTML con los resultados de la ejecución, permitiendo revisar los escenarios ejecutados, sus pasos y evidencias disponibles.

El reporte se encuentra en:

```text
target/site/serenity/index.html
```

Asimismo, el proyecto utiliza las clases `ScreenShot.java` y `PreAndProsCondition.java` para gestionar la captura y organización de evidencias durante la ejecución de las pruebas.

## 8. Resultados de las pruebas

En la última ejecución completa del proyecto se obtuvieron los siguientes resultados:

| Indicador | Resultado |
|---|---:|
| Escenarios ejecutados | 4 |
| Pruebas aprobadas | 4 |
| Pruebas fallidas | 0 |
| Pruebas con errores | 0 |
| Porcentaje de aprobación | 100 % |
| Estado de construcción | BUILD SUCCESS |

## 9. Análisis de calidad del código

El proyecto incorpora herramientas de análisis estático para evaluar la calidad del código:

- **PMD:** permite identificar posibles problemas en la estructura y escritura del código.
- **CPD:** detecta fragmentos de código duplicados.
- **SpotBugs:** analiza posibles errores en la implementación.
- **FindSecBugs:** complementa el análisis mediante la identificación de posibles vulnerabilidades de seguridad.

En la última ejecución de `mvn clean verify`, las verificaciones de PMD y CPD finalizaron correctamente. SpotBugs también completó el análisis sin errores ni advertencias.

## 10. Conclusión

El proyecto permitió implementar un conjunto de pruebas automatizadas para validar cuatro funcionalidades de la plataforma DemoBlaze, aplicando Serenity BDD, Selenium, Cucumber y el patrón Screenplay.

La ejecución completa obtuvo cuatro escenarios aprobados y permitió generar un reporte de resultados mediante Serenity BDD. Además, se incorporaron herramientas de análisis estático para complementar la evaluación de la calidad del código.