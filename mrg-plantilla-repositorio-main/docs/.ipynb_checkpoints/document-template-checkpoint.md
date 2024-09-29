# [Práctica 1 URDF] 


| Código | Description |
| ------:| ----------- |
| ***Asignatura*** | 1| 
| **Robotica-2022-I**  | Práctica*01 ...* |

## Contenido

- [Objetivo](#objetivo)
- [Introducción](#introduccion)
- [Desarrollo](#desarrollo)
- [Conclusiones](#conclusiones)
- [Autor](#autor)
- [Referencias](#referencias)

## Objetivo

El objetivo de esta práctica es que el alumno comprenda, interprete y modifique la información básica de los formatos de Universal Robot Description File (URDF).

## Introducción

La **Práctica 1** tiene como objetivo principal que los estudiantes se familiaricen con los elementos clave del **Robot Operating System 2 (ROS 2)**, y el **Unified Robot Description Format (URDF)**, herramientas fundamentales para la descripción y simulación de robots en ambientes virtuales. A lo largo de esta práctica, se investigan y aplican conceptos esenciales como la definición de URDF, los tipos de juntas o articulaciones que se pueden especificar en dicho formato, y los elementos geométricos primitivos utilizados para modelar un robot. Además, la práctica aborda el uso de **nodos y tópicos en ROS 2**, componentes esenciales para la comunicación y la sincronización de tareas en sistemas robóticos distribuidos. Asimismo, se introduce a los estudiantes a **RVIZ**, una herramienta gráfica en 3D utilizada para la visualización de robots y sus entornos, permitiendo la interpretación visual de las acciones y movimientos simulados. Con esta práctica, se busca que los estudiantes comprendan cómo describir un robot de manera precisa en un entorno ROS 2, facilitando el desarrollo de simulaciones avanzadas y la implementación de proyectos en robótica.

Previo de la Práctica 1

### **Definición de URDF**
El **Unified Robot Description Format (URDF)** es un formato de archivo basado en XML utilizado en ROS (Robot Operating System) para describir la estructura física de un robot. Este archivo especifica la geometría, las articulaciones y los enlaces del robot, lo que permite su visualización y simulación en herramientas como RVIZ o Gazebo. Los URDF son esenciales para definir cómo un robot está construido y cómo se mueve, proporcionando un marco estandarizado para la descripción de robots en simulaciones o implementaciones físicas.

### **Tipos de Juntas en el Formato URDF**
Dentro de un archivo URDF, se pueden definir varios tipos de **juntas** o articulaciones, cada una con diferentes características de movimiento. Los tipos más comunes son:
1. **Fixed Joint:** No permite movimiento entre los dos enlaces conectados. Es una junta fija.
2. **Revolute Joint:** Permite un movimiento de rotación alrededor de un eje, similar a una bisagra.
3. **Continuous Joint:** Similar a la junta revoluta, pero permite rotación infinita.
4. **Prismatic Joint:** Permite un movimiento lineal a lo largo de un eje, es decir, deslizamiento.
5. **Floating Joint:** Permite movimiento en 6 grados de libertad (traslaciones y rotaciones), pero rara vez se utiliza en URDF debido a su complejidad en simulaciones.

### **Elementos "Primitivos" para Definir un Robot en ROS**
En el contexto de URDF y ROS, los **elementos primitivos** son las formas geométricas básicas utilizadas para modelar la estructura física de los robots. Algunos de los elementos más comunes son:
1. **Box (caja):** Se define por su longitud, ancho y altura.
2. **Cylinder (cilindro):** Se define por su radio y altura.
3. **Sphere (esfera):** Se define solo por su radio.
4. **Mesh (malla):** Permite importar formas más complejas, típicamente en formato STL o COLLADA, para describir objetos que no pueden representarse con geometrías básicas.

### **¿Qué es un Nodo y un Tópico en ROS 2?**
En **ROS 2**, un **nodo** es una unidad de ejecución que realiza una tarea específica dentro de un sistema robótico. Cada nodo puede estar encargado de tareas como la lectura de sensores, el control de actuadores, o la planificación de movimientos. Los nodos pueden comunicarse entre sí para coordinar sus actividades.

Un **tópico** en ROS 2 es un canal de comunicación asíncrono en el que los nodos pueden publicar o suscribirse para intercambiar datos. Un nodo que genera datos (como las lecturas de un sensor) publicará esa información en un tópico, mientras que otros nodos que necesiten esos datos se suscribirán al tópico para recibir la información.

### **¿Qué es RVIZ?**
**RVIZ** es una herramienta de visualización 3D utilizada en ROS. Permite a los desarrolladores ver el estado de un robot y su entorno en tiempo real, incluyendo la geometría del robot, los datos de los sensores, los mapas de navegación y las trayectorias de movimiento. RVIZ es crucial para depurar y analizar el comportamiento de los robots durante las simulaciones o en aplicaciones del mundo real.


## Desarrollo 

El desarrollo de la práctica se divide en dos partes:

1. La primera parte de realizará en clase, en la cual se desarrollará y simulará de descripción de un eslabón cayo movimiento está restringido por una junta rotacional.
2. El alumno debe modificar el código del archivo para agregar otro eslabón el cual puede estar unido al primer eslabón por una junta revolución o una junta prismática.

Bloques de cita

> "If it weren't for my lawyer, I'd still be in prison.
>  It went a lot faster with two people digging."
>
> --- Joe Martin

Bloque de cita con vínculo de referencia. 

> Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
> tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. 
>
> At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren,
> no sea takimata sanctus est Lorem ipsum dolor sit amet [[1]](#1). **<- referencia insertada** 

Imágenes

![Markdown Guide](/images/markdown-logo.png) Markdown Guide [Basic Syntax](https://www.markdownguide.org/basic-syntax/), [Extended Syntax](https://www.markdownguide.org/extended-syntax/)

Ejemplo de la estructura del directorios del repositorio: 

Proyecto de **ROS** con los directorios **adicionales** para almacenar **imágenes** y **documentos** referentes al **proyecto**.

**Nota:** La estructura mostrada representa -en su mayoría- a los directorios más usados dentro de un proyecto de **ROS**.


```text
 proyecto/
    ├── images/
    │   ├── imagen1.png
    │   ├── imagen2.png
    │   ├── imagen3.gif
    │   └── imagen5.svg
    ├── docs/
    │   ├── archivo1.md
    │   ├── archivo2.pdf
    │   ├── archivo3.txt
    │   └── archivo2.pdf
    ├── src/
    │   ├── include/
    │   │   ├── lib1.h
    │   │   └── libcpp.so
    │   ├── config/
    │   │   ├── config-file01.yaml
    │   │   └── config-file02.yaml
    │   ├── meshes/
    │   │   ├── visual/
    │   │   │   ├── mesh-file.stl
    │   │   │   └── mesh-file.dae
    │   │   └── collision/
    │   │       ├── mesh-file.stl
    │   │       └── mesh-file.dae
    │   ├── launch/
    │   │   ├── launch-file1.launch
    │   │   ├── rviz-file1.rviz
    │   │   ├── rviz-file2.rviz
    │   │   └── launch-file3.launch
    │   ├── msg/
    │   │   ├── Message-file1.msg
    │   │   └── Message-file2.msg
    │   ├── srv/
    │   │   ├── ServiceMsg-file1.srv
    │   │   └── ServiceMsg-file2.srv
    │   ├── action/
    │   │   ├── ActionMsg-file1.action
    │   │   └── ActionMsg-file2.action
    │   ├── urdf/
    │   │   ├── urdf-file.urdf
    │   │   └── xacro-file.xacro
    │   ├── scripts/
    │   │   ├── pyscript-file.py
    │   │   └── cpp-programm.cpp
    │   ├── src/
    │   │   ├── cpp-programm.cpp
    │   │   └── pyprogramm-file.py
    │   ├── Otros-archivos-del-proyecto.txt
    │   ├── package.xml
    │   └── CMakeLists.txt
    ├── .gitignore
    ├── CMakeLists.txt
    ├── LICENSE.md
    ├── Otros-archivos-generales.txt
    └── Readme.md
```

***Bloques de código***

Bloques de código "cercados"

```
Texto de ejemplo aquí...
```

De acuerdo a la sintaxis del lenguaje de programación, ver más [información](https://docs.github.com/es/github/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks).

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

Youtube videos

[![Markdown, Curso Práctico para principiantes y desarrolladores](https://img.youtube.com/vi/oxaH9CFpeEE/0.jpg)](https://www.youtube.com/watch?v=oxaH9CFpeEE)

## Conclusiones

Conclusiones o cierre al trabajo realizado.

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At
vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren,
no sea takimata sanctus est Lorem ipsum dolor sit amet [[2]](#2). **<- referencia insertada en el párrafo** . 

## Autor

***[Nombre del autor o listado de los integrantes del equipo]***

**Autor** Pizano Bravo Alexis [GitHub profile](https://github.com/rivascf)

## Referencias

<a id="1">[1]</a>  I.A. Glover and P.M. Grant, Digital Communications, 3rd ed.  Harlow: Prentice Hall, 2009. 

<a id="2">[2]</a>  H.-L. Pham, V. Perdereau, B. Adorno, en P. Fraisse, “Position and Orientation Control of Robot Manipulators Using Dual Quaternion Feedback”, 11 2010, bll 658–663. <https://www.researchgate.net/publication/224200087_Position_and_Orientation_Control_of_Robot_Manipulators_Using_Dual_Quaternion_Feedback>

**Nota**:

> Listado de referencias documentales consultadas para realizar el trabajo:
> consultar el siguiente [vínculo](https://www.bath.ac.uk/publications/library-guides-to-citing-referencing/attachments/ieee-style-guide.pdf)
> para el formato de referencia estilo **IEEE**.
> 
> ```text
> [Num ref] Iniciales del autor. Apellido del autor, Título del libro, edicion (si no es la primera). 
> Lugar de publicación: Publicador, Año.
> ```
