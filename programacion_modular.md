## Programación Modular

(Booch, 1991)
(Carlo Ghezzi, 1991)
(Deheza,2005)

### Programas y sentencias
Un programa de computadora es un sistema con componentes e interrelaciones. Intentaremos
determinar cuáles son dichos componentes y como se relacionan.
En primer lugar definiremos los conceptos de programa y programa de computadora.
Un programa puede ser definido como "una secuencia precisa y ordenada de instrucciones y
grupos de instrucciones, las cuales, en su total, definen, describen, o caracterizan la
realización de alguna tarea".
Un programa de computadora es simplemente un programa el cual, posiblemente a través de
una transformación, indica a la computadora como realizar una tarea.
En el nivel más elemental, observamos que un programa de computadora está compuesto de
sentencias o instrucciones. Estas instrucciones están ordenadas en una secuencia. Podemos
por lo tanto identificar a las instrucciones como componentes y a la secuencia como una
relación. Esta es la visión clásica o "algorítmica" de un programa.
De esta visión tenemos como consecuencia, que el esfuerzo en el desarrollo de un programa
se enfatiza en encontrar un método de solución y su transcripción sentencia a sentencia.
Para los propósitos de nuestro estudio, consideraremos que una sentencia es una línea de
código que el programador escribe.

### La Lingûistica de la Modularidad
Previo a la definición de módulo de programa haremos algunas observaciones. Supongamos
un conjunto de sentencias como las que se representan a en la figura 1.1:

**Figura 1**

Diremos que A1 y A2 son los límites del conjunto o agregado de sentencias llamado A. La
sentencia B se encuentra dentro de A, y C se encuentra fuera de A.
Las sentencias se encuentran en el orden en que ingresaran a un compilador. Este orden es
conocido como orden lexicográfico de un programa. Para nuestro estudio el término
lexicográfico siempre significará "como está escrito" o el orden en que aparecen las
sentencias de un programa en el listado de un compilador. Volviendo al ejemplo, diremos que
la sentencia C está lexicográficamente después que la A2.
Es importante distinguir que el orden lexicográfico casi siempre no se corresponde con el
orden de ejecución de las sentencias.
Uno de los propósitos de los elementos de límite (A1 y A2 en el ejemplo) es el de controlar el
alcance en el que identificadores son definidos y asociados a objetos (variables).
Estamos ahora en condiciones de definir el término módulo de programa o simplemente
módulo:

>Un módulo es una secuencia lexicográficamente contigua de sentencias, encerrada entre elementos de frontera, y que poseen un identificador del conjunto de dichas sentencias.

Dicho de otra manera, un módulo es un grupo de sentencias contiguas que poseen un
identificador simple por el cual son referenciadas.
Esta definición es general y dentro de la misma podemos encontrar implementaciones
particulares de lenguajes específicos como ser: "párrafos", "secciones", y "subprogramas" de
COBOL, "funciones" de C, "procedimientos" de Pascal, etc.
Un lenguaje de programación incluye un determinado tipo de módulo, solo si implementa
construcciones lingüísticas específicas que realizan las características de definición y
activación de dichos módulos

### Conexiones normales y patológicas

Diremos que entre dos módulos existe una conexión normal cuando la conexión se produce al
nivel del identificador del módulo invocado.
En oposición si la conexión intermódular se realiza a un identificador de un elemento interno
del módulo invocado, diremos que es una conexión patológica.

**Figura page 6**

### 1.4 Como alcanzar sistemas de mínimo costo

Cuando se trata con un problema de diseño, por ejemplo, un sistema que pueda ser
desarrollado en un par de semanas, no se tienen mayores problemas, y el desarrollador puede
tener todos los elementos del problema "en mente" a la vez. Sin embargo cuando se trabaja en
proyectos de gran escala, es difícil que una sola persona sea capaz de llevar todas las tareas y
tener en mente todos los elementos a la vez.
El diseño exitoso se basa en un viejo principio conocido desde los días de Julio Cesar: Divide
y conquistarás.
Específicamente, diremos que el costo de *implementación* de un sistema de computadora
podrá minimizarse cuando pueda separarse en partes
* *Manejablemente pequeñas*
* *Solucionables separadamente*

Por supuesto, la interpretación de manejablemente pequeña varía de persona en persona. Por
otro lado, muchos intentos de particionar sistemas en pequeñas partes arribaron incrementos
en los tiempos de implementación. Esto se debe fundamentalmente al segundo punto:
solucionables separadamente En muchos sistemas para implementar la parte A, debemos
conocer algo sobre la B, y para implementar algo de B, debemos conocer algo de C.
De manera similar, podemos decir que el costo de *mantenimiento* puede ser minimizado
cuando las partes de un sistema son:
* Facilmente relacionables con la aplicación
* Manejablemente pequeñas
* Corregibles separadamente

Muchas veces la persona que realiza la modificación no es quien diseñó el sistema.
Es importante que las partes de un sistema sean manejablemente pequeñas en orden de
simplificar el mantenimiento. Un trabajo de encontrar y corregir un error en una "pieza" de
código de 1.000 líneas es muy superior a hacerlo con piezas de 20 líneas. No solo disminuye
el tiempo de localizar la falla sino que si la modificación es muy engorrosa, puede reescribirse
la pieza completamente. Este concepto de "módulos descartables" ha sido utilizado con éxito
muchas veces.
Por otra parte, para minimizar los costos de mantenimiento debemos lograr que cada pieza sea
independiente de otra. En otras palabras debemos ser capaces de realizar modificaciones al
módulo A sin introducir efectos indeseados en el módulo B.
Finalmente, diremos que el costo de modificación de un sistema puede minimizarse si sus
partes son

* Facilmente relacionables con la apliación
* Modificables separadamente

En resumen, podemos afirmar lo siguiente: los costos de implementación, mantenimiento, y
modificación, generalmente serán minimizados cuando:

>Cada pieza del sistema corresponda a exactamente una pequeña, bien definida pieza del dominio del problema, y cada relación entre las piezas del sistema corresponde a relaciones entre piezas del dominio del problema.

### 1.5 Como se logra el costo mínimo con Diseño Estructurado

Un buen diseño estructurado es un ejercicio de participación y organización de los
componentes de un sistema.
Entenderemos por particionar, la subdivisión de un problema en subproblemas más pequeños,
de tal forma que cada subproblema corresponda a una pieza del sistema.
La cuestión es: ¿Dónde y cómo debe dividirse el problema? ¿Qué aspectos del problema
deben pertenecer a la misma pieza del sistema, y cuales a distintas piezas? El diseño
estructurado responde estas preguntas con dos principios básicos:

* Partes del problema altamente interrelacionadas deberán pertenecer a la misma pieza del
sistema.
* Partes sin relación entre ellas, deben pertenecer a diferentes piezas del sistema sin relación
directa.

Otro aspecto importante del diseño estructurado es la organización del sistema. Debemos
decidir cómo se interrelacionan las partes, y que parte está en relación con cual. El objetivo es
organizar el sistema de tal forma que no existan piezas más grandes de lo estrictamente
necesario para resolver los aspectos del problema que ella abarca. Igualmente impórtate, es el
evitar la introducción de relaciones en el sistema, que no existe en el dominio del problema.

### Concepto de cajas negras

Una caja negra es un sistema (o un componente) con entradas conocidas, salidas conocidas, y
generalmente transformaciones conocidas, pero del cual no se conoce el contenido en su
interior.
En la vida diaria existe innumerable cantidad de ejemplos de uso cotidiano: una radio, un
televisor, un automóvil, son cajas negras que usamos a diario sin conocer (en general) como
funciona en su interior. Solo conocemos como controlarlos (entradas) y las respuestas que
podemos obtener de los artefactos (salidas).
El concepto de caja negra utiliza el principio de *abstracción.*

Este concepto es de suma utilidad e importancia en la ingeniería en general, y por ende en el
desarrollo de software. Lamentablemente muchas veces para poder hacer un uso efectivo de
determinado módulo, el diseñador debe revisar su contenido ante posibles contingencias como
ser comportamientos no deseados ante determinados valores. Por ejemplo, es posible que una
rutina haya sido desarrollada para aceptar un determinado rango de valores y falla si se la
utiliza con valores fuera de dicho rango, o produce resultados inesperados. Una buena documentación en tales casos, es de utilidad pero no transforma al módulo en una verdadera
caja negra. Podríamos hablar en todo caso de "cajas blancas".
Los módulos de programas de computadoras pueden variar en un amplio rango de
aproximación al ideal de caja negra. En la mayoría de los casos podemos hablar de "cajas
grises".

### 1.7 Comparación entre las estructuras administrativas y el diseño estructurado

Uno de los aspectos más interesantes del diseño de programas es la relación que puede
establecerse con las estructuras de organización humana, particularmente la jerarquía de
administración encontrada en la mayoría de las grandes organizaciones.
Observemos por ejemplo el siguiente diagrama de organización de una empresa

**Figura page 9A**

A simple vista podemos apreciar que el presidente de la empresa tiene demasiados
subordinados, y consecuentemente su trabajo involucrará el manejo de demasiados datos y la
toma de demasiadas decisiones, demasiada complejidad, que lo llevará a cometer posibles
errores.
Podemos establecer una analogía con la estructura de programas y es razonable pensar que un
módulo que tenga demasiados módulos subordinados a quienes controlar, sea sumamente
complejo, y susceptible a fallas.
Veamos otro ejemplo

**Figura page 9B**

Podemos apreciar a simple vista que la tarea de los jefes A, X, Y, es relativamente trivial y
podría ser comprimida en una sola jefatura. Estableciendo una comparación con la estructura
de programas, si tenemos un módulo cuya única función es llamar a otro, y este a su vez a
otro, el cual llama a uno que finalmente realizará la tarea, los módulos intermedios podrán
comprimirse un único módulo de control.
Podemos decir que en una organización perfecta, los administradores no realizan ninguna
tarea operativa. Su labor consiste en coordinar información entre los subordinados y tomar
decisiones. Los niveles inferiores son los que realizan el trabajo operativo. Análogamente,
podemos argumentar que los módulos de nivel alto en un programa o sistema solamente
coordinan y controlan la ejecución de los módulos de menor nivel, quienes son los que
realizan los cómputos y procesos que el sistema requiere.
Finalmente observaremos que los administradores suministran a sus subordinados únicamente
la información que estrictamente necesitan. Análogamente los módulos inferiores solo deben
tener acceso a la información que necesitan, y no a otras.
El establecimiento de un paralelo entre las estructuras organizativas humanas y los programas
de computadora nos será muy útil en el estudio del diseño estructurado.
1.8 Manejo de la complejidad
En principio diremos que escribir un programa "grande" generalmente lleva más tiempo que
escribir uno "pequeño". Esto es valedero si medimos "grande" y "pequeño" en unidades
apropiadas. Claramente el número de instrucciones de un programa no es una medida de
complejidad ya que existen instrucciones más complejas que otras, y algoritmos más
complejos que otros. En realidad lo que diremos es que es más difícil resolver un problema
difícil! , e intentaremos realizar un análisis sobre como disminuir la complejidad de un
determinado problema.
Si asumimos que podemos medir por algún método la complejidad de un problema P (no
importa aquí que método), diremos que la complejidad del mismo será M(P), y que el costo
de realizar un programa que resuelva el problema P será C(P). Los enunciados previos
responderán a la siguiente regla:
dados dos problemas P y Q observaremos lo siguiente
```math #page10A 

Si M(P) > M(Q) entonces C(P) > C(Q)
```
es decir el costo de resolver un determinado problema es directamente proporcional al tamaño
del mismo.
Intentaremos tomar dos problemas separados y en lugar de escribir dos programas, crear un
programa combinado. Si juntamos los dos problemas, obtendremos uno mayor que si
tomamos los dos por separado. La razón fundamental para no combinar los problemas, es que
los humanos tenemos inconvenientes para tratar adecuadamente grandes complejidades, y en
la medida que esta se incrementa somos susceptibles a cometer un mayor número de errores.
En virtud de esto podemos afirmar que
```math #page10B
M(P+Q) > M(P) + M(Q)
```
y consecuentemente
```math #page11A
C(P+Q) > C(P) + C(Q)
```

Siempre será preferible crear dos piezas pequeñas que una sola más grande, si ambas
solucionan el mismo problema.
Este fenómeno no es solo válido para el campo de la computación. Es verdadero en cualquier
campo de la solución de problemas (matemática, física, etc.).
El psicólogo-matemático George Miller, realizó una serie de investigaciones sobre las
limitaciones en el procesamiento de información humano. Estos estudios determinaron que la
mente humana puede mantener y tratar simultáneamente hasta con siete objetos, o conceptos.
En efecto, la memoria necesaria para la resolución de problemas con múltiples elementos,
tiene una capacidad de 7  2 entidades. Por sobre este número la cantidad de errores se
incrementa desproporcionadamente en forma no lineal

**Figura page11A**


