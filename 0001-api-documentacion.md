# Swagger

Fecha de comienzo: 03 de Noviembre del 2022
Fecha de terminado: 

Autores:
 - @reynaldoverdugomacropay

## 1 TL;DR

<!--
párrafo corto que explica qué estas proponiendo
-->
Agregar en nuestras API's un framework|herramientas para documentarlas mediante una investigación.

## 2 Motivación

<!--
¿qué motiva esta decisión y por qué es importante?
el propósito de esta sección es articular de una manera sencilla el valor de la decision que vamos a tomar
-->

Nuestra empresa se encuentra en constante crecimiento creando o actualizando API's. Por lo tanto al documentarlas, tendremos las siguientes ventajas:

  - Entendimiento de cada una de nuestras API's.
  - Mejor toma de decisiones y ahorro de tiempos en productividad, ya que al conocer nuestras API's podemos re-utilizarlas siempre y cuando se de el caso.
  - Mejora de tiempos de productividad en el areá de Middleware, ya que cualquier pregunta, duda pueden consultar a la documentación del API.
  - Interfraz gráfica amigable para que las aréas externas puedan entender con facilidad. 

## 3 Propuesta de implementación

<!--
Este es el núcleo de tu propuesta, y su proposito es ayudarte a pensar en la solución. Esto debe ser un wireframe, no un documento perfecto con todos los detalles.

Escribir es pensar https://medium.learningbyshipping.com/writing-is-thinking-an-annotated-twitter-thread-2a75fe07fade

  - usa diagramas para ilustrat tus ideas o flujos
  - inluye ejemplos de código si estas proponiendo una interfaz o contrato de sistemsa nuevo
  - agrega links con las especificaciones de proyectos

El proposito de esta sección se resume en:
"Esta es la dirección en la que nos voy a llevar, alguién ve huecos en mi propuesta o tiene comentarios sobre cómo mejorarla?

 -->
 
Actualmente se cuentan con templates para diferentes tipos de proyectos dependiendo del requerimiento y lenguaje o de la forma que se requiere el despliegue en aws.
  - Basado en eso templates se pueden modificar para incluir la documentacion con la api/libreria que se necesite dependiendo del caso.
  - Hay templates basados en lenguajes diferentes como lo son: NodeJs, Php, Java; Phyton, C#
  - Al igual que documentar las apis, habría que poner informacion en el readme para que el equipo de DevOps pueda realizar despliegues sin detalle alguno.

Las propuestas para el uso de la documentación dentro de los proyectos en desarollo se encuentran: 
  - Swagger: Es una serie de reglas, herramientas y especificaciones que ayudan con la documentacion de las apis. Esta permite crear una documentacion bastante completa para que el resto de los integrantes del equipo puedan entenderla.
  Maneja una intefaz grafica que permite visualizar las apis asi como los comentarios y hacer pruebas para ver el funcionamiento de las mismas. Asi mismo muestra que mensajes puede mostrar en diversos tipos de caso. Funciona generando una sanbox con la definicion apartir del swagger.json pero haciendo la conversion primero desde Swagger.yaml
      - Url: https://swagger.io/
      - Roles:
          - Customers: Son los que tienen acceso a la documentacion y pueden probar las funciones de la Api
          - Designers: Son los que pueden crear, editar, comentar en la Api, en pocas palabras son los colaboradores del proyecto.

  La propuesta cuenta con varias Ventajas:
   -  Es de las mas utilizadas
   -  Es compatible con node Js.
   -  Si es Node Js es gratis el uso de swagger.
   -  La interfaz permite ver parte del codigo, asi como es muy amigable para el usuario
   -  Permite ver los metodos de ingreso de datos y ver que recibe y que envia.
   -  Permite versionado de Apis
   
El Swagger se expondría en la ruta del API mediante "/docs" en los proyectos anteriores, futuros hechos con Node JS.
## 4 Métricas

<!--
Que métricas debemos vamos a instrumentar, o monitorear para observar las implicaciónes de esta decisiòn?
Por ejemplo, cuando interactuamos con un sistema externo que tipo de latencia esperariamos o si agregamos una tabla nueva que tan rápido se llenaría?
-->
Uno de los grandes inconvenientes es que los aplicativos y requerimientos estan hechos en diferentes lenguajes, la opcion de centralizar dichos proyectos llevaria mas tiempo del que se dispone para cada proyecto. Para ello la propuesta de centralizar en un solo tipo de lenguaje se veria beneficiada para los aplicativos nuevos, ya que esto facilitaria mucho la compresion de los proyectos, mientras que los que ya estan en produccion se podrian mantener como estan hasta que se les permita hacer un rediseño, adaptandolo a las nuevas tecnologias que se estan implementando y al marco de trabajo.

Parte de los proyectos anteriores hechos antes del cambio realizado por la empresa, presentan un tiempo de respuesta algo lento, pero se habla de proyectos grandes que ya estan siendo usados por el usuario final, lo cual hacerle un rediseño por el momento no es conveniente, por lo cual la propuesta seria bienvenida por los nuevos aplicativos. Y los aplicativos que ya cuenten con el marco de trabajo actual.

## 5 Riesgos e inconvenientes

<!--
¿Hay razones por las que no deberiamos hacer esto?
¿Qué riesgos estamos tomando? Por ejemplo, no tenemos experiencia con esta tecnología nueva o no entendemos la escala aún.
-->
A su vez la propuesta con ciertas desventajas:
- No es compatible con muchos lenguajes
- Al no ser compatible con swagger un lenguaje es necesario hacer uso de swaggerhub el cual tiene un precio.
- Solo da 14 dias gratis de uso de swagger hub
- Para tener mas colaboradores se debe ampliar el plan que se paga por mes
- Los empleados no conocen del todo esta nueva tecnologia
- No se cuentan con plantillas donde se implemente.
- Un cambio grande en la manera de manejar los proyectos
- Hay proyectos ya hechos y que se encuentran en produccion que hacerles cambio requeriria hacer despliegues nuevamente.

Los costos aplican para swagger hub, cuando se intente implementar en un lenguaje que no soporte.
Costos:
Por Mes:
  -  $90 USD/Mes: 3 Designers/6 Consumers
  -  $150 USD/Mes: 5 Designers/10 Consumers
  -  $300 USD/Mes: 10 Designers/20 Consumers
Por Año:
  -  $75 USD/Mes: 3 Designers/6 Consumers
  -  $125 USD/Mes: 5 Designers/10 Consumers
  -  $250 USD/Mes: 10 Designers/20 Consumers

## 6 Alternativas
Para poder llevar acabo estas tarea de la documentación de aplicaciones tenemos diferentes alternativas que pueden cubrir las funciones que swagger realiza.

- RAML: Lenguaje de definicion para apis que se basan en http, una aplicacion del formato YAML 1.2, el cual faciliya la documentacion de api Rest y las mantiene sincronizada. Proporcionando la informacion necesaria para poder describir las API RESTful/ RESTful, fomentando la reutilizacion de codigo.
    - Url: https://raml.org/

- Oracle+Apiary: Al igual que Swagger esta es una alternativa bastante llamativa, funciona de la misma manera, pero teniendo en cuenta que esta ligada con oracle. donde se pueden visualizar mas de un proyecto, y cuenta con conexion a github.
    - Url: https://apiary.io/
- FastApi: Una api de de python que facilita la codificacion asi como la documentacion minimizando incluso la duplicacion de codigo dentro del proyecto. Esta debe instalarse directamente en los proyectos python para poder hacer uso de ella, ademas de ir a la par con node js.
    - Url: https://fastapi.tiangolo.com/es/


<!--
¿Hay otras formas de resolver éste problema?
-->

## 7 Impacto potencial y dependencias

<!--
  ¿Qué otros sistemas se verán afectados con esta propuesta?
  ¿Qué consideraciones de seguridad debemos tener?¿Como pueden explotar esta parte del sistema?
  ¿Que impacto tiene esta decision sobre soporte al cliente?

  Aquí buscamos ser concientes del ambiente en el que operamos y generar empatía hacia otros que pueden verse afectados por nuestra decisión.
 -->

- RAML:
    - Ventajas:
        - Proporciona documentacion interactiva.
        - compatible con Node Js y Php
        - Permite tener el control en la documentacion
        - Es de codigo abierto.
        - Tiene soporte solido
        - Fomenta la reutilizacion de Codigo
        - Permite el descubrimiento de mejores practicas de codificacion.
        - Permite centrarse directamente en el "contrato" que ofrece el endpoint
        - La metodologia que emplea permite facilitar el testing aportando el entorno perfecto para usar TDD.
        - Puede convertir su especificacion a OPENAPI(Swagger)

    - Desventajas:
        - Lenguaje es tipo mobile
        - No compatible con muchos Lenguajes
        - Documentacion completamente en ingles
        - No todos los proyectos estan hechos con html, php o Node JS
        - Los programadores no utilizan siempre la misma tecnologia en los requerimientos

- Oracle+Apiary:
    - Ventajas:
        - Conexion con github.
        - sincronizacion de proyectos con github.
        - Permite el uso gratuito de manera ilimitada, pero esta restringido con ciertas caracteristicas.
        - Permite controlar quienes son colaboradores y quienes solo pueden visualiar
    - Desventajas:
        - Actualmente la compra de planes es confuso.
        - Los planes de pago que manejaba estan obsoletos
        - Se tiene que comprar una suscripcion a Oracle Cloud
        - El modo gratuito solo permite 5 editores y 10 viewers
        - No compatible con muchos Lenguajes
- FastApi:
    - Ventajas:
        - Documentacion en diferentes idiomas incluyendo español
        - Ayuda a crear codigo para produccion con documentacion interactiva
        - Previene mas los errores humanos
        - Facil de usar
        - Intuitivo
        - Basado en estandares como Swagger
    - Desventajas:
        - Esta api/libreria solo es para python
        - No todos los proyectos estan hechos en phyton
        - Los desarrolladores deberan acostumbrarse a este nuevo marco de trabajo
        - Podria retrasar los proyectos cuando el desarrollador no conozca de este lenguaje.

- Comparacion de Precios


| Tipo   | De Paga? | Mensual  | Anual | Panel | Cloud? | Comentario |
| :---:  |  :---:  | :---: | :---:  |  :---:  | :---: | :---: |
| Swagger |   ❌    |  Free  |   Free  |   ❌   |    ❌   | Al ser solo Swagger no tiene costo |
| Swagger Hub |    ✔    |  Planes de $90, $150, $300 USD  |   Planes de $75, $125, $250 USD  |   ✔   |    ✔   | Dependiendo del plan es la cantidad de Designers y Consumers y el mas completo para documentacion y facilidad de pruebas, Los costos aplican para swagger hub |
| RAML  |    ❌    |   Free   |   Free   |    ❌    |    ❌    | No cuenta con un panel administrativo de las api, codigo abierto|
| APIARY |   ❌ Obsoleto   |  Free  |   Free  |   ✔   |    ✔   | Esta gratuito pero esta limitado con muchas cosas|
| FASTAPI  |    ❌    |   Free   |   Free   |    ❌    |    ❌    | No cuenta con un panel administrativo de las api|



## 8 Preguntas sin resolver

<!--
¿ Qué preguntas no hemos resuelto?
-->
  - ¿Estamos dispuestos a manejar diferentes tipos de documentacion si se trata de aplicativos que sean incompatibles con la propuesta?
  - ¿Que sucedera con los proyectos previos?
  - ¿Se usara una misma estructura?

## 9 Conclusión
En conclusión, la opción mas viable y factible es Swagger para el manejo de la documentación de las Api Rest, debido a que pese a los costos nos facilita y brinda mas herramientas que solo el uso de la api via codigo, al implementar solo swagger no tendria ningun costo, ademas al contratar Swagger Hub esto nos permitira que en las configuraciones se le pueda proporcionar al equipo de QA los roles de Consumers para poder realizar pruebas, mientras que al equipo de desarrollo se le otorga el de Designers. Tambien por que el panel que maneja es el que permite realizar pruebas directamente con lo que se tiene.
Permite el versionado de las aplicaciones, ademas de ser el mas estandar de todos ya que la gran mayoria de librerias/apis se basan en este como un estandar.
Es de los mas usados al igual que de los mas conocidos, es por eso que la opcion mas viable y sin limitacion o problematica es Swagger, pero puede verse solucionado el problema con Swagger Hub, ya que se trabajo detras del codigo principal.
A pesar de las desventajas que pueda haber utilizando swagger, que se puede solucionar con Swagger Hub nos da mas beneficios por que nos proporciona mas control sobre los proyectos. Y al ofrecer un sistema de roles esto permite terner mayor seguridad sobre nuestros desarrollos.
Aparte de contar con la documentacion en español, lo cual es conveniente ya que no todos tienen un ingles tan fluido. Swagger es bastante conveniente, ya que varios lideres de proyectos han trabajado con swagger con anterioridad y esto permitiria centralizar y estructurar bien el manejo de la documentacion con el resto de los programadores.

Por que Swagger y no RAML, Swagger cuenta con Swagger Hub que es el que permite realizar pruebas de las aplicaciones deleccionando nel poyecto, asi como tiene una documentacion solida a comparacion de RAML, cuenta con una comidad bastante activa para la base de apoyo.
Cuenta con un soporte muy pobre para las versiones mas nuevas, ademas de queswagger tiene una gran ventaja sobre raml ya que esta diseñado como una especificacion de abajo hacia arriba mientras que RAML es todo lo contrario, Raml sobresale sobre el ciclo de vida de la api, mientras que swagger especifica que comportamiento afecta a la api a la hora de crear sistemas entrelazados y complejos.
Ademas que la interfaz grafica de Swagger permite tener un mejor control sobre los proyectos. Aparte de que swagger soporta documentaciones robustas mientras que RAML no puede.