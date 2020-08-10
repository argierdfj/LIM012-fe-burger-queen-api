# Objetivos de aprendizaje Peer Feedback

#### EXPRESS

- [ ] [Rutas](http://expressjs.com/es/api.html#router)
    El objeto Router es una instancia aislada de middleware y rutas. Puede pensar en ella como una "miniaplicación", capaz solo de realizar funciones de middleware y enrutamiento. Cada aplicación Express tiene un enrutador de aplicaciones incorporado.
    
    Un enrutador se comporta como el middleware en sí mismo, por lo que puede usarlo como argumento para app.use () o como argumento para el método use () de otro enrutador.
    
    El objeto express de nivel superior tiene un método Router () que crea un nuevo objeto router.


- [ ] [Middlewares](http://expressjs.com/es/guide/writing-middleware.html#escritura-de-middleware-para-su-uso-en-aplicaciones-express), [Middlewares](https://platzi.com/clases/1437-express-js/15735-que-es-un-middleware-y-que-tipos-existen/)
    Las funciones de middleware son funciones que tienen acceso al objeto de solicitud (req), al objeto de respuesta (res) y a la siguiente función de middleware en el ciclo de solicitud/respuestas de la aplicación. La siguiente función de middleware se denota normalmente con una variable denominada next. 
    
    Las funciones de middleware pueden realizar las siguientes tareas:
    
    - Ejecutar cualquier código.
    - Realizar cambios en la solicitud y los objetos de respuesta.
    - Finalizar el ciclo de solicitud/respuestas.
    - Invocar el siguiente middleware en la pila.
    
    Si la función de middleware actual no finaliza el ciclo de solicitud/respuestas, debe invocar next() para pasar el control a la siguiente función de middleware. De lo contrario, la solicitud quedará colgada.


#### HTTP
- [ ] [Request](https://expressjs.com/es/4x/api.html#req)
    El obj Request representa la solicitud HTTP y tine propiedades para la cadena de consulta de solicitud, parámetros, body, HTTP headers y etc.

    El objeto [request](https://medium.com/@aarnlpezsosa/introducci%C3%B3n-a-express-js-a1ebe16dbcf4) es el primer parámetro que recibe el callback dentro del método get de express, este objeto proporciona toda la información referente a la petición: como url, parámetros, método, headers enviados por el cliente, etc.

- [ ] [Response](http://expressjs.com/es/api.html#res)
     El objeto Response representa la respuesta HTTP que envía una aplicación Express cuando recibe una solicitud HTTP.

    El objeto [HTTP Response](https://medium.com/@aarnlpezsosa/introducci%C3%B3n-a-express-js-a1ebe16dbcf4) es el segundo parámetro que recibe el callback dentro del método get de express, este objeto representa la respuesta HTTP que express envía al cliente. Proporciona diversos métodos y propiedades que facilitan el envío de respuestas al cliente como son:
    - res.send()
    - res.sendFile()
    - res.sendStatus()
    - res.render()
    - res.json()
    - res.jsonp()
    - res.set()


- [ ] [Header](https://developer.mozilla.org/es/docs/Web/HTTP/Headers)

    Las cabeceras (en inglés headers) HTTP permiten al cliente y al servidor enviar información adicional junto a una petición o respuesta. Una cabecera de petición esta compuesta por su nombre (no sensible a las mayusculas) seguido de dos puntos ':', y a continuación su valor (sin saltos de línea). Los espacios en blanco a la izquierda del valor son ignorados.

    Las Cabeceras pueden ser agrupadas de acuerdo a sus contextos:
    - **Cabecera general:** Cabeceras que se aplican tanto a las peticiones como a las respuestas, pero sin relación con los datos que finalmente se transmiten en el cuerpo.
    - **Cabecera de consulta:** Cabeceras que contienen más información sobre el contenido que va a obtenerse o sobre el cliente.
    - **Cabecera de respuesta:** Cabeceras que contienen más información sobre el contenido, como su origen o el servidor (nombre, versión, etc.).
    - **Cabecera de entidad:** Cabeceras que contienen más información sobre el cuerpo de la entidad, como el tamaño del contenido o su tipo MIME.

    **[Las cabeceras HTTP](https://developer.mozilla.org/es/docs/Web/HTTP/Messages)** para respuestas siguen también la misma estructura como cualquier otra cabecera: una cadena de texto, que no diferencia entre mayusculas y minúsculas, seguida por dos puntos (':') y un valor cuya estructura depende del tipo de cabecera. Toda la cabecera incluido su valor, se ha de expresar en una única línea. 

    - [Establecer Headers personalizados](https://expressjs.com/es/4x/api.html#setHeaders)






- [ ] [Body](https://expressjs.com/es/4x/api.html#req.body)

    Contiene pares de datos clave-valor enviados en el cuerpo de la solicitud. Por defecto es undefined y se completa cuando utiliza middleware de análisis de cuerpo como express.json()o express.urlencoded().

    [body](https://developer.mozilla.org/es/docs/Web/HTTP/Messages), la última parte del mensaje de respuesta el es 'cuerpo'. No todas las respuestas tienen uno, respuestas con un código de estado como 201 o 204 normalmente prescinden de él.

    De forma general, los cuerpos se pueden diferenciar en tres categorias:

    - Cuerpos con un único dato, consisten en un simple archivo, de longitud conocida y definido en las cabeceras: Content-Type y Content-Length.
    - Cuerpos con un único dato, consisten en un simple archivo, de longitud desconocida, y codificado en partes, indicadas con Transfer-Encoding valor chunked (que significa: 'partido' en inglés).
    - Cuerpos con múltiples datos, consisten de varios datos, cada uno con una sección distinta de información. Este caso es relativamente raro y poco común.


- [ ] [Verbos HTTP](https://developer.mozilla.org/es/docs/Web/HTTP/Methods)

    HTTP define un conjunto de métodos de petición para indicar la acción que se desea realizar para un recurso determinado. Aunque estos también pueden ser sustantivos, estos métodos de solicitud a veces son llamados HTTP verbs. Cada uno de ellos implementan una semántica diferente, pero algunas características similares son compartidas por un grupo de ellos: ej. un request method puede ser safe, idempotent, o cacheable.

    **GET**
    El método GET  solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.
    
    **HEAD**
    El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.
    
    **POST**
    El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
    
    **PUT**
    El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
    
    **DELETE**
    El método DELETE borra un recurso en específico.
    
    **CONNECT**
    El método CONNECT establece un túnel hacia el servidor identificado por el recurso.
    
    **OPTIONS**
    El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.
    
    **TRACE**
    El método TRACE  realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.
    
    **PATCH**
    El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.

- [ ] [Códigos de estatus HTTP](https://developer.mozilla.org/es/docs/Web/HTTP/Status)

    Los códigos de estado de respuesta HTTP indican si se ha completado satisfactoriamente una solicitud HTTP específica. Las respuestas se agrupan en cinco clases:
    - Respuestas informativas (100–199),
    - Respuestas satisfactorias (200–299),
    - Redirecciones (300–399),
    - Errores de los clientes (400–499),
    - y errores de los servidores (500–599).

- [ ] [Encodings y JSON]()
    [JSON](https://es.wikipedia.org/wiki/JSON) (acrónimo de JavaScript Object Notation, «notación de objeto de JavaScript») es un formato de texto sencillo para el intercambio de datos. Se trata de un subconjunto de la notación literal de objetos de JavaScript, aunque, debido a su amplia adopción como alternativa a XML, se considera (año 2019) un formato independiente del lenguaje.
    
    Una de las supuestas ventajas de JSON sobre XML como formato de intercambio de datos es que resulta mucho más sencillo escribir un analizador sintáctico (parser) para él. En JavaScript, un texto JSON se puede analizar fácilmente usando la función eval(), algo que (debido a la ubicuidad de JavaScript en casi cualquier navegador web) ha sido fundamental para que haya sido aceptado por parte de la comunidad de desarrolladores AJAX.

- [ ] [CORS](https://developer.mozilla.org/es/docs/Web/HTTP/Access_control_CORS) 
    El Intercambio de Recursos de Origen Cruzado (CORS) es un mecanismo que utiliza cabeceras HTTP adicionales para permitir que un user agent obtenga permiso para acceder a recursos seleccionados desde un servidor, en un origen distinto (dominio) al que pertenece. Un agente crea una petición HTTP de origen cruzado cuando solicita un recurso desde un dominio distinto, un protocolo o un puerto diferente al del documento que lo generó.
    
    Un ejemplo de solicitud de origen cruzado: el código JavaScript frontend de una aplicación web que es localizada en http://domain-a.com utiliza XMLHttpRequest para cargar el recurso http://api.domain-b.com/data.json.
    
    Por razones de seguridad, los exploradores restringen las solicitudes HTTP de origen cruzado iniciadas dentro de un script. Por ejemplo, XMLHttpRequest y la API Fetch siguen la política de mismo-origen. Ésto significa que una aplicación que utilice esas APIs XMLHttpRequest sólo puede hacer solicitudes HTTP a su propio dominio, a menos que se utilicen cabeceras CORS.

#### AUTH
- [ ] [JWT](https://es.wikipedia.org/wiki/JSON_Web_Token)
    JSON Web Token es un estándar abierto basado en JSON propuesto por IETF para la creación de tokens de acceso que permiten la propagación de identidad y privilegios o claims en inglés. 

- [ ] [Almacenamiento y acceso de contraseñas]()

#### SERVIDORES
- [ ] [Variables de Entorno](https://es.wikipedia.org/wiki/Variable_de_entorno)

    Una variable de entorno es una variable dinámica que puede afectar al comportamiento de los procesos en ejecución en un ordenador.
    
    Son parte del entorno en el que se ejecuta un proceso. Por ejemplo, un proceso en ejecución puede consultar el valor de la variable de entorno TEMP para descubrir una ubicación adecuada para almacenar archivos temporales, o la variable HOME o USERPROFILE para encontrar la estructura de directorios propiedad del usuario que ejecuta el proceso.
    
    Fueron introducidas en su forma moderna en 1979 con la versión 7 de Unix, por lo que están incluidas en todos los sabores y variantes del sistema operativo Unix a partir de ese momento, incluyendo Linux y macOS. Desde PC DOS 2.0 en 1982, todos los sistemas operativos de Microsoft, incluyendo Microsoft Windows y OS/2, también las han incluido como una característica, aunque con sintaxis, uso y nombres de variables estándar algo diferentes.

    [Se utilizan](https://platzi.com/clases/1759-fundamentos-node/25186-variables-de-entorno/) para los valores que no deben ir dentro del software, como credenciales: claves, tokens.
    Para crearlas accedemos al processo. ```const variableDeEntorno = process.env.NOMBREDELAVARIABLEDEENTORNO```

    Se les puede dar un valor por defecto con la expresión or || y defirnir el valor que queremos darle por defecto.
    Buenas prácticas, las variables de entorno se escriben en mayúsculas porque se basan en el estándar de los servidores de linux antiguos y de como funcionaban las configuraciones casi todas las variables de entorno que estan fuera se escribían en mayúscula y si son 2 palabras se separan con _ ```MI_WEB```.
  
    [Como usar las variables de entorno para diferente ambientes](https://platzi.com/clases/1646-backend-nodejs/22255-variables-de-entorno-cors-y-https/)
    
    Ya vimos cómo en nuestro ambiente local podemos hacer uso de las variables de entorno usando el archivo .env y la librería dotenv. Generalmente lo que se recomienda es usar el mismo para los diferentes ambientes como Staging (Pruebas) y Producción.
    
    Para ello se debe acceder al servidor remoto:
    
    Duplicar el archivo .env.example y renombrarlo por .env.
    Cargar las respectivos valores de las variables de entorno.
    Usar valores y servicios diferentes para cada ambiente, esto quiere decir que las credenciales de desarrollo, staging y producción deben ser completamente diferente.
    Si se quiere tener un backup de estos valores se recomienda usar las notas seguras de aplicaciones como 1Password o LastPass.
    Como lo hemos dicho antes no se debe hacer commit del archivo .env y este debe estar en el .gitignore, ademas se recomienda manejar solo un archivo .env. Más información: https://github.com/motdotla/dotenv#faq
    
    **Cuando no es posible acceder al servidor remoto**
    
    Algunos servicios como Heroku o Now no nos permiten acceder a un servidor remoto pues la administración del servidor es controlada por los mismos servicios, sin embargo cada servicio tiene sus mecanismos para establecer las variables de entorno:
    
    - Configuración de variables de entorno en Heroku
    - Configuración de variables de entorno en Now

    **Variables de entorno de forma nativa**

    El uso del archivo .env junto con la biblioteca dotenv es un mecanismo que nos facilita la configuración de variables de entorno pero si por alguna razón las quisiéramos cargar de manera nativa, es decir desde el sistema operativo recomiendo este tutorial de Digital Ocean

- [ ] [SSH](https://es.wikipedia.org/wiki/Secure_Shell)
    SSH (o Secure SHell) es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada. Además de la conexión a otros dispositivos, SSH permite copiar datos de forma segura (tanto archivos sueltos como simular sesiones FTP cifradas), gestionar claves RSA para no escribir contraseñas al conectar a los dispositivos y pasar los datos de cualquier otra aplicación por un canal seguro tunelizado mediante SSH y también puede redirigir el tráfico del (Sistema de Ventanas X) para poder ejecutar programas gráficos remotamente. El puerto TCP asignado es el 22.

- [ ] [SSH Keys](https://www.nettix.com.pe/documentacion/soporte-documentacion/que-son-las-llaves-ssh-o-ssh-keys#:~:text=Una%20clave%20SSH%20es%20uno,autenticaci%C3%B3n%20de%20clave%20p%C3%BAblica%20SSH.&text=Las%20claves%20SSH%20vienen%20en,una%20contrase%C3%B1a%20de%20617%20d%C3%ADgitos.)

    Una clave SSH es uno de los dos archivos utilizados en un método de autenticación conocido como autenticación de clave pública SSH. En este método de autenticación, un archivo (conocido como la clave privada) generalmente se mantiene en el lado del cliente y el otro archivo (conocido como la clave pública) se almacena en el lado del servidor.
    
    No hay dos pares de claves SSH iguales. Entonces, en teoría, puede usar un par para la autenticación. Así es como funciona:
    
    Las claves SSH vienen en muchos tamaños, pero una opción popular es un cifrado RSA de 2048 bits, que es comparativo con una contraseña de 617 dígitos. En los sistemas Windows, es posible generar su propio par de claves SSH descargando y utilizando un cliente SSH como PuTTY. En sistemas Mac y Linux, es posible generar un par de claves SSH usando una ventana de terminal. Mire el video a continuación para descubrir cómo generar su propio par de claves RSA en Mac y Linux.

- [ ] [VPS](https://es.wikipedia.org/wiki/Servidor_virtual_privado)
    Un servidor virtual privado (VPS, del inglés virtual private server) es un método de particionar un servidor físico en varios servidores virtuales (máquinas virtuales con tareas de servidor) de tal forma que todo funcione como si se estuviese ejecutando en una única máquina. Cada servidor virtual es capaz de funcionar bajo su propio sistema operativo y además cada servidor puede ser reiniciado de forma independiente.
    
    La práctica de particionar un único servidor físico para que funcione como varios servidores virtuales ya comenzó con los mainframes y ha vuelto a resurgir con el desarrollo de la virtualización y las tecnologías para otras arquitecturas.
    
    Al funcionar un VPS con su propia copia del sistema operativo, los clientes tienen nivel de acceso root o de superusuario y por tanto, pueden instalar cualquier tipo de software que pueda ser ejecutado bajo este sistema operativo. Algunos programas no ejecutan bien en entornos virtuales, incluyendo firewalls, clientes antivirus e incluso otras herramientas virtuales; algunos VPS proveen fuertes restricciones, pero generalmente son laxas comparadas con las que existen en los servidores de almacenamiento compartido. Debido a que varios clientes (virtuales) pueden trabajar sobre una sola máquina, un VPS normalmente tiene ciertas limitaciones en cuanto al tiempo de procesamiento, RAM y espacio en el disco.

#### BBDD
- [ ] [Instalación]()
- [ ] [Conexión a través del cliente]()
- [ ] [Conection String]()
- [ ] [Queries y comandos]()

#### DESPLIEGUE
- [ ] [Contenedores](https://msaffirio.wordpress.com/2018/07/23/contenedores-containers/)
    Los Contenedores [–Containers–](https://www.cio.com/article/2924995/what-are-containers-and-why-do-you-need-them.html) son una solución al problema de cómo hacer que el software se ejecute confiablemente cuando se traslada de un entorno informático a otro. Esto podría ser desde la computadora portátil de un desarrollador a un entorno de prueba, desde un entorno de transición al de producción, y tal vez desde una máquina física en un centro de datos a una máquina virtual en una nube privada o pública [1].
    
    Los Contenedores son un método de virtualización de un sistema operativo que permite ejecutar una aplicación junto con sus elementos dependientes, en un ambiente aislado e independiente. Los Contenedores permiten empaquetar fácilmente el código, las configuraciones y las dependencias de una aplicación en bloques fáciles de usar que ofrecen consistencia ambiental, eficiencia operativa, productividad para el desarrollador y control de versiones.
    
    Los [Contenedores](https://aws.amazon.com/es/containers/) pueden ayudar a garantizar que las aplicaciones se implementen de manera más rápida, confiable y consistente, independientemente del entorno de ejecución o despliegue. Los Contenedores también permiten un control más detallado de los recursos, lo que le brinda una mayor eficiencia en el uso de la infraestructura computacional [2].

- [ ] [Docker](https://es.wikipedia.org/wiki/Docker_(software))
    Docker es un proyecto de código abierto que automatiza el despliegue de aplicaciones dentro de contenedores de software, proporcionando una capa adicional de abstracción y automatización de virtualización de aplicaciones en múltiples sistemas operativos.1​Docker utiliza características de aislamiento de recursos del kernel Linux, tales como cgroups y espacios de nombres (namespaces) para permitir que "contenedores" independientes se ejecuten dentro de una sola instancia de Linux, evitando la sobrecarga de iniciar y mantener máquinas virtuales.2​

- [ ] [Docker compose](https://riptutorial.com/es/docker-compose)
    Compose es una herramienta para definir y ejecutar aplicaciones Docker de múltiples contenedores. Con Compose, utiliza un archivo Compose para configurar los servicios de su aplicación. Luego, utilizando un solo comando, creará e iniciará todos los servicios desde su configuración. Para obtener más información sobre todas las funciones de Compose, consulte la lista de funciones.
    
    Usar Compose es básicamente un proceso de tres pasos.

    1. Defina el entorno de su aplicación con un Dockerfile para que pueda reproducirse en cualquier lugar.
    2. Defina los servicios que conforman su aplicación en docker-compose.yml para que puedan ejecutarse juntos en un entorno aislado.
    3. Por último, ejecute docker-compose up y Compose se iniciará y ejecutará toda la aplicación.