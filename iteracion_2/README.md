# Variables
En este apartado se pretende describir el significado de las diferentes
variables y flujos que se tuvieron en cuenta para el desarollo de la segunda
iteración del modelo de Dinámica de Sistemas. 

## Variables de nivel
- Cantidad de tareas pendientes
- Cantidad de tareas finalizadas
- Cantidad de Correcciones de cátedra
- Cantidad de Errores

## Variables auxiliares

### Plazo restante
 Este hace referencia a la cantidad de días que restan para que se le solicite
 al alumno una presentación final. Esta variable depende de las siguientes
- **_Prorroga:_** Cantidad de días de prorroga brindados al alumno, valor que se
  tomará en cuenta al calcular la cantidad de días restantes en caso de que
  corresponda.

### Presión de fecha de entrega
Este valor representa la presión a la que se ve sometida el alumno, esta varía
en el tiempo, cuando el `porcentaje de avance` disnimuye y/o el `plazo restante`
es alto esta (la variable) va a disminuir, o aumenta en caso contrario. Las
variables de las cuales depende son las siguientes:
- **_Plazo restante_**
- **_Porcentaje de avance_**

### Porcentaje de avance
Este valor representa al porcentaje de avance que se tiene en el poryecto. Este
va a depender de dos variables que determinarán la cantidad de tareas por
realizar y las ya realizadas, el cociente de estas brindará el porcentaje de
avance.
- **_Tareas pendientes_**
- **_Tareas finalizadas_**

### Prorroga
Ésta hace referencia a la cantidad de tiempo que se le permitirá al alumno
alargar la presentación del trabajo. Esta variable es dependiente de las
siguientes:
- **_Prorroga normal:_** valor que indica la cantidad de días que se prolonga la
  presentación del trabajo en días, esta se le dará al alumno si el alcanza el
  `porcentaje aceptable de avance del proyecto`.
- **_Porcentaje aceptable de avance del proyecto:_** valor que indica el
  porcentaje que requiere la cátedra para poder conceder la prorroga a un
  alumno.
- **_Porcentaje de avance:_** valor que indica el porcentaje de avance en el que
  se encuentra el proyecto.
- **_Cantidad de prorrogas disponibles:_** esta hace referencia a cuantas veces,
  la cátedra brindará prorrogas a los alumnos para un trabajo en particular,
  antes de que este se considere como libre (en el proyecto esto se considera
  como `fracaso`) .

### Cantidad de tareas iniciales
Este valor indica la cantidad de tareas iniciales que se tienen a la hora de dar
inicio el proyecto, este valor se determinará de manera manual en la iteración,
como tarea futura, se puede ver el proceso de cómo se crean las tareas que se
deben realizar para cumplir con el trabajo.

### Experiencia
Este busca representar el nivel de experiencia que tiene un alumno basandose en
las habilidades individuales de campos, considerados por el equipo, como clave a
la hora del desarrollo de un producto de software.
- **_Lenguaje:_** este valor hace referencia a que tan bien se le dá al alumno
  el uso de la herramienta (específicamente hablando de lenguaje de
  programación, framework, stack) que eligió para llevar adelante el proyecto.
- **_Bases de Datos:_** de la misma forma, este valor, busca determinar el nivel
  de comodidad que el individuo tiene con el manejo de las bases de datos.
- **_Análisis y Diseño:_** este valor, busca abstraer que tan efectivo/eficaz es
  el alumno a la hora del relevamiento de los requerimientos y del diseño de una
  solución de software para el mismo.

Cuanto más experiencia tenga el estudiante en su haber, sufrirá menos las
cuestiones relacionadas con los cambios de requreimientos por parte de la
cátedra, o el rediseño de partes del software, cuestiones que se reflejan en la
cantidad de tareas a tratar.

### Acceso a material de ayuda
Este valor representará el nivel de acceso que el alumno tenga a fuentes
alternativas de ayuda para el desarrollo del trabajo, estas fuentes van desde el
acceso a internet en el hogar hasta manuales de usuario de herramientas.

### Carga horaria dedicada a la facultad
Este valor representa el tiempo en horas que el alumno le dedica diariamente a
la facultad, se hace una discriminación en cuanto a:
- **_Carga horaria de consulta:_** este valor representa la carga horaria que el
  alumno dedica a una clase de consulta referente al proyecto.
  - _Nota:_ ver como se va a medir esto, por el hecho de que se tienen clases
    semanales, por lo que esto no va a estar en horas solamente, sino que estará
    en horas/semana.
- **_Cantidad de materias cursando:_** este valor va a representar la cantidad
  de materias que el alumno se encuentra cursando de manera paralela a la
  cátedra de Proyecto de Software

### Carga horaria de dedicación al proyecto
Este valor representa el tiempo en horas que el alumno le dedica diariamente a
la facultad, teniendo en cuenta que se toman factores como `familia` o `trabajo`
a la hora del calculo de la variable. A continuación las variables de las cuales
depende este concepto:
- **_Tiene familia:_** este valor determinará si la familia juega un rol
  influyente a la hora de saber cuanto tiempo se dedica al proyecto.
- **_Trabaja:_** de la misma manera, este valor va a determinar que tanto
  influye el hecho de que el alumno tenga un trabajo en el desarrollo del
  proyecto.
- **_Carga horaria dedicada a la facultad_**.

## Flujos

- Dedicación
  - Carga horaria que puede dedicar al proyecto (diaria/semanal)
    - O carga horaria dedicada a la facultad, esto va a permitir la relación
    con
      - Cantidad de materias
- Enfermedad
  - Factor que disminuye en cierta forma la carga horaria
- Tema y cuanto se tarde en encontrar uno
- Facilidad de acceso a material de ayuda [1]
  - Manuales
  - internet
  - cursos
- Prorrogas (tiempo que dura la prorroga, en dias)
  - prorroga normal
  - cantidad de prorrogas posibles


[1] podríamos implementar una tabla en donde tengamos un sistema de
pesos que nos permita computar la no aplicabilidad de unode los siguientes
factores 

Damos por sentado lo siguiente
------------------------------

- El proyecto final es el desarrollo de un sistema
- En esta etapa de la investigación se definen tres grandes ramas que se
supone tiene todo proyecto final de ASC:
  - Bases de datos
  - Lenguaje
  - Análisis y diseño 