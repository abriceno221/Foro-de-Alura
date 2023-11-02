<h1 align="center" id="titulo-e-imagen-de-portada"> FORO ALURA 💻</h1>

<div align="center" id="titulo-e-imagen-de-portada">
        <img src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/bbb347ba-edd5-4d23-84c2-d4d26d092ea8">
</div>
<br>

<div align = "center" id="insignias">
    <span style="display: inline-block;">
        <img alt="Static Badge" src="https://img.shields.io/badge/relase%20date-november2023-green">
        <img alt="Static Badge" src="https://img.shields.io/badge/JavaSE17-purple">
        <img alt="Static Badge" src="https://img.shields.io/badge/status-finished-red">     
    </span>
</div>

<br>

<h2 id="indice">Índice</h2>

<ol>
    <li><a href="#titulo-e-imagen-de-portada">Título e imagen de portada</a></li>
    <li><a href="#insignias">Insignias</a></li>
    <li><a href="#indice">Índice</a></li>
    <li><a href="#descripcion-del-proyecto">Descripción del proyecto</a></li>
    <li><a href="#caracteristicas-de-la-aplicacion-y-demostracion">Características de la aplicación y demostración</a></li>
    <li><a href="#tecnologias-utilizadas">Tecnologías utilizadas</a></li>
    <li><a href="#personas-desarrolladores-del-proyecto">Personas-Desarrolladores del Proyecto</a></li>
    <li><a href="#conclusion-y-notas-finales">Conclusión y notas finales</a></li>
</ol>

<br>
<h2 id="descripcion-del-proyecto">✏️Descripción del proyecto</h2>
Se trata de una API REST desarrollada usando Spring Boot con el fin de simular el foro de la plataforma Alura. Básicamente es un espacio interactivo que les permite a los estudiantes activos que 
se encuentran cursando alguna formación virtual de esta institución, presentar sus dudas sobre determinados cursos con el fin de que algún compañero o los docentes encargados puedan 
darles respuesta. El objetivo es simular las acciones y herramientas que permiten el funcionamiento del foro a nivel de Back-End: almacenamiento de la información, tratamiento de 
datos que permitan establecer la relación entre tópicos y respuestas, relacionamiento de los usuarios con las respuestas de un tópico, entre otras funcionalidades.

<h2 id="caracteristicas-de-la-aplicacion-y-demostracion">⚙️Características de la aplicación y demostración</h2>
<ul>
    <li><code>Registro de un nuevo tópico</code>: la API contiene un endpoint para el registro de nuevos tópicos y acepta solicitudes POST para el URI "/topicos".
      Los datos del tópico (titulo, mensaje, autor y curso) deben enviarse en el cuerpo de la solicitud, en formato JSON.
      <p></p>
      <img alt="post" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/813deec4-9099-4402-974a-1baa13efcb53">
        <img alt="post-respuesta" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/b2f935bd-19b8-4feb-bb08-918f7b715050">
    </li>
    <li><code>Mostrar todos los tópicos creados</code>: la API contiene un endpoint para el listado de todos los tópicos y acepta solicitudes GET para la URI "/topicos".
      Los datos de cada tópico (titulo, mensaje, fecha de creación, estatus, autor y curso) son devueltos en el cuerpo de la respuesta, en formato JSON.
      <p></p>
      <img alt="get" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/81b275d8-c938-4bcc-bd37-ca45e02b41c9">
        <img alt="get-respuesta" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/73c8b142-2223-4ef0-9b9e-068118a789f6">
    </li>
    <li><code>Detallando un tópico</code>: la API contiene un endpoint para el listado de un tópico en específico y acepta solicitudes GET para la URI "/topicos/{id}".
      Los datos del tópico (titulo, mensaje, fecha de creación, estatus, autor y curso) son devueltos en el cuerpo de la respuesta, en formato JSON.
      <p></p>
      <img alt="get-especifico" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/a4952c24-babc-4f43-876e-2940ecc0d870">
      <img alt="get-especifico-respuesta" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/763275c9-44f8-43ef-b616-e7864435f77f"> 
    </li>
    <li><code>Actualizar un tópico</code>: la API contiene un endpoint para la actualización de un tópico y acepta solicitudes PUT para la URI "/topicos/{id}".
      <p></p>
      <img alt="put" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/2af94cdd-0a61-4cbc-be6d-17638b9667c6">
      <img alt="put-respuesta" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/4930e2d9-d573-40cd-8f04-08a9583f09cb">
    </li>
    <li><code>Eliminar un tópico</code>: la API contiene un endpoint para la eliminación de un tópico y acepta solicitudes DELETE para la URI "/topicos/{id}". En realidad de trata de un delete lógico, no se
      elimina totalmente el tópico de la base de datos, si no que se desactiva para no mostrarlo cuando se listen los tópicos y para que no interfiera en la creación de nuevos, pero se deja igualmente el registro 
      con toda la información pertinente en la base de datos.
      <p></p>
      <img alt="put" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/7a19a59b-4b3b-42a1-90c6-b5bcfb1d79de">
      <img alt="put-respuesta" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/ecb77331-e753-4bf8-88ad-333b31f39128">
    </li>
    <li><code>Validaciones</code>: cada request detallado anteriormente, sigue diferentes validaciones para su correcta ejecución
      <p></p>
      <ul>
        <li><code>POST</code>: para el caso de los registros, se debe validar que todos los campos sean llenados previamente y que no se creen tópicos repetidos (con mismo título y mensaje).</li>
        <li><code>GET</code>: para el caso de mostrar uno o más registros, se debe validar que estos se encuentren activos y que se devuelvan los datos correctos.</li>
        <li><code>PUT</code>: para el caso de actualizar un tópico, se valida que efectivamente el id enviado corresponda a un tópico y que este se encuentre activo.</li>
        <li><code>DELETE</code>: al igual que en el caso de actualizar, para eliminar un tópico se valida que el id enviado sea correcto y que el tópico no haya sido desactivado anteriormente</li>
      </ul>
    </li>
    <li><code>Pruebas a la API</code>: el código contiene test automatizados para el controller de Topico y los estados http 201 (cuando los datos ingresados son correctos y permiten registrar un nuevo tópico) y 400 (cuando los datos ingresados son invalidos). De igual forma, contiene test automatizados para el Respository de Topico para verificar que la consulta a la base retorna los datos esperados.
    </li>
<li><code>Documentación de la API</code>: la documentación de la API se realizó usando la api externa OpenApi, por lo que ingresando a los siguientes links, es posible probar las diferentes funciones de la API 
        y obtener más información de esta.
      <p></p>
        - http://localhost:8080/v3/api-docs
        <p></p>
        <img alt="login" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/934ceafd-758d-44a4-bc13-3ab98b83583a">
        - http://localhost:8080/swagger-ui/index.html
        <p></p>
      <img alt="login" src="https://github.com/abriceno221/Foro-de-Alura/assets/132310492/9b29bb2e-15fe-476b-91db-fdde4691634f">
    </li>
    <li><code>Autenticación y Autorización</code>: la autenticación de la API es de tipo stateless
    </li>
</ul>

<h2 id="tecnologias-utilizadas">🖥️Tecnologías utilizadas</h2>
<ul>
    <li>Java 17</li>
    <li>MySQL</li>
    <li>JPA-Hibernate</li>
    <li>Lombok</li>
    <li>Bean Validation</li>
    <li>Spring Security</li>
    <li>Bcrypt</li>
    <li>OpenAPI 2.2.0</li>
    <li>auth0 4.2.0</li>
    <li>Flyway</li>
</ul>
  
<h2 id="personas-desarrolladores-del-proyecto">🧑‍💻Personas-Desarrolladores del Proyecto</h2>
<a href="https://github.com/abriceno221">
  <img src="https://github.com/abriceno221/Conversor/assets/132310492/49dac16e-fb44-4779-bff7-05ac8593aee4" width="115" alt="Anderson Briceño Baez">
  <br>
  <sub>Anderson Briceño Baez</sub>
</a>

<h2 id="conclusion-y-notas-finales">📜Conclusión y notas finales</h2>
Es necesario resaltar que este proyecto fue realizado como parte del plan educativo Back-End de Alura Latam en alianza con ONE (Oracle Next Education). Como el enfoque educativo era Back-End, Alura Latam
se encargó muy amablemente de suministrar el Front-End de la aplicación y yo realicé la lógica detrás para complementar el proyecto con los conocimiento de Back-End (principalmente en este caso JDBC y MySQL) adquiridos.
