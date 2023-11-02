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
      Los datos del tópico( titulo, mensaje, autor y curso) deben enviarse en el cuerpo de la solicitud, en formato JSON.
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
    <li><code>Mostrar todos los tópicos creados</code>: la API contiene un endpoint para el listado de todos los tópicos y acepta solicitudes GET para la URI "/topicos".
      Los datos de cada tópico (titulo, mensaje, fecha de creación, estatus, autor y curso) son devueltos en el cuerpo de la respuesta, en formato JSON.
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
    <li><code>Detallando un tópico</code>: la API contiene un endpoint para el listado de un tópico en específico y acepta solicitudes GET para la URI "/topicos/{id}".
      Los datos del tópico (titulo, mensaje, fecha de creación, estatus, autor y curso) son devueltos en el cuerpo de la respuesta, en formato JSON.
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
    <li><code>Actualizar un tópico</code>: la API contiene un endpoint para la actualización de un tópico y acepta solicitudes PUT para la URI "/topicos/{id}".
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
    <li><code>Eliminar un tópico</code>: la API contiene un endpoint para la eliminación de un tópico y acepta solicitudes DELETE para la URI "/topicos/{id}". En realidad de trata de un delete lógico, no se
      elimina totalmente el tópico de la base de datos, si no que se desactiva para no mostrarlo cuando se listen los tópicos y para que no interfiera en la creación de nuevos, pero se deja igualmente el registro 
      con toda la información pertinente en la base de datos.
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
    <li><code>Validaciones</code>: cada request detallado anteriormente, sigue diferentes validaciones para su correcta ejecución
      <p></p>
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
      <p></p>
      <ul>
        <li><code>POST</code>: para el caso de los registros, se debe validar que todos los campos sean llenados previamente y que no se creen tópicos repetidos (con mismo título y mensaje).</li>
        <li><code>GET</code>: para el caso de mostrar uno o más registros, se debe validar que estos se encuentren activos y que se devuelvan los datos correctos.</li>
        <li><code>PUT</code>: para el caso de actualizar un tópico, se valida que efectivamente el id enviado corresponda a un tópico y que este se encuentre activo.</li>
        <li><code>DELETE</code>: al igual que en el caso de actualizar, para eliminar un tópico se valida que el id enviado sea correcto y que el tópico no haya sido desactivado anteriormente</li>
      </ul>
    </li>
    <li><code>Pruebas a la API</code>: el código contiene test automatizados para el controller de Topico y los estados http 201 (cuando los datos ingresados son correctos y permiten registrar un nuevo tópico) y 
      400 (cuando los datos ingresados son invalidos).
      <p></p>
      De igual forma, contiene test automatizados para el Respository de Topico para verificar que la consulta a la base retorna los datos esperados.
      <img alt="login" src="https://github.com/abriceno221/Hotel-Alura/assets/132310492/ce93a136-54ae-4133-9e96-bc7a5d93234b">
    </li>
</ul>

<h2 id="tecnologias-utilizadas">🖥️Tecnologías utilizadas</h2>
<ul>
    <li>Java 11</li>
    <li>MySQL</li>
    <li>JDBC</li>
    <li>C3P0</li>
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
