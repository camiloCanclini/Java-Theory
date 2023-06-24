![SpringBoot](https://4.bp.blogspot.com/-ou-a_Aa1t7A/W6IhNc3Q0gI/AAAAAAAAD6Y/pwh44arKiuM_NBqB1H7Pz4-7QhUxAgZkACLcBGAs/s1600/spring-boot-logo.png)

# Spring Boot

Spring Boot es un framework de desarrollo de aplicaciones Java que se basa en el framework Spring y tiene como objetivo principal simplificar y agilizar el proceso de creación de aplicaciones empresariales. Proporciona una infraestructura y una configuración por defecto inteligentes, lo que permite a los desarrolladores enfocarse en la implementación de la lógica de negocio en lugar de perder tiempo en la configuración manual.

Spring Boot adopta una filosofía de "opinión sobre la configuración", lo que significa que proporciona valores predeterminados sensibles y configuración automática basada en convenciones para muchos aspectos comunes de las aplicaciones, como el acceso a bases de datos, la configuración de servidores web, la seguridad, el manejo de transacciones, entre otros.



## Spring Y Spring Boot

Aunque en un inicio puede parecer que estemos hablando de la misma tecnologia la realidad es otra, mientras que **Spring** es un marco de desarrollo de aplicaciones empresariales más general, **Spring Boot** es una capa de abstracción adicional que se construye sobre **Spring** y proporciona características adicionales para facilitar y agilizar el desarrollo de aplicaciones **Spring**. **Spring Boot** se enfoca en la opinión sobre la configuración, la conveniencia y la autoconfiguración, lo que lo hace especialmente útil para desarrollar aplicaciones rápidas y eficientes.

![](https://1.bp.blogspot.com/-4vTgRx2HlTE/YN9IoM8gMzI/AAAAAAAAuTk/Qk-GDPUDTEENOmwhl04bZLq65PrZUwBTACLcBGAsYHQ/s2048/Spring%2BEcosystem.png)

> Spring Boot facilita la creación de aplicaciones basadas en Spring independientes y de grado de producción que puede "simplemente ejecutar". Tomamos una opinión obstinada de la plataforma Spring y las bibliotecas de terceros para que pueda comenzar con el mínimo esfuerzo. La mayoría de las aplicaciones de Spring Boot necesitan una configuración mínima de Spring.


## Caracteristicas

* Cree aplicaciones Spring independientes

* Incruste Tomcat, Jetty o Undertow directamente (no es necesario implementar archivos WAR)

* Proporcione dependencias "iniciales" obstinadas para simplificar su configuración de compilación

* Configure automáticamente Spring y bibliotecas de terceros siempre que sea posible

* Proporcione funciones listas para producción, como métricas, controles de estado y configuración externalizada

* Absolutamente sin generación de código y sin requisitos para la configuración XML

## Iniciar Proyectos

Para inciar nuestro proyectos con Spring Boot podemos hacer uso de la herramienta que nos provee la siguiente url: [https://start.spring.io/](https://start.spring.io/)

Aqui encontraremos una interfaz grafica que nos facilitara la creacion y parte de la configuracion de nuestro proyecto con Spring Boot. Entre las cosas que podemos seleccionar se encuentran:

* El manejador de dependencias, ya sea, Maven o Gradel.
* La version de Spring Boot
* La informacion de nuestro proyecto (metadatos)
* El tipo de empaquetamiento que tendra nuestro projecto, puede ser JAR o WAR
* La version de Java
* Y por ultimo las dependencias que deseemos agregarle a nuestro proyecto

## Como Funciona Spring Boot

La forma en la que podemos consebir a este framework, es como MVC (Modelo Vista Controlador). MVC es un patrón de arquitectura de software que divide una aplicación en tres componentes principales: el "**Modelo**" que representa los datos y la lógica de negocio, la "**Vista**" que muestra la información al usuario y el "**Controlador**" que maneja las interacciones y coordina la comunicación entre el Modelo y la Vista. El uso de MVC promueve la separación de preocupaciones, facilita el mantenimiento y fomenta la reutilización de código en el desarrollo de aplicaciones.

![](https://i.ytimg.com/vi/gtBS7HKfy-k/maxresdefault.jpg)

![](https://shreysharma.com/wp-content/uploads/2019/04/mvc.webp)

## Anotaciones Spring Boot

Concretamente para trabajar con el patron mostrado anteriormente deberemos hacer uso de las anotaciones de Java.

Las anotaciones en Java son metadatos que se agregan a clases, métodos, campos u otros elementos de un programa Java para proporcionar información adicional o instrucciones al compilador, herramientas de desarrollo o tiempo de ejecución. Las anotaciones se representan con un prefijo @ seguido del nombre de la anotación y se colocan antes del elemento al que se aplican. Permiten agregar información adicional, como configuraciones, restricciones, comportamiento especializado o documentación, para facilitar el desarrollo, la depuración y el mantenimiento del código.

### Ejemplos

```java
public class ExampleClass {

    @Deprecated
    private int oldField;

    @Override
    @SuppressWarnings("unchecked")
    public void someMethod() {
        // Código del método
    }

    @CustomAnnotation(value = "example")
    public void customAnnotatedMethod() {
        // Código del método
    }
}
```

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
public class SpringBootExampleApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringBootExampleApplication.class, args);
    }
}

@RestController
class HelloController {

    @GetMapping("/hello")
    public String hello() {
        return "Hola, mundo!";
    }
}
```

### Lista Anotaciones

* **@SpringBootApplication:** Esta anotación se utiliza en la clase principal de una aplicación Spring Boot y combina varias anotaciones, incluyendo @Configuration, @EnableAutoConfiguration y @ComponentScan. Configura automáticamente la aplicación y habilita la configuración automática de Spring Boot.

* **@RestController:** Esta anotación se utiliza para marcar una clase como un controlador REST. Combina las anotaciones @Controller y @ResponseBody, lo que significa que los métodos de la clase devuelven directamente datos en formato JSON o XML como respuesta HTTP.

* **@RequestMapping:** Esta anotación se utiliza para mapear una URL o una ruta de solicitud a un método específico en un controlador. Puedes especificar el método HTTP, los parámetros y otras opciones de configuración.

* **@Autowired:** Esta anotación se utiliza para inyectar automáticamente dependencias en una clase. Se puede aplicar en constructores, métodos setter o directamente en los campos.

* **@Component:** Esta anotación se utiliza para marcar una clase como un componente de Spring. Es la anotación base para otras anotaciones como @Controller, @Service y @Repository. Spring detecta automáticamente los componentes marcados con @Component y los registra en el contexto de la aplicación.

* **@Service:** Esta anotación se utiliza para marcar una clase como un servicio de negocio. Proporciona una semántica clara para distinguir la capa de servicio de otras capas, como el controlador o la capa de acceso a datos.

* **@Repository:** Esta anotación se utiliza para marcar una clase como un repositorio de datos. Se utiliza en la capa de acceso a datos y se encarga de interactuar con la base de datos o cualquier otro almacenamiento de datos.

* **@Configuration:** Esta anotación se utiliza para marcar una clase como una fuente de configuración de Spring. Puede contener métodos anotados con @Bean, que se utilizan para configurar y registrar los componentes en el contexto de la aplicación.

* **@Transactional:** Esta anotación se utiliza para marcar un método o clase como transaccional. Se encarga de administrar las transacciones en métodos anotados, asegurando que se realicen todas las operaciones dentro de una transacción única.

* **@Valid:** Esta anotación se utiliza para habilitar la validación de los objetos de entrada en un controlador. Junto con anotaciones de validación como @NotNull, @Min, @Max, permite validar y verificar los datos de entrada antes de procesarlos.

### GetMapping y PostMapping

`@GetMapping` y `@PostMapping` son anotaciones utilizadas en Spring Boot para mapear métodos de controlador a las solicitudes HTTP GET y POST, respectivamente. Aquí te explico más sobre cada una de ellas:

`@GetMapping`: Esta anotación se utiliza para mapear un método de controlador a una solicitud HTTP GET. Indica que el método se ejecutará cuando se realice una solicitud GET a una URL específica. Puedes especificar la URL o la ruta de solicitud utilizando la anotación @GetMapping seguida de la URL entre comillas. Por ejemplo:

```java
@GetMapping("/ruta")
public String metodoGet() {
    // Código del método
}
```

`@PostMapping`: Esta anotación se utiliza para mapear un método de controlador a una solicitud HTTP POST. Indica que el método se ejecutará cuando se realice una solicitud POST a una URL específica. Puedes especificar la URL o la ruta de solicitud utilizando la anotación @PostMapping seguida de la URL entre comillas. Por ejemplo:

```java
@PostMapping("/ruta")
public String metodoPost() {
    // Código del método
}
```

Ambas anotaciones son útiles para definir los controladores REST en una aplicación Spring Boot y especificar cómo deben responder a las solicitudes HTTP GET y POST. Puedes utilizar otros métodos de anotación similares, como @PutMapping, @DeleteMapping, entre otros, para mapear métodos a otros tipos de solicitudes HTTP.