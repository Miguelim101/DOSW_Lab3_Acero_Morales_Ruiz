# 📄 Requerimientos del Sistema

## 1. Lista general de requerimientos

El sistema de TechCup tiene los siguientes requerimientos:

### 1.1 Requerimientos funcionales

El sistema de TechCup debe tener la capacidad de:

1. Permitir la autenticacion de los diferentes tipos de usuarios (Organizadores, Capitanes, y Estudiantes) mediante nombre de usuario y contraseña.

2. Permitir a los organizadores crear torneos (identificacion, fecha, cuotas, organizador, partidos), cambiar su estado, inscribir equipos a un torneo activo, y actualizar su informacion.

3. Permitir a los organizadores consultar y verificar los pagos de los equipos, y aprobar las inscripciones de los equipos.

4. Permitir a los organizadores generar un informe de los ingresos obtenidos por las cuotas de inscripcion de los torneos que crearon y gestionan.

5. Permitir a los capitanes crear equipos, realizar pagos por PSE, actualizar la informacion de los equipos, y solicitar la inscripcion de su equipo en torneos.

6. Permitir a los Estudiantes cosultar el informe de equipos o torneos especificos.

7. No debe de permitir que existan dos torneos con la misma fecha y que tenga un estado de "Activo" o "En curso".

### 1.2 Requerimientos no funcionales

El sistema de TechCup debe tener:

1. Una interfaz cuya paleta de colores se compone de los colores: #A60F18, #000000, #FFFFFF.

2. Mostrar un mensaje al cliente cuando el usuario o contraseña ingresada sean incorrectos o los datos sean correctos y se haya logrado iniciar sesion o registrarse correctamente.

3. Tener una interfaz diferente en la pagina de inicio segun el tipo de usuario (Organizador, Capitan o Estudiante), para que cada uno tenga acceso a las funcionalidades correspondientes.

4. Una interfaz responsiva a las dimensiones del dispositivo en la que es presentada.

5. Para cada accion funcional de cada rol, se debe de indicar si fue exitosa o no, y en caso de no ser exitosa, indicar la razon.


## 2. Diagramas de caso de uso

### 2.1 Requerimiento Funcional 01

| Campo | Descripción |
|------|-------------|
| **ID** | RF-01 |
| **Nombre del requerimiento** | Autenticacion de Usuario |
| **Descripción** | *El sistema debe de permitir la autenticacion de los diferentes tipos de usuarios (Organizadores, Capitanes, y Estudiantes) mediante nombre de usuario y contraseña.* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, Bankify debe tener previamente al usuario registrado o permitir que se registre por primera vez, y validar que sea un estudiante de la Escuela con su correo institucional.* |
| **Actor** | *Organizadores, Capitanes y Estudiantes* |
| **Flujo principal** | *Registro*<br>1. Los 3 actores mencionados se registran con un usuario y contraseña en la interfaz de registro.<br>2. El sistema verifica las credenciales ingresadas, muestra un mensaje que indica si esas son correctas o incorrectas.<br>3. Y si son correctas; segun su tipo de correo institucional registra al nuevo usuario como Organizador o debe de seleccionar si es un Capitan o Estudiante.<br>4. El sistema envia al actor a la interfaz de inicio.<br><br>*Logeo*<br>1. Los 3 actores mencionados se logean con un usuario y contraseña en la interfaz de login.<br>2. El sistema verifica las credenciales ingresadas y muestra un mensaje que indica si estas son correctas o incorrectas.<br>3. Y si son correctas; inicia la sesion del usuario.<br>4. El sistema envia al actor a la interfaz de inicio.|
| **Diagrama de caso de uso** | ![RF-01](../uml/RF-01.png) |
| **Poscondiciones** | *Se espera como resultado que se pueda registrar o logear un usuario que tenga un correo institucional, y acceder correctamente a la pagina de inicio en caso de que sus credenciales sean correctas.* |


### 2.2 Requerimiento Funcional 02

| Campo | Descripción |
|------|-------------|
| **ID** | RF-02 |
| **Nombre del requerimiento** | Funcionalidades Del Organizador |
| **Descripción** | *El sistema debe de permitir a los Organizadores crear torneos ingresando una fecha y una cuota de inscripcion, inscribir equipos a un torneo activo creado por el, actualizar la informacion de los torneos, cambiar su estado (Pendiente, Activo, En curso, Cerrado y Cancelado), añadir partidos al torneo, consultar los equipos de un Torneo, consultar y verificar los pagos de los equipos y aprobar las inscripciones de los equipos a su torneo, no debe de permitir que el organizador cree mas de un torneo por semestre, y tambien no debe de permitir eliminar torneos.* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, TechCup debe de tener previamente registrado al organizador como un usuario, los equipos que el organizador desea inscribir a su torneo ya deben de estar creados.* |
| **Actor** | *Organizador* |
| **Flujo principal** |*Crear Un Torneo*<br>1. El Organizador desde su interfaz de inicio acciona la funcionalidad de crear un torneo.<br>2. El sistema abre una nueva interfaz donde le solicita al organizador datos como la fecha y la cuota de inscripcion.<br>3.1 El Organizador una vez termina hace clic en el boton inferior de Crear.<br>3.2 El Organizador si desea puede cancelar la creacion de un torneo, haciendo clic en el boton inferior de Cancelar.<br>4.1 El sistema verifica que la fecha y la cuota ingresadas cumpla con las restricciones del sistema.<br>4.2 El sistema dirige al Organizador a la interfaz de inicio [Aqui Finaliza este Flujo]<br>5. El sistema crea el torneo.<br>6. El sistema dirige al Organizador a la interfaz de informacion y gestion del torneo creado.<br><br>*Inscribir Equipos*<br>1. El Organizador dentro de la interfaz de informacion y gestion de uno de sus torneos, acciona la funcionalidad de inscribir equipos<br>2. El sistema abre una nueva interfaz donde el Organizador puede buscar los equipos por su nombre.<br>3. El Organizador ingresa parcialmente o la totalidad del nombre del equipo que desea inscribir.<br>4. El sistema va filtrando los equipos cuyo nombre coinciden.<br>5. Cuando el Oganizador encontro el equipo deseado, hace clic sobre este y se guarda el equipo seleccionado.<br>6. El Organizador puede seguir seleccionando equipos y los equipos ya seleccionados se muestran en la parte superior.<br>7. El Organizador puede eliminar los equipos ya seleccionados haciendo clic en un boton con una X ubicado a la derecha de cada equipo.<br>8.1 Una vez el Organizador tiene todos los equipos que desea inscribir hace clic en el boton inferior "Finalizar Inscripcion".<br>8.2 El Organizador si desea puede cancelar la inscripcion de equipos, haciendo clic en el boton inferior de Cancelar. [Se salta al flujo 10]<br>9. El sistema realiza la inscripcion al torneo de todos los equipos seleccionados por el Organizador.<br>10. El Organizador es llevado de vuelta a la interfaz de informacion y gestion del torneo por el sistema.<br><br>*Actualizar Informacion De Un Torneo (Incluye Actualizar El Estado)*<br>1. El Organizador dentro de la interfaz de informacion y gestion de un torneo, acciona la funcionalidad de actualizar informacion.<br>2. El sistema abre una nueva interfaz donde se presenta la informacion que se puede actualizar en campos modificables por el Organizador.<br>3. El Organizador modifica o selecciona los valores en los campos segun desee.<br>4.1 El Organizador una vez termina hace clic en el boton inferior de Guardar.<br>4.2 El Organizador si desea puede cancelar la actualizacion de la informacion, haciendo clic en el boton inferior de Cancelar. [Se salta al Flujo 6]<br>5. El sistema sobreescribe la informacion anterior con la nueva ingresada por el Organizador.<br>6. El Organizador es llevado de vuelta a la interfaz de informacion y gestion del torneo por el sistema.<br><br>*Añadir Partidos Al Torneo*<br>1. El Organizador dentro de la interfaz de informacion y gestion de un torneo, acciona la funcionalidad de añadir partidos al torneo.<br>2. El sistema abre una nueva interfaz donde el organizador puede buscar los equipos por su nombre.<br>3. El Organizador ingresa parcialmente o la totalidad del nombre del equipo que desea colocar en un partido.<br>4. El sistema va filtrando los equipos cuyo nombre coinciden.<br>5. Cuando el Oganizador encontro el equipo deseado, hace clic sobre este y se guarda el equipo seleccionado, que se puede ver en la parte superior.<br>6. Al elegir un segundo equipo aparece una ventana emergente que le solicita al Organizador datos como la hora del partido y lugar.<br>7.1 El Organizador una vez termina hace clic en el boton inferior Aceptar.<br>7.2 El Organizador si desea puede cancelar la creacion del partido, haciendo clic en el boton inferior de Cancelar. [Se salta al Flujo 6]<br>8. El partido a crear se guarda y se muestra en la parte superior.<br>9. El Organizador puede seguir seleccionando pares de equipos para crear partidos, cuando selecciona el primer equipo se muestra justo debajo de los partidos a crear. [Basicamente seguir haciendo el Flujo 5, 6, 7.1 o 7.2].<br>10.1 El Organizador una vez termina hace clic en el boton inferior de Guardar.<br>10.2 El Organizador si desea puede cancelar la creacion de partidos de un torneo, haciendo clic en el boton inferior de Cancelar. [Se salta al Flujo 12]<br>11. El sistema crea cada uno de los partidos.<br>12. El Organizador es llevado de vuelta a la interfaz de informacion y gestion del torneo por el sistema.<br><br>|
| **Diagrama de caso de uso** | ![RF-02](../uml/RF-02.png) |
| **Poscondiciones** | *Se espera como resultado …* |

### 2.3 Requerimiento Funcional 03

| Campo | Descripción |
|------|-------------|
| **ID** | RF-03 |
| **Nombre del requerimiento** | Funcionalidades Del Capitan |
| **Descripción** | *El sistema debe de permitir a los Capitanes crear equipos, realizar pagos por PSE, actualizar la informacion de los equipos, y solicitar la inscripcion de su equipo en torneos.* |
| **Precondiciones** | *Para que el sistema cumpla con este requerimiento, Bankify debe tener previamente …* |
| **Actor** | *Capitan* |
| **Flujo principal** | *Crear Equipos*<br>1. El Capitan desde su interfaz de inicio acciona la funcionalidad de crear un equipo.<br>2. El sistema abre una nueva interfaz donde le solicita al capitan datos como el nombre del equipo y de manera opcional agregar miembros al equipo.<br>3. Para el campo de añadir miembros al equipo, existe un buscador donde el capitan ingresa parcialmente o la totalidad del nombre del Estudiante que desea colocar en el equipo.<br>4. El sistema va filtrando los Estudiantes cuyo nombre coinciden.<br>5. Cuando el capitan encontro el Estudiante deseado, hace clic sobre este y se guarda en el campo.<br>6.1 El capitan una vez termina hace clic en el boton inferior de Crear.<br>6.2 El capitan si desea puede cancelar la creacion de un equipo, haciendo clic en el boton inferior de Cancelar.<br>7.1 El sistema verifica que los datos ingresados existan y cumplan con las restricciones del sistema.<br>7.2 El sistema dirige al capitan su pagina de inicio. [Aqui termina este Flujo]<br>8. El sistema crea el equipo.<br>9. El sistema dirige al capitan a la interfaz de informacion y gestion del equipo creado.<br><br>*Actualizar Informacion De Un Equipo*<br>1.  |
| **Diagrama de caso de uso** | ![RF-03](../uml/RF-03.png) |
| **Poscondiciones** | *Se espera como resultado …* |


## 3. Preguntas
