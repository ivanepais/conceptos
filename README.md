# conceptos

|| Manejo de Excepciones
    
    Permite al programador controlar los errores ocasionados durante la ejecución de un programa informático. 

    Cuando ocurre cierto tipo de error, el sistema reacciona ejecutando un fragmento de código que resuelve la situación, por ejemplo retornando un mensaje de error o devolviendo un valor por defecto. 

    La definición de excepción se basa en la observación de que cada procedimiento tiene una condición previa, un conjunto de circunstancias por las cuales terminará "normalmente".

    Un mecanismo de manejo de excepciones permite que el procedimiento genere una excepción si se viola esta condición previa, por ejemplo, si el procedimiento ha sido llamado con un conjunto anormal de argumentos. 

    Luego, el mecanismo de manejo de excepciones maneja la excepción


    La condición previa y la definición de excepción son subjetivas.

    El conjunto de circunstancias "normales" lo define completamente el programador.  

    El programador puede considerar que la división por cero no está definida y, por lo tanto, es una excepción, o idear algún comportamiento como devolver cero o un valor especial de "DIVISIÓN CERO" (evitando la necesidad de excepciones). 


    Las excepciones comunes incluyen: 

        1. Argumento no válido (por ejemplo, el valor está fuera del dominio de una función).

        2. Recurso no disponible (como un archivo faltante, un error de unidad de red, o errores de falta de memoria), o que la rutina ha detectado una condición normal que requiere un manejo especial, por ejemplo, atención, fin de archivo.


    La presión social tiene una influencia importante en el alcance de las excepciones y el uso de mecanismos de manejo de excepciones, es decir, "ejemplos de uso, que generalmente se encuentran en bibliotecas principales y ejemplos de código en libros técnicos, artículos de revistas y foros de discusión en línea, y en los archivos de una organización". normas del código"


    El manejo de excepciones resuelve el problema del semipredicado, ya que el mecanismo distingue los valores de retorno normales de los erróneos. 

    En lenguajes sin manejo de excepciones incorporado, como C, las rutinas necesitarían señalar el error de alguna otra manera, como el código de retorno común y el patrón errno.

    Desde una perspectiva amplia, los errores pueden considerarse un subconjunto adecuado de excepciones y los mecanismos de error explícitos como errno pueden considerarse formas (detalladas) de manejo de excepciones.

    Se prefiere el término "excepción" a "error" porque no implica que algo esté mal: una condición vista como error por un procedimiento o programador puede no ser vista de esa manera por otro.

    El término "excepción" puede ser engañoso porque su connotación de "anomalía" indica que generar una excepción es anormal o inusual, cuando en realidad generar la excepción puede ser una situación normal y habitual en el programa. 

    Por ejemplo, supongamos que una función de búsqueda para una matriz asociativa genera una excepción si la clave no tiene ningún valor asociado. 

    Dependiendo del contexto, esta excepción de "clave ausente" puede ocurrir con mucha más frecuencia que una búsqueda exitosa.


    Los marcos de desarrollo web front-end, como React y Vue, han introducido mecanismos de manejo de errores donde los errores se propagan hacia arriba en la jerarquía de componentes de la interfaz de usuario (UI), de una manera análoga a cómo los errores se propagan hacia arriba en la pila de llamadas al ejecutar código. 

    Aquí el mecanismo de límite de error sirve como análogo al típico mecanismo try-catch. 

    Por lo tanto, un componente puede garantizar que los errores de sus componentes secundarios se detecten y manejen, y no se propaguen a los componentes principales.


    Subrutina: 

        Se presenta como un subalgoritmo que forma parte del algoritmo principal, el cual permite resolver una tarea específica.

        Es un segmento de código separado del bloque principal, el cual puede ser invocado en cualquier momento desde esta u otra subrutina.

        Una subrutina, al ser llamada dentro de un programa, hace que el código principal se detenga y se dirija a ejecutar el código de la subrutina. 


        Definición de una subrutina: 

            1. nombre único en el ámbito: 

                Nombre de la función con el que se identifica y se distingue de otras. 

                No podrá haber otra función ni procedimiento con ese nombre (salvo sobrecarga o polimorfismo en programación orientada a objetos).


            2. Un tipo de dato de retorno: 

                Tipo de dato del valor que la subrutina devolverá al terminar su ejecución.

            
            3. Una lista de parámetros: 

                Especificación del conjunto de argumentos (pueden ser cero, uno o más) que la función debe recibir para realizar su tarea.
    
            
            4. El código u órdenes de procesamiento: 

                Conjunto de órdenes y sentencias que debe ejecutar la subrutina.


            ```pseudocódigo

            PROGRAMA principal
                 instrucción 1
                 instrucción 2
                 ...
                 instrucción N
                 ...
                 SUBRUTINA NombreX
                    .......
                 FIN SUBRUTINA
                 ...
             FIN PROGRAMA principal.

            ```

        Ejemplo: 

            Función promedio para dos valores. 

            ```c

            float Promedio(int A, int B){
               float r;
               r=(A+B)/2.0;
               return r;
            }

            ```


            Función sin parámetros.

            ```c

            #include <stdio.h>

            int DecirHola(void) {
                printf ("¡Hola, Mundo!");
                return 0;
            }

            ```

            Imprimirá en la salida estándar "¡Hola, Mundo!". 


        Estas funciones pueden ser invocadas desde otras partes del programa con el objetivo principal es permitir la descomposición de un problema grande y/o complicado en partes que tienen una carga cognitiva relativamente baja y asignarles nombres significativos (a menos que sean anónimos).


    Problema Semipredicado: 

        Se produce un problema de semipredicado cuando una subrutina destinada a devolver un valor útil puede fallar, pero la señalización de falla utiliza un valor de retorno válido. 

        El problema es que quien llama a la subrutina no puede saber qué significa el resultado en este caso.


        Ejemplo:

            La operación de división produce un número real, pero falla cuando el divisor es cero. 

            Si tuviéramos que escribir una función que realice división, podríamos optar por devolver 0 en esta entrada no válida.

            Sin embargo, si el dividendo es 0, el resultado también es 0.

            Esto significa que no hay ningún número al que podamos regresar para señalar de manera única el intento de división por cero, ya que todos los números reales están en el rango de división.


        Las excepciones son la forma más conocida para resolver este problema. 

        Una condición de error no se considera en absoluto un valor de retorno de la función; El flujo de control normal se interrumpe y el manejo explícito del error se realiza automáticamente. 

        Son un ejemplo de señalización out-of-band.


        Otras soluciones amplian el valor de retorno: 

            1. Tipos híbridos creados manualmente

                En C, un enfoque común, cuando es posible, es utilizar un tipo de datos deliberadamente más amplio de lo estrictamente necesario para la función. 

                Por ejemplo, la función estándar getchar() se define con el tipo de retorno int y devuelve un valor en el rango [0, 255] (el rango de caracteres sin signo) en caso de éxito o el valor EOF (definido por la implementación, pero fuera del rango de carácter sin firmar) al final de la entrada o un error de lectura.


            2. Tipos de referencia que aceptan valores NULL: 

                En lenguajes con punteros o referencias, una solución es devolver un puntero a un valor, en lugar del valor en sí. 

                Este puntero de retorno se puede establecer en nulo para indicar un error. Normalmente es adecuado para funciones que devuelven un puntero de todos modos. 

                Esto tiene una ventaja de rendimiento sobre el estilo OOP de manejo de excepciones,[4] con el inconveniente de que los programadores negligentes pueden no verificar el valor de retorno, lo que resulta en un bloqueo cuando se utiliza el puntero no válido. 

                Si un puntero es nulo o no es otro ejemplo del problema de predicados; nulo puede ser un indicador que indica un error o el valor de un puntero devuelto correctamente. 

                Un patrón común en el entorno UNIX es establecer una variable separada para indicar la causa de un error. 

                Un ejemplo de esto es la función fopen() de la biblioteca estándar de C.


    Return Code: 

        Una declaración de retorno hace que la ejecución abandone la subrutina actual y se reanude en el punto del código inmediatamente después de la instrucción que llamó a la subrutina, conocido como su dirección de retorno. 

        La dirección de retorno la guarda la rutina de llamada, hoy generalmente en la pila de llamadas del proceso o en un registro. 

        Las declaraciones de retorno en muchos lenguajes de programación permiten que una función especifique un valor de retorno que se devolverá al código que llamó a la función


        En C y C++, devuelve exp; (donde exp es una expresión) es una declaración que le dice a una función que devuelva la ejecución del programa a la función que llama e informe el valor de exp. 

        Si una función tiene el tipo de retorno nulo, la declaración de retorno se puede usar sin un valor, en cuyo caso el programa simplemente sale de la función actual y regresa a la que llama. 

        Se utiliza una sintaxis similar en otros lenguajes, incluidos Modula-2 y Python.

        En algunos otros lenguajes se utiliza un parámetro de salida definido por el usuario en lugar del identificador de función.

        Algunos lenguajes de programación orientados a expresiones, como Lisp, Perl y Ruby, permiten al programador omitir una declaración de retorno explícita, especificando en su lugar que la última expresión evaluada es el valor de retorno de la subrutina. 

        En otros casos, se devuelve un valor nulo si no hay una declaración de retorno explícita: en Python, se devuelve el valor 'null' cuando se omite la declaración de retorno, mientras que en JavaScript se devuelve el valor 'undefined'

        Muchos sistemas operativos permiten que un programa devuelva un resultado (separado de la salida normal) cuando finaliza su proceso; estos valores se refieren a estados de salida (Exit status). 

        La cantidad de información que se puede transmitir de esta manera es bastante limitada y, en la práctica, a menudo se limita a señalar el éxito o el fracaso. 

        Desde dentro del programa, este retorno generalmente se logra llamando a Exit (llamada al sistema) (común incluso en C, donde está disponible el mecanismo alternativo de regresar desde la función principal).



        Cuando es omitido: 

            En el Bourne shell, valor de salida del último comando ejecutado en la función.

            En C y C++, 'undefined behavior' si la función devuelve valor

            En PHP, devuelve 'NULL'

            En Javascript devuelve el valor 'undefined'

            En Java y C#, no permitido si la función devuelve valor.

            En Python, 'none'. 


    Patrón errno: 

        errno.h es un archivo de encabezado en la biblioteca estándar del lenguaje de programación C. 

        Define macros para informar y recuperar condiciones de error utilizando el símbolo errno (abreviatura de "número de error").

        errno actúa como una variable entera. 

        Ciertas funciones de la biblioteca almacenan un valor (el número de error) en errno cuando detectan errores. 

        Al iniciar el programa, el valor almacenado es cero. 

        Las funciones de biblioteca almacenan sólo valores mayores que cero. 

        Cualquier función de biblioteca puede alterar el valor almacenado antes del retorno, detecte o no errores.

        La mayoría de las funciones indican que detectaron un error al devolver un valor especial, normalmente NULL para funciones que devuelven punteros y -1 para funciones que devuelven números enteros.

        Algunas funciones requieren que la persona que llama preestablezca errno en cero y lo pruebe después para ver si se detectó un error.

        La macro errno se expande a un valor l de tipo int, a veces con los especificadores de tipo externo y/o volátil dependiendo de la plataforma. 

        Originalmente, esta era una ubicación de memoria estática, pero hoy en día casi siempre se usan macros para permitir subprocesos múltiples, de modo que cada subproceso vea su propio número de error local de subproceso.

        El archivo de encabezado también define macros que se expanden a constantes enteras que representan los códigos de error. 

        La biblioteca estándar de C solo requiere que se definan tres.


        EDOM:

            Resultados de un parámetro fuera del dominio de una función, ej. 'sqrt(-1)'.


        ERANGE:

            Resultados de un resultado fuera del rango de una función, ej. 'strtol("0xffffffff", NULL, 0)' en sistemas con una longitud de 32 bits de ancho.


        EILSEQ (Requerido desde 1994 Enmienda 1 al estándar C89):

            Resultado de una secuencia de bytes ilegal, ej. 'mbstowcs(buf, "\xff", 1)' en sistemas que utilizan UTF-8.


    Exit status: 

        El estado de salida, o código de salida, de un proceso terminado es un número entero que se pone a disposición de su proceso padre (o llamador).

        En DOS, esto puede denominarse nivel de error.

        Cuando se ejecutan programas de computadora, el sistema operativo crea una entidad abstracta llamada proceso en el que se mantiene la contabilidad de ese programa.

        En sistemas operativos multitarea como Unix o Linux, los procesos activos pueden crear nuevos procesos. 

        El proceso que genera otro se llama proceso padre, mientras que los creados son procesos hijos. 

        Los procesos secundarios se ejecutan simultáneamente con el proceso principal. 

        La técnica de generación de procesos secundarios se utiliza para delegar parte del trabajo a un proceso secundario cuando no hay motivo para detener la ejecución del proceso primario. 

        Cuando el hijo termina de ejecutarse, sale llamando a la llamada al sistema de salida (exit system call).

        Esta llamada al sistema facilita pasar el código de estado de salida al padre, que puede recuperar este valor utilizando la llamada al sistema de espera (wait system call).


        C: 

            Permite que los programas que salen o regresan de la función principal indiquen el éxito o el fracaso al devolver un número entero o las macros EXIT_SUCCESS y EXIT_FAILURE. 

            En sistemas tipo Unix, estos son iguales a 0 y 1 respectivamente.

            Un programa en C también puede utilizar la función exit() especificando el estado del número entero o la macro de salida como primer parámetro.

            El valor de retorno de main se pasa a la función de salida, que para valores cero, EXIT_SUCCESS o EXIT_FAILURE pueden traducirlo a "una forma definida por la implementación" de terminación exitosa o terminación fallida.

            Aparte de cero y las macros EXIT_SUCCESS y EXIT_FAILURE, el estándar C no define el significado de los códigos de retorno.

            Las reglas para el uso de códigos de retorno varían en diferentes plataformas (consulte las secciones específicas de la plataforma)


        Java: 

            Cualquier método puede llamar a System.exit(int status), a menos que un administrador de seguridad no lo permita. 

            Esto finalizará la máquina virtual Java que se está ejecutando actualmente.

            "El argumento sirve como código de estado; por convención, un código de estado distinto de cero indica una terminación anormal".

    
    Call Stack: 

        Una pila de llamadas es una estructura de datos de pila que almacena información sobre las subrutinas activas de un programa de computadora. 

        Este tipo de pila también se conoce como pila de ejecución, pila de programa, pila de control, pila de tiempo de ejecución o pila de máquina y, a menudo, se abrevia simplemente como "la pila".

        Aunque el mantenimiento de la pila de llamadas es importante para el correcto funcionamiento de la mayoría del software, los detalles normalmente están ocultos y son automáticos en los lenguajes de programación de alto nivel. 

        Muchos conjuntos de instrucciones de computadora proporcionan instrucciones especiales para manipular pilas.

        Una pila de llamadas se utiliza para varios propósitos relacionados, pero la razón principal para tener una es realizar un seguimiento del punto al que cada subrutina activa debe devolver el control cuando termina de ejecutarse. 

        Una subrutina activa es aquella que ha sido llamada, pero aún no ha completado su ejecución, después de lo cual el control debe devolverse al punto de llamada. 

        Dichas activaciones de subrutinas pueden anidarse en cualquier nivel (recursivo como caso especial), de ahí la estructura de pila. 

        Por ejemplo, si una subrutina 'DrawSquare' llama a una subrutina 'DrawLine' desde cuatro lugares diferentes, 'DrawLine' debe saber dónde regresar cuando se complete su ejecución. 

        Para lograr esto, la dirección que sigue a la instrucción que salta a 'DrawLine', la dirección de retorno (return address), se coloca en la parte superior de la pila de llamadas con cada llamada.


        En los lenguajes de programación de alto nivel, los detalles de la pila de llamadas generalmente están ocultos para el programador.

        Sólo se les da acceso a un conjunto de funciones, y no a la memoria de la pila en sí. Este es un ejemplo de abstracción. 

        La mayoría de los lenguajes ensambladores, por otro lado, requieren que los programadores participen en la manipulación de la pila. 

        Los detalles reales de la pila en un lenguaje de programación dependen del compilador, el sistema operativo y el conjunto de instrucciones disponible.


        El objetivo principal de una pila de llamadas es almacenar las direcciones de retorno.

        Cuando se llama a una subrutina, la ubicación (dirección) de la instrucción en la que posteriormente se puede reanudar la llamada a la rutina debe guardarse en algún lugar. 

        El uso de una pila para guardar la dirección del remitente tiene ventajas importantes sobre algunas convenciones de llamada alternativas, como guardar la dirección del remitente antes del comienzo de la subrutina llamada o en alguna otra ubicación fija. 

        Una es que cada tarea puede tener su propia pila y, por lo tanto, la subrutina puede ser segura para subprocesos, es decir, capaz de estar activa simultáneamente para diferentes tareas que hacen cosas diferentes. 

        Otro beneficio es que al proporcionar reentrada, la recursividad se admite automáticamente. 

        Cuando una función se llama a sí misma de forma recursiva, se debe almacenar una dirección de retorno para cada activación de la función para que luego pueda usarse para regresar de la activación de la función. 

        Las estructuras de pila proporcionan esta capacidad automáticamente.

        Dependiendo del idioma, el sistema operativo y el entorno de la máquina, una pila de llamadas puede tener propósitos adicionales, que incluyen, por ejemplo:


        Almacenamiento de datos locales:
            
            Una subrutina frecuentemente necesita espacio de memoria para almacenar los valores de las variables locales, las variables que se conocen sólo dentro de la subrutina activa y no retienen valores después de que regresa.


        Paso de parámetros

            Las subrutinas a menudo requieren que el código que las llama les proporcione valores para los parámetros, y no es raro que se pueda disponer de espacio para estos parámetros en la pila de llamadas.


        Pila de evaluación:
            
            Los operandos para operaciones aritméticas o lógicas suelen colocarse en registros y operarse allí.


        Contexto de subrutina adjunto
            
            Algunos lenguajes de programación (por ejemplo, Pascal y Ada) admiten la declaración de subrutinas anidadas, a las que se les permite acceder al contexto de sus rutinas adjuntas, es decir, los parámetros y variables locales dentro del alcance de las rutinas externas.


        Contexto de bloque cerrado
            
            En algunos lenguajes, por ejemplo, ALGOL 60, PL/I, un bloque dentro de un procedimiento puede tener sus propias variables locales, asignadas al entrar al bloque y liberadas al salir del bloque. 

            De manera similar, el bloque puede tener sus propios controladores de excepciones, desactivados al salir del bloque.


        Otro estado de retorno;
            
            Además de la dirección del remitente, en algunos entornos puede haber otros estados de la máquina o del software que deben restaurarse cuando regresa una subrutina.


        La pila de llamadas típica se utiliza para la dirección de retorno, los locales y los parámetros (conocido como marco de llamada). 

        En algunos entornos puede haber más o menos funciones asignadas a la pila de llamadas. 

        En el lenguaje de programación Forth, por ejemplo, normalmente sólo la dirección de retorno, los índices y los parámetros del bucle contados y posiblemente las variables locales se almacenan en la pila de llamadas (que en ese entorno se denomina pila de retorno), aunque cualquier dato se puede colocar temporalmente. 

        Allí se utiliza un código especial de manejo de la pila de retorno siempre que se respeten las necesidades de llamadas y devoluciones; Los parámetros normalmente se almacenan en una pila de datos o pila de parámetros separada, generalmente llamada pila en la terminología Forth, aunque hay una pila de llamadas, ya que generalmente se accede a ella de manera más explícita. Algunos Forths también tienen una tercera pila para parámetros de punto flotante.


    Tipos de Excepciones: 

        Las excepciones se dividen en verificadas y no verificadas. 

        Es importante esta división porque el compilador implementa requerimientos de atrapar o declarar para las verificadas lo que hará que se detecten las excepciones automáticamente y de acuerdo al lenguaje de programación utilizado se utilizará un método para corregirlas. 

        Sin embargo para las que no verificadas se producirá un error indicando que deben atraparse y declararse. 

        Por eso el programador debe pensar en los problemas que pueden ocurrir cuando se llama a un método y definir excepciones para verificarse cuando sean importantes. 

        Las clases de excepciones pueden derivarse de una superclase común, por lo que con un manejador para atrapar objetos de la superclase, también se pueden atrapar todos los objetos de las subclases de esa clase. 

        Pero también, se pueden atrapar a cada uno de los tipos de las subclases de manera individual si estas requieren ser procesadas diferente.

        A cada célula se le conoce como compiladora de distintos.
    

    Limpieza de pila

        En ocasiones cuando se lanza una excepción, pero no se atrapa en un enlace específico, la pila de llamadas se limpia y el programa intenta volverlo a atrapar en el siguiente bloque, esto se conoce como limpieza de pila. 

        Este proceso hace que el método en el que no se atrapó la excepción termine, todas sus variables quedan fuera del enlace y el control regresa a la instrucción que originalmente la invocó. 

        La limpieza de pila se repetirá hasta que la excepción pueda ser atrapada porque de lo contrario se producirá un error a la hora de compilar.


    Aserciones:

        Las aserciones ayudan a asegurar la validez del programa al atrapar los errores potenciales e identificar los posibles errores lógicos del desarrollo. 

        Estas pueden escribirse como comentarios para apoyar a la persona que desarrolla el programa.

        
        Precondiciones y pos condiciones:

            Estas características son utilizadas por los programadores para hacer un análisis de lo esperado del programa antes y después de su ejecución.

            Son importantes porque gracias a ellas se pueden detectar posibles fallas en el programa y corregirlas.


            1. Las precondiciones son verdaderas cuando se invoca a un método, estas describen las características del método y las expectativas que se tienen en el estado actual del programa. 

            Si no se cumplen las precondiciones el comportamiento del método es indefinido por lo que se lanza una excepción que esté preparada o continuar con el programa esperando el error. 


            2. Las pos condiciones describen las restricciones en el entorno y cualquier efecto secundario del método. 

            Es recomendable escribirlas para saber que esperar en un futuro si es que se hacen modificaciones.


    Try-Catch:

        Al ejecutar código Java pueden ocurrir diferentes errores: errores de codificación cometidos por el programador, errores por entradas incorrectas u otras cosas imprevisibles.

        Cuando ocurre un error, Java normalmente se detendrá y generará un mensaje de error.

        El término técnico para esto es: Java generará una excepción (arrojará un error)/throw an exception (throw an error).


        Try: 
            
            Permite definir un bloque de código que se probará en busca de errores mientras se ejecuta.


        Catch: 

            Permite definir un bloque de código que se ejecutará si ocurre un error en el bloque try.


        Ejemplo de error sin try-catch: 

            Tiene una advertencia generica por parte del compilador. 

            ```java

            public class Main {
              public static void main(String[ ] args) {
                int[] myNumbers = {1, 2, 3};
                System.out.println(myNumbers[10]); // error!
              }
            }

            ```

            Output: 

                ```
                Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 10 at Main.main(Main.java:4) 

                ```


        Podemos manejar un error como este con Try-Catch: 


            ```java

            public class Main {
              public static void main(String[ ] args) {
                try {
                  int[] myNumbers = {1, 2, 3};
                  System.out.println(myNumbers[10]);
                } catch (Exception e) {
                  System.out.println("Something went wrong.");
                }
              }
            }

            ```

            Output: 

                ```
                Something went wrong. 

                ```


    Finally
        
        Permite ejecutar código, después de try-catch, independientemente del resultado.

        Es crucial en los casos en los que es posible que sea necesario liberar los recursos ocupados. 

        Por ejemplo, cerrar conexiones a archivos, etc. 


        ```java

        public class Main {
          public static void main(String[] args) {
            try {
              int[] myNumbers = {1, 2, 3};
              System.out.println(myNumbers[10]);
            } catch (Exception e) {
              System.out.println("Something went wrong.");
            } finally {
              System.out.println("The 'try catch' is finished.");
            }
          }
        }

        ```

        Output: 

            ```     
            Something went wrong.
            The 'try catch' is finished. 

            ```


    Ejemplos: 

        ```java
        
        public class ExcDemo {
            public static void main(String[] args) {
                int nums[]=new int[4];
                try {
                    System.out.println("Antes de que se genere la excepción.");
                    //generar una excepción de índice fuera de límites
                    nums[7]=10;
                }catch (ArrayIndexOutOfBoundsException exc){
                    //Capturando la excepción
                    System.out.println("Índice fuera de los límites!");
                } finally {
                System.out.println("Después de que se genere la excepción.");
                }
            }
        }
        
        ```
        

        ```python 

        try:
            result = x / y
        except ZeroDivisionError:
            print "division by zero!"
        else:
            print "result is", result
        finally:
            print "executing finally clause"

        ```
    

    Throw: 

        Permite crear un error personalizado.

        La declaración throw se usa junto con un tipo de excepción. 

        Hay muchos tipos de excepciones disponibles en Java: 'ArithmeticException', 'FileNotFoundException', 'ArrayIndexOutOfBoundsException', 'SecurityException'.


        ```java

        public class Main {
          static void checkAge(int age) {
            if (age < 18) {
              throw new ArithmeticException("Access denied - You must be at least 18 years old.");
            }
            else {
              System.out.println("Access granted - You are old enough!");
            }
          }

          public static void main(String[] args) {
            checkAge(15); // Set age to 15 (which is below 18...)
          }
        }

        ```


        Output: 

            ```
            Exception in thread "main" java.lang.ArithmeticException: Access denied - You must be at least 18 years old.
                at Main.checkAge(Main.java:4)
                at Main.main(Main.java:12) 

            ```


        Si la llamamos con el valor 20: 

            ```
            checkAge(20);

            ```

            Output: 

                ```
                Access granted - You are old enough! 

                ```


    Try/catch/finally, throw en main y métodos: 

        Una excepción es un tipo especial de objeto. 

        Cuando escribe 'new excepción()', está creando un nuevo objeto de excepción.

        Cuando escribes 'throw new Exception()' estás creando un nuevo error y luego lo arrojas al bloque try-catch más cercano, abortando el resto de tu código.

        Cuando lanzas una excepción, queda atrapada por el bloque try-catch en el que está anidada. 

        Es decir, suponiendo que esté registrado el bloque catch adecuado para esa excepción.

        Si el código no está incluido en un bloque try-catch, el programa se cerrará automáticamente tan pronto como se produzca un error.

        Utilice un try-catch en torno a cualquier código o método que pueda generar un error, especialmente debido a la entrada del usuario (dentro de lo razonable).

        Algunas excepciones deben detectarse, otras son opcionales (checked versus no unchecked).

        Cuando agrega lanzamientos a la firma de un método, está anunciando a otros métodos que si llaman a ese método, tiene el potencial de generar una excepción marcada (no es necesario para los no marcados). 

        Utiliza esta funcionalidad cuando no desea detectar el error dentro de ese método, pero desea permitir que los métodos que llaman a su método detecten el error por sí mismos.

        Las excepciones son una forma de hacer que su programa responda de manera coherente a situaciones inesperadas o no válidas y son especialmente útiles cuando se requiere la entrada del usuario, aunque también son útiles en otras situaciones como la entrada/salida de archivos.


        'throws' es una declaración de que un método generará ciertas excepciones. 

        Esto lo aplica el compilador de Java para las excepciones comprobadas, y no para los errores o las excepciones no comprobadas.

        "throw new": 

            "throw" es un operador que lanza una excepción.
             
            "new" es un operador que crea una nueva instancia de un objeto.

        El bloque "try" le permite ejecutar métodos que declaran que arrojan excepciones, y ahí es donde usa la cláusula "catch", para detectar esas excepciones lanzadas.

        Además, también existe el bloque de try con recursos donde puede usar un bloque try para operar en un recurso consumible (por ejemplo, una secuencia) que implementa 'AutoCloseable' y luego cerrarlo.

        También existe la cláusula "finally" para un bloque try, que le permite ejecutar la limpieza o cualquier otro método que DEBE ejecutarse después de un bloque try, independientemente de si ocurren excepciones o no.


        En Java, puedes utilizar varios bloques catch.

        No significa necesariamente que tengas que hacerlo.

        Depende del código que tenga en el bloque try y de cuántas excepciones marcadas pueda generar (o incluso excepciones no marcadas si realmente desea detectarlas, normalmente no es así y no es necesario).

        Una mala práctica es utilizar un único controlador para la excepción general (o peor, Throwable, que también detectaría RuntimeExceptions y errores):

            ```java

            try {
                // cosas que arrojan múltiples excepciones
            }
            // mala practica
            catch (Excepción e) {
                // HACER
            }

            ```

        La buena práctica es detectar todas las excepciones marcadas potencialmente lanzadas.

        Si algunas de ellas están relacionadas en términos de herencia, siempre capture primero las clases secundarias (es decir, las excepciones más específicas), para que su código no se compile:

            ```java

            try {
                // cosas que arrojan FileNotFoundException Y IOException
            }
                // buena practica: FileNotFoundException es una clase secundaria de IOException - ambas marcadas
            catch (FileNotFoundException fnfe) {
                 // HACER
            }
            catch (IOException ioe) {
                 // HACER
            }

            ```

      
        También eche un vistazo a los bloques multicaptura de Java 7, donde las excepciones no relacionadas se pueden capturar todas a la vez con un | separador entre cada tipo de excepción:

        ```java

        try (opcionalmente con recursos) {
             // cosas que arrojan FileNotFoundException y MyOwnCheckedException
        }
        // las siguientes excepciones no están relacionadas
        catch (FileNotFoundException | MyOwnCheckedException e) {
             // HACER
        }

        ```

        Nota

            En este ejemplo al que se vinculó, el primer fragmento de código a continuación. 

            Poniéndolo todo junto puede considerarse subóptimo: detecta las excepciones potencialmente lanzadas, pero una de ellas es una IndexOutOfBoundsException, que es una RuntimeException (sin marcar) y debería no se puede abordar en teoría.

            En su lugar, la variable TAMAÑO (o probablemente constante) debe reemplazarse por una referencia al tamaño de la Lista que se está iterando, es decir, list.size(), para evitar que se lance IndexOutOfBoundsException.


    Hay dos tipos de excepciones.

        1. unchecked:

            Estos están definidos por las clases Error y RuntimeException y todas sus subclases. 

            Java no le obliga a manejar estas excepciones de ninguna manera.


        2. checked: 

            Estos se definen como la clase Throwable y todas sus subclases que no entran en la categoría definida en (1). 

            Java te obliga a manejar estas excepciones con un try/catch. 

            Si llama a un método que puede generar dicha excepción (definida con la palabra clave throws) fuera de un bloque try, su código no se compilará.


        throws: 

            Esta es una forma de declarar que un método puede potencialmente generar una excepción que debe detectarse con un try/catch. 

            ```java

            public void doSomething() throws MyException { ... }

            ```

            Es una declaración de un método que potencialmente puede generar una instancia de MyException.

            
            try/catch/finally: 

                Esta es una forma de manejar excepciones que pueden producirse mediante algún tipo de código. 

                El código que está intentando ejecutar va en el bloque try, el código de manejo de errores va en el bloque catch. 

                El bloque finalmente opcional es algo que se ejecutará independientemente de si se lanza o no una excepción. 

                De hecho, se llamará al bloque finalmente incluso si realiza una devolución dentro de su intento o captura. Por ejemplo

                ```java

                try {
                    doSomething();
                } catch (MyException exception) {
                    exception.printStackTrace();
                }

                ```

            o un ejemplo de uso 'finally':

                ```java

                MyResource myResource = getMyResource();
                
                try {
                    myResource.open();
                    doStuffWithMyResource(myResource);
                } catch (Exception exception) {
                    exception.printStackTrace();
                } finally {
                    if (myResource.isOpen()) {
                        myResource.close();
                    }
                }

                ```

        

|| Estrategia de Evaluación 

    
    Funciones: 

        Una función, subprograma, procedimiento, método, rutina o subrutina es una unidad invocable que tiene un comportamiento bien definido y puede ser invocada por otras unidades de software para exhibir ese comportamiento.

        Las unidades invocables proporcionan una poderosa herramienta de programación.

        El objetivo principal es permitir la descomposición de un problema grande y/o complicado en partes que tienen una carga cognitiva relativamente baja y asignarles nombres significativos (a menos que sean anónimos). 

        Una aplicación sensata puede reducir el costo de desarrollo y mantenimiento de software, al tiempo que aumenta su calidad y confiabilidad.

        Las unidades invocables están presentes en múltiples niveles de abstracción en el entorno de programación. 

        Por ejemplo, un programador puede escribir una función en código fuente que se compila en código de máquina que implementa una semántica similar. 

        Hay una unidad invocable en el código fuente y una asociada en el código máquina, pero son diferentes tipos de unidades invocables, con diferentes implicaciones y características.


        Bibliotecas: 

            El nombre biblioteca de subrutinas originalmente significaba una biblioteca, en sentido literal, que mantenía colecciones indexadas de cintas o barajas de cartas para uso colectivo.

            Las subrutinas resultaron muy útiles.

            Permitieron el uso del mismo código en muchos programas diferentes. 

            La memoria era un recurso muy escaso en las primeras computadoras y las subrutinas permitían ahorros significativos en el tamaño de los programas.

            Muchas de las primeras computadoras cargaban las instrucciones del programa en la memoria desde una cinta de papel perforada.

            Cada subrutina podría entonces ser proporcionada por un trozo de cinta separado, cargado o empalmado antes o después del programa principal (o "línea principal"); y la misma cinta de subrutina podría ser utilizada por muchos programas diferentes. 

            Se utilizó un enfoque similar en computadoras que cargaban instrucciones de programas a partir de tarjetas perforadas.


        Return salto indirecto

            Para eliminar la necesidad de un código automodificado, los diseñadores de computadoras finalmente proporcionaron una instrucción de salto indirecto, cuyo operando, en lugar de ser la dirección de retorno en sí, era la ubicación de una variable o registro del procesador que contenía la dirección de retorno.

            En esas computadoras, en lugar de modificar el salto de retorno de la función, el programa que llama almacenaría la dirección de retorno en una variable para que cuando la función se completara, ejecutara un salto indirecto que dirigiría la ejecución a la ubicación dada por la variable predefinida.

        
        Saltar a subrutina

            Otro avance fue el salto a la instrucción de subrutina, que combinaba el guardado de la dirección del remitente con el salto de llamada, minimizando así significativamente los gastos generales.


    Call Stack: 

        La mayoría de las implementaciones modernas de una llamada a función utilizan una pila de llamadas, un caso especial de la estructura de datos de la pila, para implementar llamadas y retornos a funciones. 

        Cada llamada a procedimiento crea una nueva entrada, llamada marco de pila (stack frame), en la parte superior de la pila (top of the stack); cuando el procedimiento regresa, su marco de pila se elimina de la pila y su espacio puede usarse para otras llamadas a procedimientos. 

        Cada marco de pila contiene los datos privados de la llamada correspondiente, que normalmente incluyen los parámetros y variables internas del procedimiento, y la dirección de retorno.

        La secuencia de llamada se puede implementar mediante una secuencia de instrucciones ordinarias (un enfoque todavía utilizado en arquitecturas de computación con conjunto de instrucciones reducido (RISC) y palabras de instrucción muy largas (VLIW), pero muchas máquinas tradicionales diseñadas desde finales de la década de 1960 han incluido instrucciones especiales para ese propósito.


        La pila de llamadas suele implementarse como un área contigua de memoria. 

        Es una elección de diseño arbitraria si la parte inferior de la pila es la dirección más baja o más alta dentro de esta área, de modo que la pila pueda crecer hacia adelante o hacia atrás en la memoria; sin embargo, muchas arquitecturas eligieron lo último.

        Algunos diseños, en particular algunas implementaciones de Forth, utilizaban dos pilas separadas, una principalmente para información de control (como direcciones de retorno y contadores de bucle) y la otra para datos. 

        El primero era, o funcionaba como, una pila de llamadas y el programador sólo podía acceder indirectamente a través de otras construcciones del lenguaje, mientras que el segundo era accesible más directamente.

        Cuando se introdujeron por primera vez las llamadas a procedimientos basados en pila, una motivación importante fue ahorrar memoria preciosa.

        Con este esquema, el compilador no tiene que reservar espacio separado en la memoria para los datos privados (parámetros, dirección de retorno y variables locales) de cada procedimiento. 

        En cualquier momento, la pila contiene solo los datos privados de las llamadas que están actualmente activas (es decir, las que han sido llamadas pero aún no han regresado). 

        Debido a la forma en que los programas generalmente se ensamblaban a partir de bibliotecas, no era (y sigue siendo) raro encontrar programas que incluyen miles de funciones, de las cuales sólo unas pocas están activas en un momento dado.

        El mecanismo de pila de llamadas podría ahorrar cantidades significativas de memoria. 

        De hecho, el mecanismo de pila de llamadas puede verse como el método más antiguo y sencillo para la gestión automática de la memoria.

        Sin embargo, otra ventaja del método de pila de llamadas es que permite llamadas a funciones recursivas, ya que cada llamada anidada al mismo procedimiento obtiene una instancia separada de sus datos privados.

        En un entorno de subprocesos múltiples, generalmente hay más de una pila.

        Un entorno que admita totalmente corrutinas o evaluación diferida puede utilizar estructuras de datos distintas de las pilas para almacenar sus registros de activación.

        Apilamiento atrasado: 

            Una desventaja del mecanismo de pila de llamadas es el mayor costo de una llamada a procedimiento y su retorno coincidente. 

            El costo adicional incluye incrementar y disminuir el puntero de la pila (y, en algunas arquitecturas, verificar el desbordamiento de la pila) y acceder a la pila, 
            variables y parámetros locales por direcciones relativas al marco, en lugar de direcciones absolutas. 

            El costo puede materializarse en un mayor tiempo de ejecución, una mayor complejidad del procesador, o ambas cosas.

            Esta sobrecarga es más obvia y objetable en los procedimientos hoja o funciones hoja, que regresan sin realizar ninguna llamada a ningún procedimiento.

            Para reducir esa sobrecarga, muchos compiladores modernos intentan retrasar el uso de una pila de llamadas hasta que sea realmente necesaria.

            Por ejemplo, la llamada de un procedimiento P puede almacenar la dirección de retorno y los parámetros del procedimiento llamado en cierto procesador registros y transferir el control al cuerpo del procedimiento mediante un simple salto. 

            Si el procedimiento P regresa sin realizar ninguna otra llamada, la pila de llamadas no se utiliza en absoluto. Si P necesita llamar a otro procedimiento Q, entonces usará la pila de llamadas para guardar el contenido de cualquier registro (como la dirección de retorno) que será necesario después de que Q regrese.


        Características: 

            Una unidad invocable es una lista de instrucciones que, comenzando con la primera instrucción, se ejecuta secuencialmente excepto según lo indique su lógica interna. 

            Se puede invocar (llamar) muchas veces durante la ejecución de un programa.

            La ejecución continúa en la siguiente instrucción después de la instrucción de llamada cuando devuelve el control.


            La mayoría de los lenguajes de programación modernos proporcionan funciones para definir y llamar funciones, incluida la sintaxis para acceder a dichas funciones, que incluyen:

                
            Delimitar la implementación de una función del resto del programa.

             
            Asignar un identificador, nombre, a una función.

             
            Definir parámetros formales con un nombre y tipo de datos para cada uno.

             
            Asigne un tipo de datos al valor de retorno, si corresponde.

             
            Especifique un valor de retorno en el cuerpo de la función.

            
            Llamar a una función.

            
            Proporcionar parámetros reales que correspondan a los parámetros reales de una función llamada.

            
            Devolver el control a la llamada en el punto de llamada.

            
            Consumir el valor de retorno en la llamada.

            
            Disponer de los valores devueltos por una llamada.

            
            Proporcionar un ámbito de denominación privado para las variables.

            
            Identificar variables fuera de la función a las que se puede acceder dentro de ella.

            
            Propagar una condición excepcional fuera de una función y manejarla en el contexto de llamada.

            
            Empaquetar funciones en un contenedor como módulo, biblioteca, objeto o clase.


        Nombre:

            Algunos lenguajes, como Pascal, Fortran, Ada y muchos dialectos de BASIC, usan un nombre diferente para una unidad invocable que devuelve un valor (función o subprograma) frente a una que no lo hace (subrutina o procedimiento). 

            Otros lenguajes, como C, C++, C# y Lisp, usan solo un nombre para una unidad invocable, función. 

            Los lenguajes de la familia C utilizan la palabra clave void para indicar que no hay valor de retorno.

        
        Sintaxis de llamada:

            Si se declara que devuelve un valor, se puede incrustar una llamada en una expresión para consumir el valor de retorno. 

            Por ejemplo, una unidad exigible de raíz cuadrada podría denominarse como y = sqrt(x).

                y es la variable. 

                sqrt(x) es la función. 

            Una unidad invocable que no devuelve un valor se llama como una declaración independiente como print("hola"). 

            Esta sintaxis también se puede utilizar para una unidad invocable que devuelve un valor, pero el valor devuelto se ignorará.

            Algunos lenguajes más antiguos requieren una palabra clave para las llamadas que no consumen un valor de retorno, como CALL print("hola").


        Parámetros:
        
            La mayoría de las implementaciones, especialmente en lenguajes modernos, admiten parámetros que el invocable declara como parámetros formales. 

            Una persona que llama pasa parámetros reales, también conocidos como argumentos, para que coincidan. 

            Los diferentes lenguajes de programación proporcionan diferentes convenciones para pasar argumentos.


            Parámetros por valor: 

                Se pasa una copia del argumento.

                Como Pascal, Delphi, Simula, CPL, PL/M, Modula, Oberon, Ada, and many others including C, C++ and Java.


            Parámetros por referencia: 

                Se pasa una referencia al argumento; normalmente su dirección. 

                Como Algol 68, Pascal, Delphi, Simula, CPL, PL/M, Modula, Oberon, Ada, and many others including C++, Fortran, PL/I. 


        Valor de retorno:
            
            En algunos lenguajes, como BASIC, un invocable tiene una sintaxis diferente (es decir, una palabra clave) para un invocable que devuelve un valor frente a uno que no lo hace. 

            En otros idiomas, la sintaxis es la misma independientemente. 

            En algunos de estos idiomas se utiliza una palabra clave adicional para declarar que no hay valor de retorno; por ejemplo, nulo en C, C++ y C#. 

            En algunos lenguajes, como Python, la diferencia es si el cuerpo contiene una declaración de retorno con un valor, y un invocable particular puede regresar con o sin un valor según el flujo de control.


        Efectos secundarios:

            En muchos contextos, un invocable puede tener un comportamiento de efectos secundarios, como modificar datos pasados o globales, leer o escribir en un dispositivo periférico, acceder a un archivo, detener el programa o la máquina, o pausar temporalmente la ejecución del programa.

            En lenguajes de programación estrictamente funcionales como Haskell, una función no puede tener efectos secundarios, lo que significa que no puede cambiar el estado del programa. 

            Las funciones siempre devuelven el mismo resultado para la misma entrada. 

            Por lo general, estos lenguajes solo admiten funciones que devuelven un valor, ya que no hay ningún valor en una función que no tenga valor de retorno ni efectos secundarios.


        Variables locales:

            La mayoría de los contextos admiten variables locales: memoria propiedad de un invocable para contener valores intermedios. 

            Estas variables generalmente se almacenan en el registro de activación de la llamada en la pila de llamadas junto con otra información como la dirección del remitente.


        Llamada anidada – recursividad:

            Si el lenguaje lo admite, un invocable puede llamarse a sí mismo, provocando que su ejecución se suspenda mientras se ejecuta otra ejecución anidada del mismo invocable. 

            La recursividad es un medio útil para simplificar algunos algoritmos complejos y analizar problemas complejos. 

            Los lenguajes recursivos proporcionan una nueva copia de las variables locales en cada llamada.

            Si el programador desea que el recursivo invocable use las mismas variables en lugar de locales, generalmente las declara en un contexto compartido, como estático o global.

            Los lenguajes que se remontan a ALGOL, PL/I y C y los lenguajes modernos casi invariablemente utilizan una pila de llamadas, generalmente respaldada por conjuntos de instrucciones para proporcionar un registro de activación para cada llamada. 

            De esa manera, una llamada anidada puede modificar sus variables locales sin afectar ninguna de las variables de las llamadas suspendidas.

            La recursividad permite la implementación directa de funcionalidades definidas por inducción matemática y algoritmos recursivos de divide y vencerás.


        Alcance anidado

            Algunos lenguajes, por ejemplo, Ada, Pascal, PL/I, Python, admiten la declaración y definición de una función interna, por ejemplo, el cuerpo de una función, de modo que el nombre de la interna solo sea visible dentro del cuerpo de la externa.

        
        Sobrecarga

            Algunos lenguajes admiten la sobrecarga: permiten múltiples invocables con el mismo nombre en el mismo ámbito, pero que operan en diferentes tipos de entrada. 

            Considere la función de raíz cuadrada aplicada a números reales, números complejos y entradas matriciales. 

            El algoritmo para cada tipo de entrada es diferente y el valor de retorno puede tener un tipo diferente.

            Escribiendo tres invocables separados con el mismo nombre. 

            es decir, sqrt, el código resultante puede ser más fácil de escribir y mantener ya que cada uno tiene un nombre que es relativamente fácil de entender y recordar en lugar de dar nombres más largos y complicados como sqrt_real, sqrt_complex, qrt_matrix.

            La sobrecarga se admite en muchos lenguajes que admiten escritura segura. 

            A menudo, el compilador selecciona la sobrecarga a llamar según el tipo de argumentos de entrada o falla si los argumentos de entrada no seleccionan una sobrecarga. 

            Los lenguajes más antiguos y con tipos débiles generalmente no admiten la sobrecarga.

        
        Closure:

            Un cierre es un valor invocable más de algunas de sus variables capturadas del entorno en el que fue creado. 

            Los cierres fueron una característica notable del lenguaje de programación Lisp, introducido por John McCarthy. 

            Dependiendo de la implementación, los cierres pueden servir como mecanismo para efectos secundarios.


        Optimización de las funciones: 

            Una llamada tiene una sobrecarga de tiempo de ejecución, que puede incluir:


            Asignar y reclamar almacenamiento de la pila de llamadas.


            Guardar y restaurar registros del procesador.


            Copiar variables de entrada.


            Copiar valores después de la llamada en el contexto de la persona que llama.

            Prueba automática del código de retorno.


            Manejo de excepciones.

            
            Despacho, como por ejemplo para un método virtual en un lenguaje orientado a objetos.

        
            Se emplean varias técnicas para minimizar el costo de tiempo de ejecución de las llamadas.


            Optimización del compilador:

                Algunas optimizaciones para minimizar la sobrecarga de llamadas pueden parecer sencillas, pero no se pueden utilizar si lo invocable tiene efectos secundarios.

                Por ejemplo, en la expresión (f(x)-1)/(f(x)+1), la función f no se puede llamar solo una vez y su valor se usa dos veces, ya que las dos llamadas pueden devolver resultados diferentes.

                Además, en los pocos lenguajes que definen el orden de evaluación de los operandos del operador de división, el valor de x debe recuperarse nuevamente antes de la segunda llamada, ya que la primera llamada puede haberlo cambiado.

                Determinar si un valor exigible tiene un efecto secundario es difícil; de hecho, indecidible en virtud del teorema de Rice.

                Entonces, si bien esta optimización es segura en un lenguaje de programación puramente funcional, un compilador para un lenguaje que no se limita a lo funcional generalmente asume el peor de los casos, que cada invocable puede tener efectos secundarios.


            En línea:
            
                La inserción elimina las llamadas a callables particulares. 

                El compilador reemplaza cada llamada con el código compilado del invocable. 

                Esto no solo evita la sobrecarga de la llamada, sino que también permite que el compilador optimice el código de la persona que llama de manera más efectiva al tener en cuenta el contexto y los argumentos de esa llamada. 

                Sin embargo, la inserción generalmente aumenta el tamaño del código compilado, excepto cuando solo se llama una vez o el cuerpo es muy corto, como una línea.


            Intercambio

                Los callables se pueden definir dentro de un programa o por separado en una biblioteca que puede ser utilizada por múltiples programas.

            
            Interoperabilidad

                Un compilador traduce declaraciones de llamada y devolución en instrucciones de máquina de acuerdo con una convención de llamada bien definida.

                Para el código compilado por el mismo compilador o por uno compatible, las funciones se pueden compilar por separado de los programas que las llaman. 

                Las secuencias de instrucciones correspondientes a las declaraciones de llamada y devolución se denominan prólogo y epílogo del procedimiento.

            
            Funciones integradas

                Una función incorporada, o función incorporada, o función intrínseca, es una función para la cual el compilador genera código en el momento de la compilación o lo proporciona de una manera distinta a otras funciones. 

                No es necesario definir una función integrada como otras funciones, ya que está integrada en el lenguaje de programación.


    Estrategias de evaluación: 

        En un lenguaje de programación, una estrategia de evaluación es un conjunto de reglas para evaluar expresiones.

        El término se utiliza a menudo para referirse a la noción más específica de estrategia de paso de parámetros que define el tipo de valor que se pasa a la función para cada parámetro (la estrategia de enlace) y si se deben evaluar los parámetros de una llamada a función y, de ser así, en qué orden (el orden de evaluación). 

        La noción de estrategia de reducción es distinta, aunque algunos autores combinan los dos términos y la definición de cada término no existe un consenso generalizado.

        Para ilustrar, ejecutar una llamada a la función f(a,b) puede primero evaluar los argumentos a y b, almacenar los resultados en referencias o ubicaciones de memoria ref_a y ref_b, luego evaluar el cuerpo de la función con esas referencias pasadas. 

        Esto le da a la función la capacidad de buscar los valores de los argumentos, modificarlos mediante asignación como si fueran variables locales y devolver valores a través de las referencias. 

        Esta es la estrategia de evaluación de llamada por referencia.

        La estrategia de evaluación es parte de la semántica de la definición del lenguaje de programación. 

        Algunos lenguajes, como PureScript, tienen variantes con diferentes estrategias de evaluación. 

        Algunos lenguajes declarativos, como Datalog, admiten múltiples estrategias de evaluación. 

        Algunos idiomas definen una convención de llamada.


        Orden de evaluación: 

            Mientras que el orden de las operaciones define el árbol de sintaxis abstracta de la expresión, el orden de evaluación define el orden en el que se evalúan las expresiones.


            Evaluación estricta:

                El orden aplicativo es una familia de órdenes de evaluación en la que los argumentos de una función se evalúan completamente antes de aplicar la función.

                Esto tiene el efecto de hacer que la función sea estricta, es decir, el resultado de la función no está definido si alguno de los argumentos no está definido, por lo que la evaluación del orden aplicativo se denomina más comúnmente evaluación estricta. 

                Además, una llamada a una función se realiza tan pronto como se encuentra en un procedimiento, por lo que también se denomina evaluación ansiosa o evaluación codiciosa.

                Algunos autores se refieren a la evaluación estricta como "llamada por valor" debido a la estrategia de vinculación de llamada por valor
                requiriendo una evaluación estricta

                Common Lisp, Eiffel y Java evalúan los argumentos de las funciones de izquierda a derecha, C deja el orden sin definir.

                El esquema requiere que el orden de ejecución sea la ejecución secuencial de una permutación no especificada de los argumentos.

                OCaml tampoco especifica el orden, pero en la práctica evalúa los argumentos de derecha a izquierda debido al diseño de su máquina abstracta.

                Todos estos son una evaluación estricta.


            Evaluación no estricta:

                En un orden de evaluación no estricto, una función puede devolver un resultado antes de que todos sus argumentos sean evaluados por completa. 

                El ejemplo prototípico es la evaluación de orden normal, que no evalúe ninguno de los argumentos hasta que sean necesarios en el cuerpo de la función.

                La evaluación normal de una orden tiene la propiedad de terminar sin errores siempre que cualquier otra orden de evaluación hubiera terminado sin errores.

                El nombre "orden normal" proviene del cálculo lambda, donde la reducción de orden normal encontrará una forma normal, si la hay (es una estrategia de reducción "normalizadora"). 

                La evaluación diferida se clasifica en este artículo como una técnica vinculante en lugar de un orden de evaluación. 

                Pero esta distinción no siempre se sigue y algunos autores definen la evaluación diferida como evaluación de orden normal o viceversa o confunden la no rigurosidad con la evaluación diferida.

                Las expresiones booleanas en muchos idiomas utilizan una forma de evaluación no estricta llamada evaluación de cortocircuito, donde la evaluación evalúa la expresión izquierda pero puede omitir la expresión derecha si se puede determinar el resultado; por ejemplo, en una expresión disyuntiva (OR) donde es verdadero se encuentra, o en una expresión conjuntiva (Y) donde se encuentra falso, y así sucesivamente.

                Las expresiones condicionales utilizan de manera similar una evaluación no estricta: solo se evalúa una de las ramas.


            Comparación del orden aplicativo y la evaluación del orden normal:

                Con la evaluación de orden normal, las expresiones que contienen un cálculo costoso, un error o un bucle infinito se ignorarán si no son necesarias, permitiendo la especificación de construcciones de flujo de control definidas por el usuario, una función no disponible con la evaluación de orden aplicativa. 

                La evaluación de orden normal utiliza estructuras complejas, como procesadores para expresiones no evaluadas, en comparación con la pila de llamadas utilizada en la evaluación de orden aplicativa.

                Históricamente, la evaluación normal de órdenes ha carecido de herramientas de depuración utilizables debido a su complejidad.


        Estrategias estricta para vincular parámetros: 

            Llamar por valor:

                Al llamar por valor (o pasar por valor), el valor evaluado de la expresión del argumento se vincula a la variable correspondiente en la función (frecuentemente copiando el valor en una nueva región de memoria). 

                Si la función o procedimiento puede asignar valores a sus parámetros, solo se asigna su variable local; es decir, todo lo que se pasa a una llamada de función no cambia en el alcance de la persona que llama cuando la función regresa. 

                Por ejemplo, en Pascal, pasar una matriz por valor hará que se copie toda la matriz y cualquier mutación en esta matriz será invisible para la persona que llama.


            Llamar por referencia:
                
                Llamar por referencia (o pasar por referencia) es una estrategia de evaluación en la que un parámetro está vinculado a una referencia implícita a la variable utilizada como argumento, en lugar de una copia de su valor. 

                Por lo general, esto significa que la función puede modificar (es decir, asignar) la variable utilizada como argumento, algo que será visto por quien la llama. 

                Por lo tanto, la llamada por referencia se puede utilizar para proporcionar un canal adicional de comunicación entre la función llamada y la función que llama.

                Pasar por referencia puede mejorar significativamente el rendimiento: llamar a una función con una estructura de muchos megabytes como argumento no tiene que copiar la estructura grande, solo la referencia a la estructura (que generalmente es una palabra de máquina y solo unos pocos bytes). 

                Sin embargo, un lenguaje de llamada por referencia hace que sea más difícil para un programador rastrear los efectos de una llamada a función y puede introducir errores sutiles.


    Stack overflow - Desbordamiento de la pila de llamada: 

        Se produce un desbordamiento de la pila si el puntero de la pila de llamadas excede el límite de la pila (stack pointer exceeds the stack bound). 

        La pila de llamadas puede consistir en una cantidad limitada de espacio de direcciones, a menudo determinada al inicio del programa. 

        El tamaño de la pila de llamadas depende de muchos factores, incluido el lenguaje de programación, la arquitectura de la máquina, los subprocesos múltiples y la cantidad de memoria disponible. 

        Cuando un programa intenta utilizar más espacio del que está disponible en la pila de llamadas (es decir, cuando intenta acceder a la memoria más allá de los límites de la pila de llamadas, lo que es esencialmente un desbordamiento del búfer), se dice que la pila se desborda, lo que generalmente resulta en un caída del programa.


        Recursividad infinita:

            La causa más común del desbordamiento de la pila es la recursión excesivamente profunda o infinita, en la que una función se llama a sí misma tantas veces que el espacio necesario para almacenar las variables y la información asociada con cada llamada es más de lo que cabe en la pila.


        Recursividad muy profunda:

            Una función recursiva que termina en teoría pero que causa un desbordamiento del búfer de la pila de llamadas en la práctica se puede solucionar transformando la recursividad en un bucle y almacenando los argumentos de la función en una pila explícita (en lugar del uso implícito de la pila de llamadas). 

            Esto siempre es posible porque la clase de funciones recursivas primitivas es equivalente a la clase de funciones computables LOOP. 


        Variables de pila muy grandes:
            
            La otra causa importante de un desbordamiento de pila resulta de un intento de asignar más memoria en la pila de la que cabe, por ejemplo, creando variables de matriz locales que son demasiado grandes. 

            Por esta razón, algunos autores recomiendan que las matrices de más de unos pocos kilobytes se asignen dinámicamente en lugar de como una variable local.



|| Inyección de Dependencias
    
    Es un patrón de diseño orientado a objetos, en el que se suministran objetos a una clase en lugar de ser la propia clase la que cree dichos objetos. 

    Esos objetos cumplen contratos que necesitan nuestras clases para poder funcionar (de ahí el concepto de dependencia).

    Nuestras clases no crean los objetos que necesitan, sino que se los suministra otra clase 'contenedora' que inyectará la implementación deseada a nuestro contrato.

    En otras palabras, se trata de un patrón de diseño que se encarga de extraer la responsabilidad de la creación de instancias de un componente para delegarla en otro, acuñado por Martin Fowler. 


    Componentes: 

        Un objeto o función recibe otros objetos o funciones que requiere, en lugar de crearlos internamente. 

        La inyección de dependencia tiene como objetivo separar las preocupaciones de construir objetos y usarlos, lo que lleva a programas poco acoplados.

        El patrón garantiza que un objeto o función que quiera utilizar un servicio determinado no tenga que saber cómo construir esos servicios. 

        En cambio, el 'cliente' receptor (objeto o función) recibe sus dependencias mediante un código externo (un 'inyector'), del que no tiene conocimiento.

        La inyección de dependencia hace explícitas las dependencias implícitas.

        Abarca los siguientes problemas: 

            ¿Cómo puede una clase ser independiente de la creación de los objetos de los que depende?
            
            ¿Cómo puede una aplicación y los objetos que utiliza admitir diferentes configuraciones?


        La inyección de dependencia se utiliza a menudo para mantener el código en línea con el principio de inversión de dependencia.

        En lenguajes de tipo estático, el uso de inyección de dependencia significa que un cliente sólo necesita declarar las interfaces de los servicios que utiliza, en lugar de sus implementaciones concretas, lo que facilita cambiar qué servicios se utilizan en tiempo de ejecución sin tener que volver a compilar.

        Los frameworks de aplicaciones a menudo combinan la inyección de dependencia con la inversión de control. 

        Bajo inversión de control, el marco primero construye un objeto (como un controlador) y luego le pasa el flujo de control. 

        Con la inyección de dependencia, el marco también crea instancias de las dependencias declaradas por el objeto de la aplicación (a menudo en los parámetros del método constructor) y pasa las dependencias al objeto.

        La inyección de dependencia implementa la idea de "invertir el control sobre las implementaciones de dependencias", razón por la cual ciertos marcos de Java denominan genéricamente el concepto "inversión de control" (que no debe confundirse con inversión del flujo de control).


        La inyección de dependencia implica cuatro roles:

            servicios, clientes, interfaces e inyectores.


        Servicios y clientes:

            Un servicio es cualquier clase que contiene una funcionalidad útil. 

            A su vez, un cliente es cualquier clase que utiliza servicios. 

            Los servicios que un cliente requiere son las dependencias del cliente.

            Cualquier objeto puede ser un servicio o un cliente; los nombres se relacionan únicamente con el papel que desempeñan los objetos en una inyección. 

            El mismo objeto puede incluso ser al mismo tiempo un cliente (utiliza servicios inyectados) y un servicio (se inyecta en otros objetos). 

            Tras la inyección, el servicio pasa a formar parte del estado del cliente y está disponible para su uso.


        Interfaces:

            Los clientes no deben saber cómo se implementan sus dependencias, sólo sus nombres y API. 

            Un servicio que recupera correos electrónicos, por ejemplo, puede utilizar los protocolos IMAP o POP3 entre bastidores, pero este detalle probablemente sea irrelevante para llamar al código que simplemente desea recuperar un correo electrónico. 

            Al ignorar los detalles de implementación, los clientes no necesitan cambiar cuando lo hacen sus dependencias.


        Inyectores:

            El inyector, a veces también llamado ensamblador, contenedor, proveedor o fábrica, presenta los servicios al cliente.

            La función de los inyectores es construir y conectar gráficos de objetos complejos, donde los objetos pueden ser tanto clientes como servicios. 

            El inyector en sí puede ser muchos objetos que trabajan juntos, pero no debe ser el cliente, ya que esto crearía una dependencia circular.

            Debido a que la inyección de dependencia separa cómo se construyen los objetos de cómo se usan, a menudo disminuye la importancia 'new' que se encuentra en la mayoría de los lenguajes orientados a objetos.

            Debido a que el marco maneja la creación de servicios, el programador tiende a construir solo directamente objetos de valor que representan entidades en el dominio del programa (como un objeto Empleado en una aplicación comercial o un objeto Pedido en una aplicación de compras).


        Analogía:

            A modo de analogía, se puede considerar a los automóviles como servicios que realizan el útil trabajo de transportar personas de un lugar a otro. 

            Los motores de los automóviles pueden requerir gasolina, diésel o electricidad, pero este detalle no es importante para el cliente (un conductor), a quien sólo le importa si puede llevarlos a su destino.

            Los automóviles presentan una interfaz uniforme a través de sus pedales, volantes y otros controles. 

            Como tal, el motor con el que fueron 'inyectados' en la línea de fábrica deja de importar y los conductores pueden cambiar entre cualquier tipo de automóvil según sea necesario.


    Tipos de inyección de dependencias: 

        
        Sin inyección de dependencia
            
            En el ejemplo, la clase 'Cliente' contiene una variable miembro de 'Servicio' inicializada en el constructor. 

            El cliente construye y controla directamente qué servicio utiliza, creando una dependencia codificada.

            
            ```java

            public class Client {
                private Service service;

                Client() {
                    // The dependency is hard-coded.
                    this.service = new ExampleService();
                }
            }

            ```
        

        Constructor: 

            Donde las dependencias se proporcionan a través del constructor de clase de un cliente.

            La forma más común de inyección de dependencia es que una clase solicite sus dependencias a través de su constructor. 

            Esto garantiza que el cliente esté siempre en un estado válido, ya que no se puede crear una instancia sin las dependencias necesarias.

            
            ```java

            public class Client {
                private Service service;

                // The dependency is injected through a constructor.
                Client(Service service) {
                    if (service == null) {
                        throw new IllegalArgumentException("service must not be null");
                    }
                    this.service = service;
                }
            }

            ```


        Setter: 

            Donde el cliente expone un método de setter que acepta la dependencia.

            Al aceptar dependencias a través de un método de establecimiento, en lugar de un constructor, los clientes pueden permitir que los inyectores manipulen sus dependencias en cualquier momento. 

            Esto ofrece flexibilidad, pero dificulta garantizar que todas las dependencias se inserten y sean válidas antes de utilizar el cliente.


            ```java

            public class Client {
                private Service service;

                // The dependency is injected through a setter method.
                public void setService(Service service) {
                    if (service == null) {
                        throw new IllegalArgumentException("service must not be null");
                    }
                    this.service = service;
                }
            }

            ```


        Interfaz: 

            Donde la interfaz de la dependencia proporciona un método de inyección que inyectará la dependencia en cualquier cliente que se le pase.

            En algunos marcos, los clientes no necesitan aceptar activamente la inyección de dependencia en absoluto. 

            En Java, por ejemplo, la reflexión puede hacer públicos los atributos privados al probar e inyectar servicios directamente.


            Con la inyección de interfaz, las dependencias ignoran por completo a sus clientes, pero aun así envían y reciben referencias a nuevos clientes.

            De esta forma, las dependencias se convierten en inyectores.

            La clave es que el método de inyección se proporciona a través de una interfaz.

            Aún se necesita un ensamblador para presentar el cliente y sus dependencias. 

            El ensamblador toma una referencia al cliente, la envía a la interfaz de configuración que establece esa dependencia y la pasa a ese objeto de dependencia que a su vez pasa una referencia a sí mismo al cliente.

            Para que la inyección de interfaz tenga valor, la dependencia debe hacer algo además de simplemente devolver una referencia a sí misma.

            Esto podría actuar como una fábrica o un subensamblador para resolver otras dependencias, abstrayendo así algunos detalles del ensamblador principal.

            Podría ser un recuento de referencias para que la dependencia sepa cuántos clientes la están utilizando. 

            Si la dependencia mantiene una colección de clientes, luego podría inyectarles a todos una instancia diferente de sí misma


            ```java

            public interface ServiceSetter {
                void setService(Service service);
            }

            public class Client implements ServiceSetter {
                private Service service;

                @Override
                public void setService(Service service) {
                    if (service == null) {
                        throw new IllegalArgumentException("service must not be null");
                    }
                    this.service = service;
                }
            }

            public class ServiceInjector {
                private final Set<ServiceSetter> clients = new HashSet<>();

                public void inject(ServiceSetter client) {
                    this.clients.add(client);
                    client.setService(new ExampleService());
                }

                public void switch() {
                    for (Client client : this.clients) {
                        client.setService(new AnotherExampleService());
                    }
                }
            }

            public class ExampleService implements Service {}

            public class AnotherExampleService implements Service {}


            ```


        Ensamblador - Implementación: 

            La forma más sencilla de implementar la inyección de dependencia es organizar manualmente los servicios y clientes, lo que normalmente se hace en la raíz del programa, donde comienza la ejecución.

            ```java

            public class Program {

                public static void main(String[] args) {
                    // Build the service.
                    Service service = new ExampleService();

                    // Inject the service into the client.
                    Client client = new Client(service);

                    // Use the objects.
                    System.out.println(client.greet());
                }   
            }

            ```

            La construcción manual puede ser más compleja e involucrar constructores, fábricas u otros patrones de construcción.


        Frameworks: 

            La inyección manual de dependencias suele ser tediosa y propensa a errores para proyectos más grandes, lo que promueve el uso de marcos que automatizan el proceso. 

            La inyección de dependencia manual se convierte en un marco de inyección de dependencia una vez que el código de construcción ya no es personalizado para la aplicación y es universal. 

            Si bien son útiles, estas herramientas no son necesarias para realizar la inyección de dependencia

            Algunos marcos, como Spring, pueden usar archivos de configuración externos para planificar la composición del programa.


            ``java

            import org.springframework.beans.factory.BeanFactory;
            import org.springframework.context.ApplicationContext;
            import org.springframework.context.support.ClassPathXmlApplicationContext;


            public class Injector {

                public static void main(String[] args) {
                    // Details about which concrete service to use are stored in configuration separate from the program itself.
                    BeanFactory beanfactory = new ClassPathXmlApplicationContext("Beans.xml");
                    Client client = (Client) beanfactory.getBean("client");
                    System.out.println(client.greet());
                }
            }

            ```

            Incluso con un gráfico de objetos potencialmente largo y complejo, la única clase mencionada en el código es el punto de entrada; en este caso, 'Client'.

            'Client' no ha sufrido ningún cambio para funcionar con Spring y sigue siendo un POJO.

            Al evitar que las anotaciones y llamadas específicas de Spring se distribuyan entre muchas clases, el sistema sigue dependiendo ligeramente de Spring.

    

    POJO:

        Un objeto Java antiguo (POJO) es un objeto Java ordinario, que no está sujeto a ninguna restricción especial, acuñado por Martin Fowler, Rebecca Parsons y Josh MacKenzie.

        El término "POJO" inicialmente denotaba un objeto Java que no sigue ninguno de los principales modelos, convenciones o frameworks de objetos de Java; hoy en día, "POJO" también se puede utilizar como acrónimo de objeto JavaScript antiguo, en cuyo caso el término denota un objeto JavaScript de pedigrí similar.

        El término continúa un patrón de acrónimo para acuñar retrónimos para tecnologías que no utilizan características nuevas y sofisticadas: objeto Ruby antiguo (PORO) en Ruby, servicio telefónico antiguo (POTS) en telefonía y documentación antigua (pod) en Perl. 

        El equivalente a POJO en .NET Framework es un objeto CLR antiguo (POCO).

        Para PHP, es un simple objeto PHP antiguo (POPO).

        Lo más probable es que el fenómeno POJO haya ganado una amplia aceptación debido a la necesidad de un término común y de fácil comprensión que contraste con los complicados frameworks de objetos.


        Idealmente hablando, un POJO es un objeto Java que no está sujeto a ninguna restricción distinta de las impuestas por la Especificación del lenguaje Java; es decir, un POJO no debería tener que

        1. Ampliar clases preespecificadas, como en

        ```java

        public class Foo extends javax.servlet.http.HttpServlet { ...

        ```


        2. Implementar interfaces preespecificadas, como en
        
        ```java

        public class Bar implements javax.ejb.EntityBean { ...

        ```

        
        3. Contener anotaciones predeterminadas, como en

        ```java

        @javax.persistence.Entity public class Baz { ...

        ```

               
        Variaciones contextuales
        JavaBeans

            Un JavaBean es un POJO que es serializable, tiene un constructor sin argumentos y permite el acceso a propiedades mediante métodos getter y setter que siguen una convención de nomenclatura simple.

            Gracias a esta convención, se pueden hacer referencias declarativas simples a las propiedades de JavaBeans arbitrarios. 

            El código que utiliza dicha referencia declarativa no tiene que saber nada sobre el tipo de bean, y el bean se puede usar con muchos marcos sin que estos marcos tengan que saber el tipo exacto de bean.

            La especificación JavaBeans, si se implementa completamente, rompe ligeramente el modelo POJO ya que la clase debe implementar la interfaz Serializable para ser un verdadero JavaBean. 

            Muchas clases POJO que todavía se llaman JavaBeans no cumplen con este requisito. 

            Dado que Serializable es una interfaz de marcador (sin método), esto no es una gran carga.

            A continuación se muestra un ejemplo de un componente JavaServer Faces (JSF) que tiene un enlace bidireccional a la propiedad de un POJO.


            ```java

            <h:inputText value="#{MyBean.someProperty}"/>

            ```


            La definición del POJO puede ser la siguiente:

            
            ```java

            public class MyBean {

                private String someProperty;

                public String getSomeProperty() {
                     return someProperty;
                }

                public void setSomeProperty(String someProperty) {
                    this.someProperty = someProperty;
                }
            }

            ```
            
            Debido a las convenciones de nomenclatura de JavaBean, la referencia única "someProperty" se puede traducir automáticamente al método "getSomeProperty()" (o "isSomeProperty()" si la propiedad es de tipo booleano) para obtener un valor, y al método "setSomeProperty( String)" método para establecer un valor.


        Agregar servicios de forma transparente

            A medida que los diseños que utilizan POJO se han vuelto más utilizados, han surgido sistemas que brindan a los POJO la funcionalidad completa utilizada en los frameworks y más opciones sobre qué áreas de funcionalidad son realmente necesarias.

            En este modelo, el programador no crea nada más que un POJO. 

            Este POJO se centra exclusivamente en la lógica empresarial y no depende de frameworks (empresariales). 

            Los Frameworks de programación orientada a aspectos (AOP) añaden de forma transparente cuestiones transversales como persistencia, transacciones, seguridad, etc.

            Spring fue una implementación temprana de esta idea y una de las fuerzas impulsoras detrás de la popularización de este modelo.

            Un ejemplo de un bean EJB como POJO:

                JavaBeans empresariales (EJB),
                
                API de persistencia de Java (JPA) (incluido Hibernate)
                
                CDI (Contextos e Inyección de Dependencias para la plataforma Java EE)

            A continuación se muestra un bean EJB completamente funcional, que demuestra cómo EJB3 aprovecha el modelo POJO.


            ```java

            public class HelloWorldService {

                public String sayHello() {
                    return "Hello, world!";
                }
            }

            ```

            Como se indicó, el bean no necesita extender ninguna clase EJB ni implementar ninguna interfaz EJB y tampoco necesita contener ninguna anotación EJB. 

            En cambio, el programador declara en un archivo XML externo qué servicios EJB deben agregarse al bean:


            ```java

            <enterprise-beans>
                <session>
                    <ejb-name>helloWorld</ejb-name>
                    <ejb-class>com.example.HelloWorldService</ejb-class>
                    <session-type>stateless</session-type>
                </session>
            </enterprise-beans>

            ```

            En la práctica, algunas personas encuentran que las anotaciones son elegantes, mientras que XML les parece detallado, feo y difícil de mantener, mientras que otros consideran que las anotaciones contaminan el modelo POJO.


            Por lo tanto, como alternativa a XML, muchos marcos (por ejemplo, Spring, EJB y JPA) permiten el uso de anotaciones en lugar de XML o además de él. 

            A continuación se muestra el mismo bean EJB que se muestra arriba pero con una anotación agregada.

            En este caso, el archivo XML ya no es necesario:


            ```java

            @Stateless
            public class HelloWorldService {

                public String sayHello() {
                    return "Hello, world!";
                }
            }

            ```

            Con la anotación dada anteriormente, el bean ya no es un POJO verdaderamente puro, pero dado que las anotaciones son meramente metadatos pasivos, esto tiene muchos menos inconvenientes dañinos en comparación con la invasividad de tener que extender clases y/o implementar interfaces.

            En consecuencia, el modelo de programación sigue siendo muy parecido al modelo POJO puro.


    POJI: 

        Una interfaz Java simple (POJI) es una forma básica de interfaz Java y aceptable en puntos donde no se permiten interfaces Java más complejas.


    Historia: 

        En los comienzos de la programación, los programas eran lineales y monolíticos.

        El flujo de ejecución era simple y predecible, ejecutándose línea tras línea.

        Aparecieron dos conceptos para estructurar el código: la modularidad y la reutilización de los componentes: se crean bibliotecas de componentes reutilizables. 

        El flujo se complica, saltando de componente a componente, y aparece un nuevo problema: la dependencia (acoplamiento) entre los componentes.

        Las dependencias en el software son necesarias. 

        La problemática con estas viene dada por el grado de acoplamiento que tiene la dependencia con el componente. 

        Lo ideal es tratar de favorecer un grado de acoplamiento bajo, pero sin sacrificar la cohesión.

        El problema se empieza a considerar lo suficientemente importante como para definir nuevos conceptos en el diseño como la Inversión de Control (IoC) implementada a través de Inyección de Dependencias o de eventos.     


    Implementación en Java:

        El contenedor

            La forma habitual de implementar este patrón es mediante un "Contenedor DI", también llamado "Contenedor IoC" y objetos planos o simples por ejemplo los llamados POJO en Java. 

            El contenedor inyecta a cada objeto los objetos necesarios según las relaciones de dependencia registradas en la configuración previa.

            Típicamente este contenedor es implementado por un framework externo a la aplicación (como Spring entre otros), por lo cual en la aplicación también se utilizará inversión de control al ser el contenedor (almacenado en una biblioteca) quien invoque el código de la aplicación.

        
        Declaración de la inyección

            La inyección de dependencias puede realizarse referenciando a las clases de dichas dependencias. 

            Sin embargo, esa no es una buena práctica dado que sus componentes tienen una fuerte relación entre sí, que al final nos supondrá un inconveniente para el mantenimiento del software. 

            Por eso, en la inyección de dependencias, normalmente, se usan interfaces. 

            De esta forma conseguimos abstraer la relación entre una clase A que depende de una clase B sin importar la implementación de cada uno de los dos. 

            De esta forma, conseguimos desacoplamiento.


        Formas de inyectar las dependencias

            En java, y en general en los distintos lenguajes hay distintas formas de inyectar dependencias.

            Esto se puede lograr de forma manual o mediante frameworks como Spring, para lograr esta versatilidad, la inyección de dependencias se apoya en la programación orientada a interfaces.


            Constructor:

                Si una clase A tiene la dependencia de un objeto con la interfaz B.

                ```java

                public class A {
                 private B dependency;
                 public A(B instancedepency)
                 {
                  this.dependency=instancedepency;
                 }
                 //... En su implementación A usa el objeto dependency
                }

                ```


            Metodo Setter:

                ```java

                public class A {
                 private B dependency;
                 public setDependecy(B instancedepency)
                 {
                  this.dependency=instancedepency;
                 }
                 //... En su implementación A usa el objeto dependency
                }

                ```


            Variable de instacia:

                Propiedad, campo, atributo , caracteristicas de una clase.

                ```java

                public class A {
                 public B dependency;
                 //... En su implementación A usa el objeto dependency
                }

                ```
        
        Implementación sin inyección de dependencia: 

            ```java

            public class Vehiculo {

                private Motor motor = new Motor();
                
                /** @return retorna la velocidad del vehículo*/
                public Double enAceleracionDePedal(int presionDePedal) {
                    motor.setPresionDePedal(presionDePedal);
                    int torque = motor.getTorque();
                    Double velocidad = ... //realiza el cálculo
                    return velocidad;
                }

            }

            //se omite la clase Motor ya que no es relevante para este ejemplo

            ```                

            Necesita crear una instancia de 'Motor' para calcular su velocidad.


        Inyección de dependencias usando un método setter:

            ```java

            public class Vehiculo {

                private Motor motor = null;
                
                public void setMotor(Motor motor){
                    this.motor = motor;
                }

                /** @retorna la velocidad del vehículo*/
                public Double enAceleracionDePedal(int presionDePedal) {
                    Double velocidad = null;
                    if (null != motor){
                        motor.setPresionDePedal(presionDePedal);
                        int torque = motor.getTorque();
                        velocidad = ... //realiza el cálculo
                    }   
                    return velocidad; 
                }
            }

            //se omite la clase Motor ya que no es relevante para este ejemplo

            public class VehiculoFactory {

                public Vehiculo construyeVehiculo() {
                    Vehiculo vehiculo = new Vehiculo();
                    Motor motor = new Motor();
                    vehiculo.setMotor(motor);
                    return vehiculo;
                }

            }

            ```

            'VehiculoFactory'
            representa al proveedor.

            Es una aplicación sencilla del patrón de diseño factory que hace posible que la clase 'Vehículo' no requiera saber cómo obtener un motor por sí misma, sino que es la responsabilidad de 'VehiculoFactory'.



|| Serialización 

    Es el proceso de traducir una estructura de datos o el estado de un objeto a un formato que pueda almacenarse (por ejemplo, archivos en dispositivos de almacenamiento secundarios, buffers de datos en dispositivos de almacenamiento primarios) o transmitirse (por ejemplo, flujos de datos a través de redes informáticas) y reconstruido posteriormente (posiblemente en un entorno informático diferente).

    Cuando la serie de bits resultante se vuelve a leer de acuerdo con el formato de serialización, se puede usar para crear un clon semánticamente idéntico del objeto original.

    Para muchos objetos complejos, como aquellos que hacen un uso extensivo de referencias, este proceso no es sencillo. 

    La serialización de objetos orientados a objetos no incluye ninguno de sus métodos asociados con los que estaban vinculados previamente.

    Este proceso de serializar un objeto también se denomina ordenar un objeto en algunas situaciones.

    La operación opuesta, extraer una estructura de datos de una serie de bytes, es la deserialización (también llamada deserialización o desclasificación).


    Usos:

        Los ejemplos de aplicaciones de serialización incluyen métodos como:

            Serializar datos para transferirlos a través de cables y redes (mensajería).
             
            Almacenar datos (en bases de datos, en unidades de disco duro).

            Llamadas a procedimientos remotos, por ejemplo, como en SOAP.

            Distribuir objetos, especialmente en ingeniería de software basada en componentes como COM, CORBA, etc.

            Detectar cambios en datos que varían en el tiempo.


        Para que algunas de estas características sean útiles, se debe mantener la independencia de la arquitectura. 

        Por ejemplo, para un uso máximo de la distribución, una computadora que se ejecute en una arquitectura de hardware diferente debería poder reconstruir de manera confiable un flujo de datos serializados, independientemente del endianismo. 

        Esto significa que el procedimiento más simple y rápido de copiar directamente el diseño de la memoria de la estructura de datos no puede funcionar de manera confiable para todas las arquitecturas.

        Serializar la estructura de datos en un formato independiente de la arquitectura significa evitar problemas de ordenamiento de bytes, diseño de memoria o simplemente diferentes formas de representar estructuras de datos en diferentes lenguajes de programación.

        Es inherente a cualquier esquema de serialización que, debido a que la codificación de los datos es, por definición, serial, extraer una parte de la estructura de datos serializados requiere que todo el objeto se lea de principio a fin y se reconstruya. 

        En muchas aplicaciones, esta linealidad es una ventaja, porque permite utilizar interfaces de E/S simples y comunes para mantener y transmitir el estado de un objeto. 

        En aplicaciones donde un mayor rendimiento es un problema, puede tener sentido dedicar más esfuerzo a lidiar con una organización de almacenamiento no lineal más compleja.

        Incluso en una sola máquina, los objetos punteros primitivos son demasiado frágiles para guardarlos porque los objetos a los que apuntan pueden recargarse en una ubicación diferente en la memoria. 

        Para solucionar esto, el proceso de serialización incluye un paso llamado desactivación del puntero, donde las referencias directas del puntero se convierten en referencias basadas en el nombre o la posición. 

        El proceso de deserialización incluye un paso inverso llamado cambio de puntero.

        Dado que tanto la serialización como la deserialización pueden realizarse desde código común (por ejemplo, la función Serializar en Microsoft Foundation Classes), es posible que el código común haga ambas cosas al mismo tiempo y, por lo tanto: 

            1) detecte diferencias entre los objetos que se están ejecutando. serializados y sus copias anteriores.

            2) proporcionar información para la siguiente detección. 

        No es necesario construir la copia anterior porque las diferencias se pueden detectar sobre la marcha, una técnica llamada ejecución diferencial. 

        Esto es útil en la programación de interfaces de usuario cuyos contenidos varían en el tiempo: se pueden crear, eliminar, alterar o hacer que los objetos gráficos manejen eventos de entrada sin tener que escribir necesariamente un código separado para hacer esas cosas.


    Desventajas

        La serialización rompe la opacidad de un tipo de datos abstracto al exponer potencialmente detalles de implementación privados. 

        Las implementaciones triviales que serializan todos los miembros de datos pueden violar la encapsulación.

        Para disuadir a los competidores de fabricar productos compatibles, los editores de software propietario suelen mantener en secreto comercial los detalles de los formatos de serialización de sus programas. 

        Algunos ofuscan deliberadamente o incluso cifran los datos serializados. 

        Sin embargo, la interoperabilidad requiere que las aplicaciones puedan comprender los formatos de serialización de cada una.

        Por lo tanto, las arquitecturas de llamada a métodos remotos como CORBA definen sus formatos de serialización en detalle.

        Muchas instituciones, como archivos y bibliotecas, intentan preparar sus archivos de respaldo para el futuro (en particular, volcados de bases de datos) almacenándolos en algún formato serializado relativamente legible por humanos.


    Formatos de serialización
        
        La tecnología Xerox Network Systems Courier de principios de la década de 1980 influyó en el primer estándar ampliamente adoptado. 

        Sun Microsystems publicó la Representación de datos externos (XDR) en 1987.

        XDR es un formato abierto y estandarizado como STD 67 (RFC 4506).

        A finales de la década de 1990, comenzó una iniciativa para proporcionar una alternativa a los protocolos de serialización estándar: se utilizó XML, un subconjunto SGML, para producir una codificación basada en texto legible por humanos. 
        
        Esta codificación puede resultar útil para objetos persistentes que pueden ser leídos y comprendidos por humanos o comunicados a otros sistemas independientemente del lenguaje de programación.

        Tiene la desventaja de perder la codificación más compacta basada en flujo de bytes, pero en este punto las mayores capacidades de almacenamiento y transmisión hicieron que el tamaño del archivo fuera una preocupación menor que en los primeros días de la informática. 

        En la década de 2000, XML se utilizaba a menudo para la transferencia asincrónica de datos estructurados entre el cliente y el servidor en aplicaciones web Ajax. 

        XML es un formato abierto y estandarizado como recomendación del W3C.

        JSON es una alternativa ligera de texto plano a XML y también se utiliza habitualmente para la comunicación cliente-servidor en aplicaciones web. 

        JSON se basa en la sintaxis de JavaScript, pero es independiente de JavaScript y es compatible con muchos otros lenguajes de programación. 

        JSON es un formato abierto, estandarizado como STD 90 (RFC 8259), ECMA-404 e ISO/IEC 21778:2017.

        YAML es un superconjunto estricto de JSON e incluye características adicionales como etiquetas de tipo de datos, soporte para estructuras de datos cíclicas, sintaxis sensible a sangrías y múltiples formas de citación de datos escalares. 

        YAML es un formato abierto.

        Las listas de propiedades se utilizan para la serialización mediante los marcos NeXTSTEP, GNUstep, macOS e iOS. 

        La lista de propiedades, o lista p para abreviar, no se refiere a un único formato de serialización, sino a varias variantes diferentes, algunas legibles por humanos y una binaria.

        Para conjuntos de datos científicos de gran volumen, como datos satelitales y resultados de modelos numéricos climáticos, meteorológicos o oceánicos, se han desarrollado estándares de serialización binaria específicos, ej. HDF, netCDF y el antiguo GRIB.


    Soporte de lenguaje de programación

        Varios lenguajes de programación orientados a objetos admiten directamente la serialización de objetos (o el archivo de objetos), ya sea mediante elementos synctatic sugar (facil de hacer) o proporcionando una interfaz estándar para hacerlo. 

        Los lenguajes que lo hacen incluyen Ruby, Smalltalk, Python, PHP, Objective-C, Delphi, Java y la familia de lenguajes .NET. 

        También hay bibliotecas disponibles que agregan soporte de serialización a lenguajes que carecen de soporte nativo.


        C y C++

            C y C++ no proporcionan serialización como ningún tipo de construcción de alto nivel, pero ambos lenguajes admiten la escritura de cualquiera de los tipos de datos integrados, así como estructuras de datos antiguas, como datos binarios. 

            Como tal, suele ser trivial escribir funciones de serialización personalizadas.

            Además, las soluciones basadas en compiladores, como el sistema ODB ORM para C++ y el kit de herramientas gSOAP para C y C++, son capaces de producir automáticamente código de serialización con pocas o ninguna modificación en las declaraciones de clases. 

            Otros marcos de serialización populares son Boost.Serialization de Boost Framework, el marco S11n, y Cereal. 

            El marco MFC (Microsoft) también proporciona una metodología de serialización como parte de su arquitectura Document-View.


        Java

            Java proporciona serialización automática que requiere que el objeto se marque implementando la interfaz java.io.Serializable. 

            La implementación de la interfaz marca la clase como "aceptable para serializar" y luego Java maneja la serialización internamente. 

            No hay métodos de serialización definidos en la interfaz Serializable, pero una clase serializable puede definir opcionalmente métodos con ciertos nombres y firmas especiales que, si se definen, se llamarán como parte del proceso de serialización/deserialización. 

            El lenguaje también permite al desarrollador anular el proceso de serialización de manera más exhaustiva mediante la implementación de otra interfaz, la interfaz externalizable, que incluye dos métodos especiales que se utilizan para guardar y restaurar el estado del objeto.

            Hay tres razones principales por las que los objetos no son serializables de forma predeterminada y deben implementar la interfaz Serializable para acceder al mecanismo de serialización de Java.

            En primer lugar, no todos los objetos capturan semántica útil en un estado serializado. 

            Por ejemplo, un objeto Thread está vinculado al estado de la JVM actual.

            No existe ningún contexto en el que un objeto Thread deserializado mantenga una semántica útil.

            En segundo lugar, el estado serializado de un objeto forma parte del contrato de compatibilidad de su clase. 

            Mantener la compatibilidad entre versiones de clases serializables requiere esfuerzo y consideración adicionales. 

            Por lo tanto, hacer que una clase sea serializable debe ser una decisión de diseño deliberada y no una condición predeterminada.
            
            Por último, la serialización permite el acceso a miembros privados no transitorios de una clase a los que de otro modo no se podría acceder. 

            Las clases que contienen información confidencial (por ejemplo, una contraseña) no deben ser serializables ni externalizables.

            El método de codificación estándar utiliza una traducción recursiva basada en gráficos del descriptor de clase del objeto y los campos serializables en un flujo de bytes. 

            Los primitivos, así como los objetos referenciados no transitorios y no estáticos, se codifican en la secuencia. 

            Cada objeto al que hace referencia el objeto serializado a través de un campo que no está marcado como transitorio también debe serializarse; y si algún objeto en el gráfico completo de referencias de objetos no transitorios no es serializable, entonces la serialización fallará.

            El desarrollador puede influir en este comportamiento marcando objetos como transitorios o redefiniendo la serialización de un objeto para que una parte del gráfico de referencia se trunque y no se serialice.

            Java no utiliza constructor para serializar objetos. 

            Es posible serializar objetos Java a través de JDBC y almacenarlos en una base de datos.

            Si bien los componentes Swing implementan la interfaz serializable, no se garantiza que sean portátiles entre diferentes versiones de la máquina virtual Java.

            Como tal, un componente Swing, o cualquier componente que lo herede, puede serializarse en un flujo de bytes, pero no se garantiza que se pueda reconstituir en otra máquina.


        javascript:
            
            Desde ECMAScript 5.1, JavaScript ha incluido el objeto JSON incorporado y sus métodos JSON.parse() y JSON.stringify().

            Aunque JSON se basa originalmente en un subconjunto de JavaScript, existen casos límite en los que JSON no es JavaScript válido.

            Específicamente, JSON permite que los terminadores de línea Unicode U+2028 LINE SEPARATOR y U+2029 PARAGRAPH SEPARATOR aparezcan sin escape en cadenas entrecomilladas, mientras que ECMAScript 2018 y versiones anteriores no lo hacen.




|| Inversión de dependencias

    El principio de inversión de dependencia es una metodología específica para módulos de software débilmente acoplados. 

    Al seguir este principio, las relaciones de dependencia convencionales establecidas desde módulos de alto nivel que establecen políticas hasta módulos de dependencia de bajo nivel se invierten, lo que hace que los módulos de alto nivel sean independientes de los detalles de implementación del módulo de bajo nivel. 


    El principio establece:

        A. Los módulos de alto nivel no deben importar nada de los módulos de bajo nivel. 

        Ambos deberían depender de abstracciones (por ejemplo, interfaces).


        B. Las abstracciones no deberían depender de los detalles. 

        Los detalles (implementaciones concretas) deberían depender de abstracciones.


    Al dictar que tanto los objetos de alto como los de bajo nivel deben depender de la misma abstracción, este principio de diseño invierte la forma en que algunas personas pueden pensar sobre la programación orientada a objetos.

    La idea detrás de los puntos A y B de este principio es que al diseñar la interacción entre un módulo de alto nivel y uno de bajo nivel, la interacción debe considerarse como una interacción abstracta entre ellos. 

    Esto no sólo tiene implicaciones en el diseño del módulo de alto nivel, sino también en el de bajo nivel: el de bajo nivel debe diseñarse teniendo en cuenta la interacción y puede ser necesario cambiar su interfaz de uso.

    En muchos casos, pensar en la interacción en sí misma como un concepto abstracto permite reducir el acoplamiento de los componentes sin introducir patrones de codificación adicionales, permitiendo sólo un esquema de interacción más ligero y menos dependiente de la implementación.

    Cuando los esquemas de interacción abstractos descubiertos entre dos módulos son genéricos y la generalización tiene sentido, este principio de diseño también conduce al siguiente patrón de codificación de inversión de dependencia.
    

    Patrón de capas tradicionales:

        En la arquitectura de aplicaciones convencional, los componentes de nivel inferior (por ejemplo, la capa de utilidad) están diseñados para ser consumidos por componentes de nivel superior (por ejemplo, la capa de política) que permiten construir sistemas cada vez más complejos. 

        En esta composición, los componentes de nivel superior dependen directamente de los componentes de nivel inferior para lograr alguna tarea.

        Esta dependencia de los componentes de nivel inferior limita las oportunidades de reutilización de los componentes de nivel superior.


        Capa de política -> Capa de mecanismo -> Capa de utilidad


        El objetivo del patrón de inversión de dependencia es evitar esta distribución altamente acoplada con la mediación de una capa abstracta y aumentar la reutilización de capas superiores/de políticas.


    Patrón de inversión de dependencia:

        Con la adición de una capa abstracta, tanto las capas de nivel alto como las de nivel inferior reducen las dependencias tradicionales de arriba a abajo. 

        Sin embargo, el concepto de "inversión" no significa que las capas de nivel inferior dependan directamente de las capas de nivel superior.

        Ambas capas deberían depender de abstracciones (interfaces) que expongan el comportamiento que necesitan las capas de nivel superior.


        Capa de política -> -Interfaz- Servicio de política, Interfaz <- Capa de mecanismo -> -Interfaz- Mecanismo, Interfaz de servicio <- Capa de utilidad


        En una aplicación directa de la inversión de dependencia, las abstracciones pertenecen a las capas superiores/de políticas. 

        Esta arquitectura agrupa los componentes superiores/de política y las abstracciones que definen los servicios inferiores en el mismo paquete. 

        Las capas de nivel inferior se crean mediante herencia/implementación de estas clases o interfaces abstractas.

        La inversión de las dependencias y la propiedad fomenta la reutilización de las capas superiores/de políticas. 

        Las capas superiores podrían utilizar otras implementaciones de los servicios inferiores. 

        Cuando los componentes de la capa de nivel inferior están cerrados o cuando la aplicación requiere la reutilización de servicios existentes, es común que un Adaptador media entre los servicios y las abstracciones.


    Generalización del patrón de inversión de dependencia

        En muchos proyectos, el principio y patrón de inversión de dependencia se consideran como un concepto único que debe generalizarse, es decir, aplicarse a todas las interfaces entre módulos de software. 

        Hay al menos dos razones para ello:

            1. Es más sencillo ver un buen principio de pensamiento como un patrón de codificación.

            Una vez codificada una clase abstracta o una interfaz, el programador puede decir: "He hecho el trabajo de la abstracción".


            2. Debido a que muchas herramientas de pruebas unitarias dependen de la herencia para lograr la burla, el uso de interfaces genéricas entre clases (no solo entre módulos cuando tiene sentido usar la generalidad) se convirtió en la regla.


        Si la herramienta de burla utilizada se basa únicamente en la herencia, puede resultar necesario aplicar ampliamente el patrón de inversión de dependencia.

        Esto tiene grandes inconvenientes:

            1. Simplemente implementar una interfaz sobre una clase no es suficiente para reducir el acoplamiento; Sólo pensar en la posible abstracción de las interacciones puede conducir a un diseño menos acoplado.


            2. La implementación de interfaces genéricas en todas partes de un proyecto hace que sea más difícil de entender y mantener. 

            En cada paso el lector se preguntará cuáles son las otras implementaciones de esta interfaz y la respuesta generalmente es: sólo simulacros.


            3. La generalización de la interfaz requiere más código de plomería, en particular fábricas que generalmente dependen de un marco de inyección de dependencia.


            4. La generalización de la interfaz también restringe el uso del lenguaje de programación.



        Restricciones de generalización

            La presencia de interfaces para lograr el Patrón de Inversión de Dependencia (DIP) tiene otras implicaciones de diseño en un programa orientado a objetos:


                Todas las variables miembro de una clase deben ser interfaces o abstracciones.


                Todos los paquetes de clases concretas deben conectarse únicamente a través de una interfaz o paquetes de clases abstractas.


                Ninguna clase debería derivar de una clase concreta.

                Ningún método debe anular un método implementado.

                Toda creación de instancias de variables requiere la implementación de un patrón de creación, como el método de fábrica o el patrón de fábrica, o el uso de un marco de inyección de dependencia.


        Restricciones de burla de interfaz

            El uso de herramientas de burla/mocking-object basadas en herencia también introduce restricciones:

                
                Los miembros estáticos visibles externamente deberían depender sistemáticamente de la inyección de dependencia, lo que los hace mucho más difíciles de implementar.


                Todos los métodos comprobables deben convertirse en una implementación de interfaz o una anulación de una definición abstracta.


        Direcciones futuras

            Los principios son formas de pensar. 

            Los patrones son formas comunes de resolver problemas. 

            Es posible que existan patrones de codificación para sustituir las características faltantes del lenguaje de programación.

                
                Los lenguajes de programación seguirán evolucionando para permitirles imponer contratos de uso más sólidos y precisos en al menos dos direcciones: 

                hacer cumplir las condiciones de uso (condiciones previas, posteriores e invariantes) e interfaces basadas en estados. 

                Esto probablemente alentará y potencialmente simplificará una aplicación más sólida del patrón de inversión de dependencia en muchas situaciones.


                Cada vez más herramientas burlonas/mocking-object utilizan la inyección de dependencia para resolver el problema de reemplazar miembros estáticos y no virtuales. 

                Los lenguajes de programación probablemente evolucionarán para generar códigos de bytes compatibles con burlas/mocking-object. 

                Una dirección será restringir el uso de miembros no virtuales. 

                El otro será generar, al menos en situaciones de prueba, código de bytes que permita burlas/mocking-object no basadas en herencia.


    Implementaciones

        Dos implementaciones comunes de DIP utilizan una arquitectura lógica similar pero con implicaciones diferentes.

        Una implementación directa empaqueta las clases de políticas con clases de resúmenes de servicios en una biblioteca. 

        En esta implementación, los componentes de alto nivel y los componentes de bajo nivel se distribuyen en paquetes/bibliotecas separados, donde las interfaces que definen el comportamiento/servicios requeridos por el componente de alto nivel son propiedad de la biblioteca del componente de alto nivel y existen dentro de ella. 

        La implementación de la interfaz del componente de alto nivel por parte del componente de bajo nivel requiere que el paquete del componente de bajo nivel dependa del componente de alto nivel para la compilación, invirtiendo así la relación de dependencia convencional.


        figura 1:

        Paquete A.

        Objeto A -> Referencias ->

        Paquete B.

        Objeto B


        figura 2:

        Paquete A.

        Objeto A

        Referencias ->

        Interfaz A <-


        Paquete B.

        Objeto B

        <- Hereda


        Las Figuras 1 y 2 ilustran código con la misma funcionalidad; sin embargo, en la Figura 2, se utilizó una interfaz para invertir la dependencia. 

        Se puede elegir la dirección de la dependencia para maximizar la reutilización del código de políticas y eliminar las dependencias cíclicas.

        En esta versión de DIP, la dependencia del componente de la capa inferior de las interfaces/resúmenes en las capas de nivel superior dificulta la reutilización de los componentes de la capa inferior. 

        En cambio, esta implementación ″invierte″ la dependencia tradicional de arriba hacia abajo hacia lo opuesto, de abajo hacia arriba.


        Una solución más flexible extrae los componentes abstractos en un conjunto independiente de paquetes/bibliotecas

        Capa de política -> -Interfaz- Servicio de política, Interfaz <- Capa de mecanismo -> -Interfaz- Mecanismo, Interfaz de servicio <- Capa de utilidad

        La separación de cada capa en su propio paquete fomenta la reutilización de cualquier capa, aportando robustez y movilidad.


    Ejemplos: 

        Cliente de servidor de archivos remoto:

            Un cliente de servidor de archivos remoto (FTP, almacenamiento en la nube...) se puede modelar como un conjunto de interfaces abstractas:

            
                Conexión/Desconexión (puede ser necesaria una capa de persistencia de conexión)

                Interfaz de creación de carpetas/etiquetas/cambiar nombre/eliminar/lista

                Interfaz de creación/reemplazo/cambio de nombre/eliminación/lectura de archivos

                búsqueda de archivos

                Reemplazo simultáneo o resolución de eliminación

                Gestión del historial de archivos...


            Si los archivos locales y remotos ofrecen las mismas interfaces abstractas, los módulos de alto nivel que implementan el patrón de inversión de dependencia pueden usarlos indiscriminadamente. 

            La aplicación podrá guardar sus documentos de forma local o remota de forma transparente.

            Se debe considerar el nivel de servicio requerido por los módulos de alto nivel.

            Diseñar un módulo como un conjunto de interfaces abstractas y adaptar otros módulos a él puede proporcionar una interfaz común para muchos sistemas.


        Modelo vista controlador: 


            UI (Page: -CustHandler:ICustomerHandler) -> 


            Controllers (ICustomerHandler: GetDemographics(): String) 


            <- App Layer (CustHandler:ICustomerHandler:GetDemographics(): String)


            Los paquetes UI y ApplicationLayer contienen principalmente clases concretas. 

            Los controladores contienen abstracciones/tipos de interfaz. 

            La interfaz de usuario tiene una instancia de 'ICustomerHandler'. 

            Todos los paquetes están físicamente separados. 

            En ApplicationLayer hay una implementación concreta de 'CustomerHandler' que utilizará la clase Page.

            Las instancias de la interfaz 'ICustomerHandler' se crean dinámicamente mediante una fábrica (posiblemente en el mismo paquete de controladores). 

            Los tipos concretos Page y 'CustomerHandler' dependen de 'ICustomerHandler', no entre sí.

            Dado que la interfaz de usuario no hace referencia a ApplicationLayer ni a ningún otro paquete concreto que implemente 'ICustomerHandler', la implementación concreta de 'CustomerHandler' se puede reemplazar sin cambiar la clase de interfaz de usuario.

            Además, la clase Page implementa la interfaz 'IPageViewer' que podría pasarse como argumento a los métodos 'ICustomerHandler', permitiendo la implementación concreta de 'CustomerHandler' para comunicarse con la interfaz de usuario sin una dependencia concreta.

            Nuevamente, ambos están vinculados por interfaces. 


    Patrones relacionados

        La aplicación del principio de inversión de dependencia también puede verse como un ejemplo del patrón de adaptador. 

        Es decir, la clase de alto nivel define su propia interfaz de adaptador, que es la abstracción de la que dependen las otras clases de alto nivel. 

        La implementación adaptada también depende necesariamente de la misma abstracción de la interfaz del adaptador, mientras que se puede implementar utilizando código desde su propio módulo de bajo nivel.

        El módulo de alto nivel no depende del módulo de bajo nivel, ya que solo utiliza la funcionalidad de bajo nivel indirectamente a través de la interfaz del adaptador invocando métodos polimórficos a la interfaz que son implementados por la implementación adaptada y su módulo de bajo nivel.

        Se emplean varios patrones, como complemento, localizador de servicios o inyección de dependencia, para facilitar el aprovisionamiento en tiempo de ejecución de la implementación del componente de bajo nivel elegido al componente de alto nivel.



|| Inversión de Control 
    
    En ingeniería de software, la inversión de control (IoC) es un patrón de diseño en el que partes personalizadas de un programa de computadora reciben el flujo de control (orden de evaluación de los elementos/objetos) de un framework genérico. 

    El término "inversión" es histórico: una arquitectura de software con este diseño "invierte" el control en comparación con la programación procedimental. 

    En la programación de procedimientos, el código personalizado de un programa llama a bibliotecas reutilizables para encargarse de tareas genéricas, pero con la inversión de control, es el marco el que llama al código personalizado.

    La inversión de control ha sido ampliamente utilizada por los marcos de desarrollo de aplicaciones desde el surgimiento de los entornos GUI y continúa utilizándose tanto en entornos GUI como en marcos de aplicaciones de servidor web. 

    La inversión de control hace que el marco sea extensible mediante los métodos definidos por el programador de la aplicación.

    La programación basada en eventos a menudo se implementa utilizando IoC, de modo que el código personalizado solo necesita ocuparse del manejo de eventos, mientras que el marco o el entorno de ejecución maneja el bucle de eventos y el envío de eventos/mensajes. 

    En los marcos de aplicaciones de servidores web, el envío suele denominarse enrutamiento y los controladores pueden denominarse puntos finales.

    La frase "inversión de control" también se ha utilizado por separado en la comunidad de programadores de Java para referirse específicamente a los patrones de inyección de dependencias de objetos que ocurren con "contenedores IoC" en marcos Java como el marco Spring.

    En este sentido diferente, "inversión de control" se refiere a otorgar al framework control sobre las implementaciones de dependencias que utilizan los objetos de la aplicación en lugar del significado original de otorgar el flujo de control del marco (control sobre el tiempo de ejecución del código de la aplicación, por ejemplo. devoluciones de llamada).
  

    Descripción general

        Como ejemplo, con la programación tradicional, la función principal de una aplicación podría realizar llamadas a funciones en una biblioteca de menús para mostrar una lista de comandos disponibles y solicitar al usuario que seleccione uno.

        Por lo tanto, la biblioteca devolvería la opción elegida como valor de la llamada a la función, y la función principal usa este valor para ejecutar el comando asociado.

        Este estilo era común en las interfaces basadas en texto.

        Por ejemplo, un cliente de correo electrónico puede mostrar una pantalla con comandos para cargar correo nuevo, responder el correo actual, crear correo nuevo, etc., y la ejecución del programa se bloquearía hasta que el usuario presione una tecla para seleccionar un comando.

        Por otro lado, con la inversión de control, el programa se escribiría utilizando un marco de software que conoce elementos gráficos y de comportamiento comunes, como sistemas de ventanas, menús, control del mouse, etc.

        El código personalizado "llena los espacios en blanco" del marco, como proporcionar una tabla de elementos de menú y registrar una subrutina de código para cada elemento, pero es el marco el que monitorea las acciones del usuario e invoca la subrutina cuando se selecciona un elemento de menú. 

        En el ejemplo del cliente de correo, el marco podría seguir las entradas del teclado y del mouse y llamar al comando invocado por el usuario por cualquier medio y al mismo tiempo monitorear la interfaz de red para saber si llegan nuevos mensajes y actualizar la pantalla cuando alguna red se detecta actividad. 

        El mismo marco podría usarse como esqueleto para un programa de hoja de cálculo o un editor de texto. 

        Por el contrario, el marco no sabe nada sobre navegadores web, hojas de cálculo o editores de texto; implementar su funcionalidad requiere código personalizado.

        La inversión de control conlleva la fuerte connotación de que el código reutilizable y el código específico del problema se desarrollan de forma independiente aunque operen juntos en una aplicación. 

        Las devoluciones de llamada, los programadores, los bucles de eventos y el método de plantilla son ejemplos de patrones de diseño que siguen el principio de inversión de control, aunque el término se usa más comúnmente en el contexto de la programación orientada a objetos. 

        (La inyección de dependencia es un ejemplo de la idea separada y específica de "invertir el control sobre las implementaciones de dependencias" popularizada por los marcos de Java).

        La inversión de control a veces se conoce como el "Principio de Hollywood: no nos llames, nosotros te llamaremos".


    Origen: 

        La inversión de control no es un término nuevo en informática. 

        Martin Fowler remonta la etimología de la frase a 1988, pero está estrechamente relacionada con el concepto de inversión de programa descrito por Michael Jackson en su metodología de Programación Estructurada Jackson en la década de 1970.

        Un analizador ascendente puede verse como una inversión de un analizador de arriba hacia abajo: en un caso, el control reside en el analizador, mientras que en el otro caso, reside en la aplicación receptora.

        El término fue utilizado por Michael Mattsson en una tesis (con su significado original de un marco que llama al código de la aplicación en lugar de viceversa) y luego fue tomado de allí por Stefano Mazzocchi y popularizado por él en 1999 en un proyecto desaparecido de la Apache Software Foundation, Avalon en el que se refería a un objeto principal que pasaba las dependencias de un objeto secundario además de controlar el flujo de ejecución. 

        La frase fue popularizada aún más en 2004 por Robert C. Martin y Martin Fowler, el último de los cuales remonta los orígenes del término a la década de 1980.


    Descripción

        En la programación tradicional, el flujo de la lógica empresarial está determinado por objetos que están vinculados estáticamente entre sí. 

        Con la inversión de control, el flujo depende del gráfico de objetos que se construye durante la ejecución del programa. 

        Este flujo dinámico es posible gracias a las interacciones entre objetos que se definen mediante abstracciones. 

        Esta vinculación en tiempo de ejecución se logra mediante mecanismos como la inyección de dependencia o un localizador de servicios. 

        En IoC, el código también podría vincularse estáticamente durante la compilación, pero encontrar el código para ejecutar leyendo su descripción desde una configuración externa en lugar de con una referencia directa en el código mismo.

        En la inyección de dependencia, un objeto o módulo dependiente se acopla al objeto que necesita en tiempo de ejecución. 

        Por lo general, no se puede saber qué objeto en particular satisfará la dependencia durante la ejecución del programa en el momento de la compilación mediante el análisis estático. 

        Si bien se describe aquí en términos de interacción de objetos, el principio puede aplicarse a otras metodologías de programación además de la programación orientada a objetos.

        Para que el programa en ejecución vincule objetos entre sí, los objetos deben poseer interfaces compatibles. 

        Por ejemplo, la clase A puede delegar comportamiento a la interfaz I que implementa la clase B; el programa crea una instancia de A y B, y luego inyecta B en A.



||Control Flow: 

    En informática, el flujo de control es el orden en el que se ejecutan o evalúan declaraciones individuales, instrucciones o llamadas a funciones de un programa imperativo. 

    El énfasis en el flujo de control explícito distingue un lenguaje de programación imperativo de un lenguaje de programación declarativo.

    Dentro de un lenguaje de programación imperativo, una declaración de flujo de control es una declaración que da como resultado una elección sobre cuál de dos o más caminos seguir. 

    Para los lenguajes funcionales no estrictos, existen funciones y construcciones de lenguaje para lograr el mismo resultado, pero generalmente no se denominan declaraciones de flujo de control.

    Un conjunto de enunciados se estructura a su vez generalmente como un bloque, que además de agrupar, también define un ámbito léxico.

    Las interrupciones y señales son mecanismos de bajo nivel que pueden alterar el flujo de control de una manera similar a una subrutina, pero generalmente ocurren como respuesta a algún estímulo o evento externo (que puede ocurrir de forma asincrónica), en lugar de la ejecución de una secuencia en línea, declaración de flujo de control.

    A nivel de lenguaje de máquina o lenguaje ensamblador, las instrucciones de flujo de control generalmente funcionan alterando el contador del programa. 

    Para algunas unidades centrales de procesamiento (CPU), las únicas instrucciones de flujo de control disponibles son instrucciones de rama condicionales o incondicionales, también denominadas saltos.



|| Composición 

    En informática, la composición de objetos y la agregación de objetos son formas estrechamente relacionadas de combinar objetos o tipos de datos en otros más complejos. 

    En la conversación a menudo se ignora la distinción entre composición y agregación. 

    Los tipos comunes de composiciones son objetos utilizados en programación orientada a objetos, uniones etiquetadas, conjuntos, secuencias y diversas estructuras gráficas. 

    Las composiciones de objetos se relacionan con las estructuras de datos, pero no son lo mismo.

    La composición del objeto se refiere a la estructura lógica o conceptual de la información, no a la implementación o estructura de datos físicos utilizados para representarla. 

    Por ejemplo, una secuencia se diferencia de un conjunto porque (entre otras cosas) el orden de los elementos compuestos importa para la primera pero no para el segundo. 

    Se pueden utilizar estructuras de datos como matrices, listas vinculadas, tablas hash y muchas otras para implementar cualquiera de ellas. 

    Quizás resulte confuso que algunos de los mismos términos se utilicen tanto para estructuras de datos como para compuestos.

    Por ejemplo, "árbol binario" puede referirse a: como estructura de datos, es un medio para acceder a una secuencia lineal de elementos, y las posiciones reales de los elementos en el árbol son irrelevantes (el árbol se puede reorganizar internamente como uno quiera) sin cambiar su significado. 

    Sin embargo, como composición de un objeto, las posiciones son relevantes y cambiarlas cambiaría el significado (como por ejemplo en los cladogramas).


    Técnica de programación:

        La programación orientada a objetos se basa en objetos para encapsular datos y comportamiento. 

        Utiliza dos técnicas principales para ensamblar y componer funcionalidades en otras más complejas: subtipificación y composición de objetos. 

        La composición de objetos consiste en combinar objetos dentro de objetos compuestos y, al mismo tiempo, garantizar la encapsulación de cada objeto mediante el uso de su interfaz bien definida sin visibilidad de sus partes internas. 

        En este sentido, la composición de objetos difiere de las estructuras de datos, que no imponen la encapsulación.

        La composición de objetos también puede tratarse de un grupo de múltiples objetos relacionados, como un conjunto o una secuencia de objetos. 

        La delegación puede enriquecer la composición reenviando solicitudes o llamadas realizadas al objeto compuesto adjunto a uno de sus componentes internos.

        En los lenguajes de programación basados en clases y tipificados, los tipos se pueden dividir en tipos compuestos y no compuestos, y la composición puede considerarse como una relación entre tipos: un objeto de un tipo compuesto (por ejemplo, un automóvil) "tiene" objetos de otros tipos (por ejemplo, rueda).

        Cuando un objeto compuesto contiene varios subobjetos del mismo tipo, se les puede asignar roles particulares, a menudo distinguidos por nombres o números. 

        Por ejemplo, un objeto Punto puede contener 3 números, cada uno de los cuales representa la distancia a lo largo de un eje diferente, como 'x', 'y' y 'z'. 

        La composición debe distinguirse de la subtipificación, que es el proceso de agregar detalles a un tipo de datos general para crear un tipo de datos más específico. 

        Por ejemplo, los automóviles pueden ser un tipo específico de vehículo: el automóvil es un vehículo. 

        La subtipificación no describe una relación entre diferentes objetos, sino que dice que los objetos de un tipo son simultáneamente objetos de otro tipo.

        El estudio de tales relaciones es la ontología.

        En lenguajes de programación basados en prototipos como JavaScript, los objetos pueden heredar dinámicamente los comportamientos de un objeto prototipo en el momento de su instanciación.

        La composición debe distinguirse de la creación de prototipos: el objeto recién instanciado hereda la composición de su prototipo, pero él mismo puede componerse por sí solo.

        Los objetos compuestos se pueden representar en el almacenamiento coubicando los objetos compuestos, coubicando referencias o de muchas otras maneras. 

        Los elementos dentro de un objeto compuesto pueden denominarse atributos, campos, miembros, propiedades u otros nombres, y la composición resultante como tipo compuesto, registro de almacenamiento, estructura, tupla o un tipo definido por el usuario (UDT). 


    UML: 

        En el modelado UML, los objetos se pueden componer conceptualmente, independientemente de la implementación con un lenguaje de programación. 

        Hay cuatro formas de componer objetos en UML: propiedad, asociación, agregación y composición:

            
            Una propiedad representa un atributo de la clase.

            
            Una asociación representa una relación semántica entre instancias de las clases asociadas. El extremo miembro de una asociación corresponde a una propiedad de la clase asociada.

            
            Una agregación es un tipo de asociación que modela una relación parte/todo entre un agregado (todo) y un grupo de componentes relacionados (partes).

            
            Una composición, también llamada agregación compuesta, es un tipo de agregación que modela una relación parte/todo entre un compuesto (todo) y un grupo de partes de propiedad exclusiva.


        La relación entre el agregado y sus componentes es una relación débil "tiene-a": los componentes pueden ser parte de varios agregados, se puede acceder a ellos a través de otros objetos sin pasar por el agregado y pueden sobrevivir al objeto agregado. 

        El estado del objeto componente todavía forma parte del objeto agregado.


        La relación entre el compuesto y sus partes es una fuerte relación "tiene-un": el objeto compuesto tiene la exclusiva "responsabilidad de la existencia y almacenamiento de los objetos compuestos", el objeto compuesto puede ser parte de como máximo un compuesto, y " Si se elimina un objeto compuesto, todas sus instancias parciales que son objetos se eliminan con él". 

        Por tanto, en UML, composición tiene un significado más limitado que la composición de objetos habitual.


        La notación gráfica representa:

            la propiedad como un elemento escrito en el cuadro de la clase adjunta

            la asociación como una línea simple entre las clases asociadas

            la agregación como un diamante sin relleno en el lado del agregado y una línea continua

            la composición como un diamante relleno en el lado del compuesto y una línea continua


    Patrón compuesto

        En ingeniería de software, el patrón compuesto es un patrón de diseño de partición. 

        El patrón compuesto describe un grupo de objetos que se tratan de la misma manera que una única instancia del mismo tipo de objeto. 

        La intención de un compuesto es "componer" objetos en estructuras de árbol para representar jerarquías de parte y todo. 

        La implementación del patrón compuesto permite a los clientes tratar objetos y composiciones individuales de manera uniforme.


        Descripción general

            El patrón de diseño compuesto es uno de los veintitrés patrones de diseño GoF bien conocidos que describen cómo resolver problemas de diseño recurrentes para diseñar software orientado a objetos flexible y reutilizable, es decir, objetos que son más fáciles de implementar, cambiar, probar y reutilizar.


        ¿Qué problemas puede resolver el patrón de diseño compuesto?

            Se debe representar una jerarquía parte-todo para que los clientes puedan tratar los objetos parciales y totales de manera uniforme.

            Una jerarquía parte-todo debe representarse como una estructura de árbol.


        Al definir (1) objetos de parte y (2) objetos de todo que actúan como contenedores para los objetos de parte, los clientes deben tratarlos por separado, lo que complica el código del cliente.


        ¿Qué solución describe el patrón de diseño compuesto?

            Defina una interfaz de componente unificada tanto para objetos parciales (hoja) como para objetos completos (compuestos).

            Los objetos Hoja individuales implementan la interfaz Componente directamente y los objetos Compuestos reenvían solicitudes a sus componentes secundarios.


        Esto permite a los clientes trabajar a través de la interfaz de Componente para tratar los objetos Hoja y Compuestos de manera uniforme: los objetos Hoja realizan una solicitud directamente y los objetos Compuestos reenvían la solicitud a sus componentes secundarios de forma recursiva hacia abajo en la estructura del árbol. 

        Esto hace que las clases de cliente sean más fáciles de implementar, cambiar, probar y reutilizar.


    Composición sobre herencia:

        La composición sobre la herencia (o principio de reutilización compuesta) en la programación orientada a objetos (POO) es el principio de que las clases deben favorecer el comportamiento polimórfico y la reutilización del código mediante su composición (al contener instancias de otras clases que implementan la funcionalidad deseada) sobre la herencia de una base. o clase de padres. 

        Idealmente, toda la reutilización se puede lograr ensamblando componentes existentes, pero en la práctica a menudo se necesita herencia para crear otros nuevos. 

        Por lo tanto, la herencia y la composición de objetos suelen ir de la mano, como se analiza en el libro Design Patterns (1994).


        Lo esencial:

            Una implementación de composición sobre herencia generalmente comienza con la creación de varias interfaces que representan los comportamientos que debe exhibir el sistema. 

            Las interfaces pueden facilitar el comportamiento polimórfico. 

            Las clases que implementan las interfaces identificadas se crean y agregan a las clases de dominio empresarial según sea necesario. 

            Por tanto, los comportamientos del sistema se realizan sin herencia.

            De hecho, todas las clases de dominio empresarial pueden ser clases base sin herencia alguna. 

            La implementación alternativa de los comportamientos del sistema se logra proporcionando otra clase que implemente la interfaz de comportamiento deseada.

            Una clase que contiene una referencia a una interfaz puede admitir implementaciones de la interfaz, una elección que puede retrasarse hasta el tiempo de ejecución.



|| Fabrica
    
    En programación orientada a objetos, una fábrica es un objeto para crear otros objetos; Formalmente, es una función o método que devuelve objetos de un prototipo o clase variable a partir de alguna llamada a un método, que se supone que es "nuevo". 

    En términos más generales, una subrutina que devuelve un objeto "nuevo" puede denominarse "fábrica", como en el método de fábrica o en la función de fábrica. 

    El patrón de fábrica es la base de varios patrones de diseño de software relacionados.


    Motivación:

        En la programación basada en clases, una fábrica es una abstracción de un constructor de una clase, mientras que en la programación basada en prototipos una fábrica es una abstracción de un objeto prototipo. 

        Un constructor es concreto en el sentido de que crea objetos como instancias de una sola clase y mediante un proceso específico (creación de instancias de clase), mientras que una fábrica puede crear objetos creando instancias de varias clases o utilizando otros esquemas de asignación, como un grupo de objetos. 

        Un objeto prototipo es concreto en el sentido de que se utiliza para crear objetos mediante clonación, mientras que una fábrica puede crear objetos mediante la clonación de varios prototipos o mediante otros esquemas de asignación.

        Una fábrica se puede implementar de varias maneras. 

        La mayoría de las veces se implementa como un método, en cuyo caso se denomina método de fábrica. 

        A veces se implementa como una función, en cuyo caso se denomina función de fábrica.

        En algunos lenguajes, los constructores son en sí mismos fábricas. 

        Sin embargo, en la mayoría de los lenguajes no lo son, y los constructores se invocan de una manera que es idiomática para el lenguaje, como usando la palabra clave new, mientras que una fábrica no tiene un estado especial y se invoca a través de una llamada a un método normal o una llamada a una función. 

        En estos lenguajes, una fábrica es una abstracción de un constructor, pero no estrictamente una generalización, ya que los constructores no son fábricas en sí mismos.


    Terminología:

        La terminología difiere en cuanto a si el concepto de fábrica es en sí mismo un patrón de diseño: en los patrones de diseño no existe un "patrón de fábrica", sino dos patrones (patrón de método de fábrica y patrón de fábrica abstracto) que utilizan fábricas. 

        Algunas fuentes se refieren al concepto como patrón de fábrica, mientras que otras consideran el concepto en sí mismo un modismo de programación, reservando el término "patrón de fábrica" o "patrones de fábrica" a patrones más complicados que utilizan fábricas, con mayor frecuencia el patrón de método de fábrica; En este contexto, el concepto de fábrica en sí puede denominarse fábrica simple.

        En otros contextos, particularmente en el lenguaje Python, se utiliza la propia "fábrica".

        En términos más generales, "fábrica" se puede aplicar no sólo a un objeto que devuelve objetos de alguna llamada a un método, sino a una subrutina que devuelve objetos, como en una función de fábrica (incluso si las funciones no son objetos) o un método de fábrica. 

        Debido a que en muchos lenguajes las fábricas se invocan llamando a un método, el concepto general de fábrica a menudo se confunde con el patrón de diseño de patrón de método de fábrica específico.


    Uso:

        La programación orientada a objetos proporciona polimorfismo en el uso de objetos mediante el envío de métodos, formalmente polimorfismo de subtipo mediante envío único determinado por el tipo de objeto en el que se llama el método. 

        Sin embargo, esto no funciona para los constructores, ya que los constructores crean un objeto de algún tipo, en lugar de utilizar un objeto existente.

        Más concretamente, cuando se llama a un constructor, todavía no hay ningún objeto sobre el que enviar.

        El uso de fábricas en lugar de constructores o prototipos permite utilizar el polimorfismo para la creación de objetos, no solo para su uso. 

        Específicamente, el uso de fábricas proporciona encapsulación y significa que el código no está vinculado a clases u objetos específicos y, por lo tanto, la jerarquía de clases o los prototipos se pueden cambiar o refactorizar sin necesidad de cambiar el código que los usa: se abstraen de la jerarquía de clases o los prototipos.

        Más técnicamente, en lenguajes donde las fábricas generalizan los constructores, las fábricas generalmente se pueden usar en cualquier lugar donde puedan estar los constructores, lo que significa que las interfaces que aceptan un constructor también pueden aceptar una fábrica; por lo general, solo se necesita algo que cree un objeto, en lugar de necesitar especificar una clase y una instanciación.


    Creación de objetos:

        Los objetos de fábrica se utilizan en situaciones en las que conseguir un objeto de un tipo particular es un proceso más complejo que simplemente crear un nuevo objeto, especialmente si se desea una asignación o inicialización compleja.

        Algunos de los procesos necesarios en la creación de un objeto incluyen determinar qué objeto crear, gestionar la vida útil del objeto y gestionar los problemas especializados de montaje y desmontaje del objeto. 

        El objeto de fábrica podría decidir crear la clase del objeto (si corresponde) dinámicamente, devolverlo desde un grupo de objetos, realizar una configuración compleja en el objeto u otras cosas. 

        De manera similar, usando esta definición, un singleton implementado por el patrón singleton es una fábrica formal: devuelve un objeto, pero no crea nuevos objetos más allá de la instancia única.


        Ejemplo: 

            El ejemplo más simple de una fábrica es una función de fábrica simple, que simplemente invoca un constructor y devuelve el resultado. 

            Función de fábrica f que crea una instancia de una clase:

            ```python

            def f():
                return A()
        
            ```


            Una función de fábrica simple que implementa el patrón singleton:

            def f():
                if f.obj is None:
                    f.obj = A()
                return f.obj

            f.obj = None

            ```

            Esto creará un objeto cuando se llame por primera vez y siempre devolverá el mismo objeto a partir de entonces.


    Sintaxis:

        Las fábricas se pueden invocar de varias maneras, más a menudo mediante una llamada a un método (un método de fábrica), a veces llamándolas como una función si la fábrica es un objeto invocable (una función de fábrica).

        En algunos lenguajes, los constructores y las fábricas tienen una sintaxis idéntica, mientras que en otros los constructores tienen una sintaxis especial. 

        En lenguajes donde los constructores y las fábricas tienen una sintaxis idéntica, como Python, Perl, Ruby, Object Pascal y F#, los constructores pueden ser reemplazados de forma transparente por fábricas. 

        En los lenguajes en los que difieren, hay que distinguirlos en las interfaces, y cambiar entre constructores y fábricas requiere cambiar las llamadas.


    Semántica:

        En lenguajes donde los objetos se asignan dinámicamente, como en Java o Python, las fábricas son semánticamente equivalentes a los constructores. 

        Sin embargo, en lenguajes como C++ que permiten que algunos objetos se asignen estáticamente, las fábricas son diferentes de los constructores para clases asignadas estáticamente, ya que a estos últimos se les puede determinar la asignación de memoria en el momento de la compilación, mientras que la asignación de los valores de retorno de las fábricas debe determinarse en tiempo de ejecución. 

        Si se puede pasar un constructor como argumento a una función, entonces la invocación del constructor y la asignación del valor de retorno deben realizarse dinámicamente en tiempo de ejecución y, por lo tanto, tener una semántica similar o idéntica a la invocación de una fábrica.


    Patrones de diseño:

        Las fábricas se utilizan en varios patrones de diseño, específicamente en patrones de creación como la biblioteca de objetos de patrones de diseño. 

        Se han desarrollado recetas específicas para implementarlas en muchos idiomas. 

        Por ejemplo, varios "patrones GoF", como el "patrón de método Factory", el "Builder" o incluso el "Singleton" son implementaciones de este concepto. 

        En cambio, el "patrón de fábrica abstracto" es un método para construir colecciones de fábricas.

        En algunos patrones de diseño, un objeto de fábrica tiene un método para cada tipo de objeto que es capaz de crear. 

        Estos métodos aceptan opcionalmente parámetros que definen cómo se crea el objeto y luego devuelven el objeto creado.


    Aplicaciones

        Los objetos de fábrica son comunes en kits de herramientas y marcos donde el código de la biblioteca necesita crear objetos de tipos que las aplicaciones que utilizan el framework pueden subclasificar. 

        También se utilizan en el desarrollo basado en pruebas para permitir que las clases se pongan a prueba.

        Las fábricas determinan el tipo concreto de objeto que se va a crear, y es aquí donde se crea realmente el objeto.

        Como la fábrica solo devuelve una interfaz abstracta al objeto, el código del cliente no conoce (y no está sobrecargado por) el tipo concreto real del objeto que acaba de crear. 

        Sin embargo, la fábrica abstracta conoce el tipo de objeto concreto. 

        En particular, esto significa:

            El código del cliente no tiene conocimiento alguno del tipo concreto y no necesita incluir archivos de encabezado ni declaraciones de clase relacionadas con el tipo concreto. El código del cliente trata sólo con el tipo abstracto. De hecho, la fábrica crea objetos de un tipo concreto, pero el código del cliente accede a dichos objetos sólo a través de su interfaz abstracta.


            La adición de nuevos tipos concretos se realiza modificando el código del cliente para utilizar una fábrica diferente, una modificación que suele ser una línea en un archivo. Esto es significativamente más fácil que modificar el código del cliente para crear una instancia de un nuevo tipo, lo que requeriría cambiar cada ubicación en el código donde se crea un nuevo objeto.


    Aplicabilidad:

        Las fábricas se pueden utilizar cuando:

            La creación de un objeto hace imposible su reutilización sin una duplicación significativa de código.

            La creación de un objeto requiere acceso a información o recursos que no deberían estar contenidos dentro de la clase que lo compone.

            La gestión de la vida útil de los objetos generados debe centralizarse para garantizar un comportamiento coherente dentro de la aplicación.


        Las fábricas, específicamente los métodos de fábrica, son comunes en los kits de herramientas y los marcos, donde el código de la biblioteca necesita crear objetos de tipos que las aplicaciones que utilizan el marco pueden subclasificar.

        Las jerarquías de clases paralelas a menudo requieren que los objetos de una jerarquía puedan crear objetos apropiados a partir de otra.

        Los métodos de fábrica se utilizan en el desarrollo basado en pruebas para permitir que las clases se pongan a prueba.

        Si dicha clase Foo crea otro objeto Dangerous que no se puede someter a pruebas unitarias automatizadas (tal vez se comunica con una base de datos de producción que no siempre está disponible), entonces la creación de objetos Dangerous se coloca en el método de fábrica virtual createDangerous en clase Foo. 

        Para las pruebas, luego se crea TestFoo (una subclase de Foo), con el método de fábrica virtual createDangerous anulado para crear y devolver FakeDangerous, un objeto falso. 

        Las pruebas unitarias luego usan TestFoo para probar la funcionalidad de Foo sin incurrir en el efecto secundario de usar un objeto peligroso real.


    Patrón de método de fábrica:

        En la programación orientada a objetos, el patrón de método de fábrica es un patrón de creación que utiliza métodos de fábrica para abordar el problema de crear objetos sin tener que especificar la clase exacta del objeto que se creará.

        Esto se hace creando objetos llamando a un método de fábrica, ya sea especificado en una interfaz e implementado por clases secundarias, o implementado en una clase base y opcionalmente anulado por clases derivadas, en lugar de llamar a un constructor.


    Descripción general:

        El patrón de diseño Factory Method es uno de los veintitrés patrones de diseño conocidos que describen cómo resolver problemas de diseño recurrentes para diseñar software orientado a objetos flexible y reutilizable, es decir, objetos que son más fáciles de implementar, cambiar, probar y reutilizar.

        El patrón de diseño Factory Method resuelve problemas como:

            ¿Cómo se puede crear un objeto para que las subclases puedan redefinir su implementación posterior y distinta?

            ¿Cómo se puede aplazar la creación de instancias de un objeto a una subclase?


        El patrón de diseño Factory Method describe cómo resolver dichos problemas:

            Defina un método de fábrica dentro de la superclase que difiera la creación del objeto al método de fábrica de una subclase.

            Cree un objeto llamando a un método de fábrica en lugar de llamar directamente a un constructor.


        Esto permite la escritura de subclases que pueden cambiar la forma en que se crea un objeto (por ejemplo, redefiniendo qué clase crear una instancia).



|| Singleton:
    
    En matemáticas, un singleton, también conocido como conjunto unitario o conjunto de un punto, es un conjunto con exactamente un elemento.

    Por ejemplo, el conjunto { 0 } es un singleton cuyo único elemento es 0.

    En ingeniería de software, el patrón singleton es un patrón de diseño de software que restringe la creación de instancias de una clase a una instancia singular.

    Uno de los conocidos patrones de diseño "Gang of Four", que describe cómo resolver problemas recurrentes en software orientado a objetos, el patrón es útil cuando se necesita exactamente un objeto para coordinar acciones en todo un sistema.

    Más específicamente, el patrón singleton permite que los objetos:

        Asegúrese de que solo tengan una instancia

        Proporcionar fácil acceso a esa instancia

        Controlar su creación de instancias (por ejemplo, ocultar los constructores de una clase)

    El término proviene del concepto matemático de singleton.


    Usos comunes:

        Los singletons a menudo se prefieren a las variables globales porque no contaminan el espacio de nombres global (o el espacio de nombres que los contiene). 

        Además, permiten una asignación e inicialización diferidas, mientras que las variables globales en muchos idiomas siempre consumirán recursos.

        El patrón singleton también se puede utilizar como base para otros patrones de diseño, como los patrones de fábrica abstracta, método de fábrica, constructor y prototipo. 

        Los objetos de fachada también suelen ser únicos porque solo se requiere un objeto de fachada (facade).

        El registro (Logging/Log:file) es un caso de uso común en el mundo real para singletons, porque todos los objetos que desean registrar mensajes requieren un punto de acceso uniforme y escribir conceptualmente en una única fuente.


    Implementaciones

        Las implementaciones del patrón singleton garantizan que solo exista una instancia de la clase singleton y, por lo general, brindan acceso global a esa instancia.

        Normalmente, esto se logra mediante:

            Declarar que todos los constructores de la clase son privados, lo que evita que otros objetos creen instancias de ella.

            Proporcionar un método estático que devuelva una referencia a la instancia.

        
        La instancia normalmente se almacena como una variable estática privada; la instancia se crea cuando se inicializa la variable, en algún momento antes de que se llame por primera vez al método estático.


    Inicialización diferida:

        Una implementación singleton puede utilizar una inicialización diferida en la que la instancia se crea cuando se invoca por primera vez el método estático. 

        En programas multiproceso, esto puede provocar condiciones de carrera que den como resultado la creación de múltiples instancias.



|| Builder

    Descripción general

        El patrón de diseño Builder es uno de los patrones de diseño que describen cómo resolver problemas de diseño recurrentes en software orientado a objetos.

        El patrón de diseño Builder resuelve problemas como:

            ¿Cómo puede una clase (el mismo proceso de construcción) crear diferentes representaciones de un objeto complejo?

            ¿Cómo se puede simplificar una clase que incluye la creación de un objeto complejo?


        Crear y ensamblar las partes de un objeto complejo directamente dentro de una clase es inflexible.

        Compromete a la clase a crear una representación particular del objeto complejo y hace imposible cambiar la representación posteriormente independientemente de (sin tener que cambiar) la clase.

        El patrón de diseño Builder describe cómo resolver dichos problemas:

            Encapsule la creación y el ensamblaje de las partes de un objeto complejo en un objeto Builder separado.

            Una clase delega la creación de objetos a un objeto Builder en lugar de crear los objetos directamente.


        Una clase (el mismo proceso de construcción) puede delegar en diferentes objetos Builder para crear diferentes representaciones de un objeto complejo.


    Definición:

        La intención del patrón de diseño Builder es separar la construcción de un objeto complejo de su representación. 

        Al hacerlo, un mismo proceso de construcción puede crear diferentes representaciones.


    Ventajas:

        Las ventajas del patrón Builder incluyen:

            Le permite variar la representación interna de un producto.

            Encapsula código para construcción y representación.

            Proporciona control sobre los pasos del proceso constructivo.


    Desventajas

        Las desventajas del patrón Builder incluyen:

            Se debe crear un ConcreteBuilder distinto para cada tipo de producto.

            Las clases de constructor deben ser mutables.

            Puede obstaculizar/complicar la inyección de dependencia.



|| Facade 

    El patrón de fachada es un patrón de diseño de software comúnmente utilizado en programación orientada a objetos. 

    De manera análoga a una fachada en arquitectura, una fachada es un objeto que sirve como una interfaz frontal que enmascara un código estructural o subyacente más complejo. 

    Una fachada puede:

        mejorar la legibilidad y usabilidad de una biblioteca de software enmascarando la interacción con componentes más complejos detrás de una única API (y a menudo simplificada)

        Proporcionar una interfaz específica del contexto para una funcionalidad más genérica (completa con validación de entrada específica del contexto).

        Servir como punto de partida para una refactorización más amplia de sistemas monolíticos o estrechamente acoplados en favor de un código más débilmente acoplado.


    Los desarrolladores suelen utilizar el patrón de diseño de fachada cuando un sistema es muy complejo o difícil de entender porque el sistema tiene muchas clases interdependientes o porque su código fuente no está disponible. 

    Este patrón oculta las complejidades del sistema más grande y proporciona una interfaz más simple para el cliente. 

    Por lo general, implica una única clase contenedora que contiene un conjunto de miembros requeridos por el cliente. 

    Estos miembros acceden al sistema en nombre del cliente de fachada y ocultan los detalles de implementación.


    Descripción general:

        El patrón de diseño Fachada es uno de los veintitrés patrones de diseño GoF bien conocidos que describen cómo resolver problemas de diseño recurrentes para diseñar software orientado a objetos flexible y reutilizable, es decir, objetos que son más fáciles de implementar, cambiar, probar y reutilizar.


        ¿Qué problemas puede resolver el patrón de diseño Fachada?

            Para que un subsistema complejo sea más fácil de usar, se debe proporcionar una interfaz simple para un conjunto de interfaces en el subsistema.

            Deben minimizarse las dependencias de un subsistema.


        Los clientes que acceden a un subsistema complejo se refieren directamente a (dependen de) muchos objetos diferentes que tienen diferentes interfaces (acoplamiento estrecho), lo que hace que los clientes sean difíciles de implementar, cambiar, probar y reutilizar.

        ¿Qué solución describe el patrón de diseño Fachada?

            Defina un objeto de fachada que

            implementa una interfaz simple en términos de (delegando a) las interfaces en el subsistema y
            puede realizar funciones adicionales antes/después de reenviar una solicitud.

 
        Esto permite trabajar a través de un objeto Facade para minimizar las dependencias de un subsistema.


    Uso:

    Una fachada se utiliza cuando se desea una interfaz más fácil o sencilla para un objeto subyacente. 

    Alternativamente, se puede utilizar un adaptador cuando el contenedor debe respetar una interfaz particular y debe admitir un comportamiento polimórfico. 

    Un decorador permite agregar o alterar el comportamiento de una interfaz en tiempo de ejecución.


    Adaptador:
        
        Convierte una interfaz en otra para que coincida con lo que el cliente espera.


    Decorador:

        Agrega dinámicamente responsabilidad a la interfaz al empaquetar el código original.


    Fachada

        Proporciona una interfaz simplificada.

    
    El patrón de fachada se usa típicamente cuando

        Se requiere una interfaz simple para acceder a un sistema complejo.

        Un sistema es muy complejo o difícil de entender.

        se necesita un punto de entrada para cada nivel de software en capas, o
        Las abstracciones e implementaciones de un subsistema están estrechamente acopladas.



|| Decorador
    
    En programación orientada a objetos, el patrón decorador es un patrón de diseño que permite agregar comportamiento a un objeto individual, dinámicamente, sin afectar el comportamiento de otras instancias de la misma clase. 

    El patrón decorador suele ser útil para adherirse al principio de responsabilidad única, ya que permite dividir la funcionalidad entre clases con áreas de interés únicas, así como al principio abierto-cerrado, al permitir que la funcionalidad de una clase se extienda sin ser modificado. 

    El uso del decorador puede ser más eficiente que la creación de subclases, porque el comportamiento de un objeto se puede aumentar sin definir un objeto completamente nuevo.


    Descripción general

        El patrón de diseño decorador es uno de los veintitrés patrones de diseño más conocidos; estos describen cómo resolver problemas de diseño recurrentes y diseñar software orientado a objetos flexible y reutilizable, es decir, objetos que son más fáciles de implementar, cambiar, probar y reutilizar.


        ¿Qué problemas puede resolver?

            Las responsabilidades deben agregarse (y eliminarse) de un objeto dinámicamente en tiempo de ejecución.

            Se debe proporcionar una alternativa flexible a la subclasificación para ampliar la funcionalidad.

        
        Cuando se utilizan subclases, diferentes subclases amplían una clase de diferentes maneras. 

        Pero una extensión está vinculada a la clase en tiempo de compilación y no se puede cambiar en tiempo de ejecución.


        ¿Qué solución describe?

            Definir objetos decoradores que implementan la interfaz del objeto extendido (decorado) (Componente) de forma transparente reenviándole todas las solicitudes

            realizar funciones adicionales antes/después de reenviar una solicitud.

        
        Esto permite trabajar con diferentes objetos Decorator para ampliar la funcionalidad de un objeto dinámicamente en tiempo de ejecución.


    Intención:

        El patrón decorador se puede utilizar para ampliar (decorar) la funcionalidad de un determinado objeto de forma estática o, en algunos casos, en tiempo de ejecución, independientemente de otras instancias de la misma clase, siempre que se realicen algunos trabajos preliminares en tiempo de diseño. 

        Esto se logra diseñando una nueva clase Decorador que envuelve la clase original. 

        Esta envoltura podría lograrse mediante la siguiente secuencia de pasos:

            1. Subclasificar la clase Componente original en una clase Decorador.

            2. En la clase Decorador, agregue un puntero de Componente como campo.

            3. En la clase Decorador, pase un Componente al constructor Decorador para inicializar el puntero del Componente.

            4. En la clase Decorador, reenvíe todos los métodos de Componente al puntero de Componente.

            5. En la clase ConcreteDecorator, anule cualquier método de componente cuyo comportamiento deba modificarse.

        Este patrón está diseñado para que se puedan apilar varios decoradores uno encima del otro, agregando cada vez una nueva funcionalidad a los métodos anulados.

        Tenga en cuenta que los decoradores y el objeto de clase original comparten un conjunto común de características. 


        En el diagrama anterior, el método operación() estaba disponible tanto en la versión decorada como sin decorar.

        Las características de decoración (por ejemplo, métodos, propiedades u otros miembros) generalmente se definen mediante una interfaz, mixin (también conocido como rasgo) o herencia de clase que comparten los decoradores y el objeto decorado. 

        En el ejemplo anterior, la clase Component es heredada tanto por ConcreteComponent como por las subclases que descienden de Decorator.

        El patrón decorador es una alternativa a la subclasificación. 

        La creación de subclases agrega comportamiento en el momento de la compilación y el cambio afecta a todas las instancias de la clase original; La decoración puede proporcionar un nuevo comportamiento en tiempo de ejecución para objetos seleccionados.

        Esta diferencia adquiere mayor importancia cuando existen varias formas independientes de ampliar la funcionalidad. 

        En algunos lenguajes de programación orientados a objetos, las clases no se pueden crear en tiempo de ejecución y, por lo general, no es posible predecir, en tiempo de diseño, qué combinaciones de extensiones se necesitarán. 

        Esto significaría que se tendría que crear una nueva clase para cada combinación posible. 

        Por el contrario, los decoradores son objetos creados en tiempo de ejecución y se pueden combinar según su uso. 

        Las implementaciones de I/O Streams tanto de Java como de .NET Framework incorporan el patrón decorador.


    Motivación: 

        Como ejemplo, considere una ventana en un sistema de ventanas. 

        Para permitir el desplazamiento del contenido de la ventana, es posible que desee agregarle barras de desplazamiento horizontales o verticales, según corresponda. 

        Suponga que las ventanas están representadas por instancias de la interfaz Ventana y suponga que esta clase no tiene funcionalidad para agregar barras de desplazamiento. 

        Se podría crear una subclase ScrollingWindow que los proporcione, o crear un ScrollingWindowDecorator que agregue esta funcionalidad a los objetos Window existentes. 

        En este punto, cualquier solución estaría bien.

        Ahora, supongamos que uno también desea poder agregar bordes a las ventanas.

        Nuevamente, la clase Window original no tiene soporte. 

        La subclase ScrollingWindow ahora plantea un problema, porque efectivamente ha creado un nuevo tipo de ventana. 

        Si se desea agregar soporte de bordes a muchas ventanas, pero no a todas, se deben crear subclases WindowWithBorder y ScrollingWindowWithBorder, etc. 

        Este problema empeora con cada nueva característica o subtipo de ventana que se agrega. 

        Para la solución decoradora, se crea un nuevo BorderedWindowDecorator.

        Cualquier combinación de ScrollingWindowDecorator o BorderedWindowDecorator puede decorar ventanas existentes.

        Si es necesario agregar la funcionalidad a todos los Windows, se puede modificar la clase base. 

        Por otro lado, a veces (por ejemplo, usando frameworks externos) no es posible, legal o conveniente modificar la clase base.

        En el ejemplo anterior, las clases SimpleWindow y WindowDecorator implementan la interfaz Window, que define el método draw() y el método getDescription() que se requieren en este escenario para decorar un control de ventana.


    Casos de uso comunes:

        Aplicando decoradores:

            Agregar o eliminar decoradores mediante una orden (como presionar un botón) es un patrón de interfaz de usuario común, que a menudo se implementa junto con el patrón de diseño Command.

            Por ejemplo, una aplicación de edición de texto podría tener un botón para resaltar texto. 

            Al presionar el botón, los glifos de texto individuales actualmente seleccionados estarán todos envueltos en decoradores que modifican su función draw(), lo que hace que se dibujen de manera resaltada (una implementación real probablemente también usaría un sistema de demarcación para maximizar la eficiencia).

            Aplicar o eliminar decoradores en función de cambios de estado es otro caso de uso común. 

            Dependiendo del alcance del estado, los decoradores se pueden aplicar o eliminar en masa. 

            De manera similar, el patrón de diseño State se puede implementar utilizando decoradores en lugar de objetos subclasificados que encapsulan la funcionalidad cambiante.

            El uso de decoradores de esta manera hace que el estado interno y la funcionalidad del objeto State sean más compositivos y capaces de manejar una complejidad arbitraria.


        Uso en objetos Flyweight:

            La decoración también se utiliza a menudo en el patrón de diseño Flyweight. 

            Los objetos Flyweight se dividen en dos componentes: un componente invariante que se comparte entre todos los objetos Flyweight; y una variante, componente decorado que puede ser parcialmente compartido o completamente no compartido. 

            Esta partición del objeto flyweight tiene como objetivo reducir el consumo de memoria. 

            Los decoradores normalmente también se almacenan en caché y se reutilizan. Todos los decoradores contendrán una referencia común al objeto invariante compartido. 

            Si el estado decorado es sólo parcialmente variante, entonces los decoradores también se pueden compartir hasta cierto punto, aunque se debe tener cuidado de no alterar su estado mientras se utilizan. UITableView de iOS implementa el patrón de peso mosca de esta manera: las celdas reutilizables de una vista de tabla son decoradores que contienen referencias a un objeto de fila de vista de tabla común, y las celdas se almacenan en caché/se reutilizan.


        Obstáculos al interactuar con decoradores:

            Aplicar combinaciones de decoradores de diversas maneras a una colección de objetos introduce algunos problemas al interactuar con la colección de una manera que aprovecha al máximo la funcionalidad agregada por los decoradores. 

            El uso de patrones de Adaptador o Visitante puede resultar útil en tales casos. 

            La interacción con múltiples capas de decoradores plantea desafíos adicionales y la lógica de los Adaptadores y Visitantes debe diseñarse para tenerlo en cuenta.


        Relevancia arquitectónica:

            Los decoradores apoyan un enfoque compositivo más que jerárquico de arriba hacia abajo para ampliar la funcionalidad. 

            Un decorador permite agregar o alterar el comportamiento de una interfaz en tiempo de ejecución. 

            Se pueden utilizar para envolver objetos en una combinación arbitraria de múltiples capas. 

            Hacer lo mismo con las subclases significa implementar redes complejas de herencia múltiple, que son ineficientes en memoria y, en cierto punto, simplemente no pueden escalarse. 

            Del mismo modo, intentar implementar la misma funcionalidad con propiedades sobrecarga cada instancia del objeto con propiedades innecesarias. 

            Por las razones anteriores, los decoradores a menudo se consideran una alternativa a las subclases que ahorra memoria.

            Los decoradores también se pueden utilizar para especializar objetos que no se pueden subclasificar, cuyas características deben modificarse en tiempo de ejecución (como se menciona en otra parte) o, en general, objetos que carecen de alguna funcionalidad necesaria.


        Uso para mejorar las API:

            El patrón decorador también puede aumentar el patrón Fachada. 

            Una fachada está diseñada para interactuar simplemente con el complejo sistema que encapsula, pero no agrega funcionalidad al sistema.

            Sin embargo, la envoltura de un sistema complejo proporciona un espacio que puede usarse para introducir nuevas funcionalidades basadas en la coordinación de subcomponentes del sistema. 

            Por ejemplo, un patrón de fachada puede unificar muchos diccionarios de idiomas diferentes bajo una interfaz de diccionario multilingüe.

            La nueva interfaz también puede proporcionar nuevas funciones para traducir palabras entre idiomas. Este es un patrón híbrido: la interfaz unificada proporciona un espacio para el aumento. 

            Piense en los decoradores como no limitados a envolver objetos individuales, sino que también son capaces de envolver grupos de objetos en este enfoque híbrido.



|| Gang of Four (GoF)
    
    Patrones de diseño: elementos de software orientado a objetos reutilizables (1994) es un libro de ingeniería de software que describe patrones de diseño de software. 

    El libro fue escrito por Erich Gamma, Richard Helm, Ralph Johnson y John Vlissides, con un prólogo de Grady Booch. 

    El libro está dividido en dos partes: los dos primeros capítulos exploran las capacidades y los peligros de la programación orientada a objetos, y los capítulos restantes describen 23 patrones clásicos de diseño de software. 

    El libro incluye ejemplos en C++ y Smalltalk.


    Aportes:

        Discusión de técnicas de diseño orientado a objetos, basada en la experiencia de los autores, que creen que conducirían a un buen diseño de software orientado a objetos, que incluye:

            "Programa para una interfaz, no para una implementación". (Banda de los Cuatro 1995:18)
            
            Composición sobre herencia: "Favorezca la 'composición de objetos' sobre la 'herencia de clases'". (Banda de los Cuatro 1995:20)

            Los autores afirman lo siguiente como ventajas de las interfaces sobre la implementación:

                Los clientes desconocen los tipos específicos de objetos que utilizan, siempre y cuando el objeto se adhiera a la interfaz.
                
                los clientes desconocen las clases que implementan estos objetos; los clientes sólo conocen las clases abstractas que definen la interfaz.

            El uso de una interfaz también conduce a enlaces dinámicos y polimorfismo, que son características centrales de la programación orientada a objetos.

            Los autores se refieren a la herencia como reutilización de la caja blanca, y la caja blanca se refiere a la visibilidad, porque las partes internas de las clases principales a menudo son visibles para las subclases. 

            Por el contrario, los autores se refieren a la composición de objetos (en la que objetos con interfaces bien definidas son utilizados dinámicamente en tiempo de ejecución por objetos que obtienen referencias a otros objetos) como reutilización de caja negra porque no es necesario que los detalles internos de los objetos compuestos sean visibles en el código que utiliza a ellos.

            Los autores discuten extensamente la tensión entre herencia y encapsulación y afirman que, según su experiencia, los diseñadores abusan de la herencia (Gang of Four 1995:20). 

            El peligro se expresa de la siguiente manera:

                "Debido a que la herencia expone una subclase a detalles de la implementación de su padre, a menudo se dice que 'la herencia rompe la encapsulación'". (Banda de los Cuatro 1995:19)

            Advierten que la implementación de una subclase puede llegar a estar tan ligada a la implementación de su clase principal que cualquier cambio en la implementación de la clase principal obligará a la subclase a cambiar.

            Además, afirman que una forma de evitar esto es heredar sólo de clases abstractas, pero luego señalan que la reutilización del código es mínima.

            Se recomienda utilizar la herencia principalmente cuando se agrega funcionalidad a componentes existentes, se reutiliza la mayor parte del código antiguo y se agregan cantidades relativamente pequeñas de código nuevo.

            Para los autores, la "delegación" es una forma extrema de composición de objetos que siempre puede utilizarse para reemplazar la herencia.

            La delegación implica dos objetos: un 'remitente' se pasa a un 'delegado' para permitir que el delegado se refiera al remitente. 

            Por lo tanto, el vínculo entre dos partes de un sistema se establece sólo en tiempo de ejecución, no en tiempo de compilación. 

            El artículo de devolución de llamada tiene más información sobre la delegación.

            Los autores también analizan los llamados tipos parametrizados, también conocidos como genéricos (Ada, Eiffel, Java, C#, VB.NET y Delphi) o plantillas (C++). 

            Estos permiten definir cualquier tipo sin especificar todos los demás tipos que utiliza; los tipos no especificados se suministran como 'parámetros' en el punto de uso.

            Los autores admiten que la delegación y la parametrización son muy poderosas pero añaden una advertencia:

                "El software dinámico y altamente parametrizado es más difícil de entender y construir que el software más estático". (Banda de los Cuatro 1995:21)

            Los autores distinguen además entre "Agregación", donde un objeto "tiene" o "es parte de" otro objeto (lo que implica que un objeto agregado y su propietario tienen vidas idénticas) y conocimiento, donde un objeto simplemente "conoce" otro objeto. 

            A veces el conocimiento se denomina "asociación" o relación de "uso". 

            Los objetos conocidos pueden solicitar operaciones entre sí, pero no son responsables entre sí. 

            El conocimiento es una relación más débil que la agregación y sugiere un acoplamiento mucho más flexible entre objetos, lo que a menudo puede ser deseable para una máxima mantenibilidad en los diseños.

            Los autores emplean el término "kit de herramientas" (toolkit) donde otros hoy podrían usar "biblioteca de clases", como en C# o Java. 

            En su lenguaje, los kits de herramientas son el equivalente orientado a objetos de las bibliotecas de subrutinas, mientras que un "Framework" es un conjunto de clases cooperativas que conforman un diseño reutilizable para una clase específica de software. 

            Afirman que las aplicaciones son difíciles de diseñar, los kits de herramientas son más difíciles y los Frameworks son los más difíciles de diseñar.


    Patrones por tipo

        Creacional:

            Los patrones de creación son aquellos que crean objetos, en lugar de tener que crear instancias de objetos directamente. 

            Esto le da al programa más flexibilidad para decidir qué objetos deben crearse para un caso determinado.

                Los grupos de fábricas abstractas se oponen a fábricas que tienen un tema común.

                Builder construye objetos complejos separando construcción y representación.

                El método de fábrica crea objetos sin especificar la clase exacta a crear.

                Prototype crea objetos clonando un objeto existente.

                Singleton restringe la creación de objetos para una clase a una sola instancia.


        Estructural:

            Los patrones estructurales se refieren a la composición de clases y objetos. 

            Utilizan la herencia para componer interfaces y definir formas de componer objetos para obtener nuevas funciones.

                El adaptador permite que clases con interfaces incompatibles trabajen juntas envolviendo su propia interfaz alrededor de la de una clase ya existente.

                Bridge desacopla una abstracción de su implementación para que las dos puedan variar de forma independiente.

                Compuesto compone cero o más objetos similares para que puedan manipularse como un solo objeto.

                Decorador agrega/anula dinámicamente el comportamiento en un método existente de un objeto.

                Facade proporciona una interfaz simplificada para una gran cantidad de código.

                Flyweight reduce el costo de crear y manipular una gran cantidad de objetos similares.

                Proxy proporciona un marcador de posición para otro objeto para controlar el acceso, reducir costos y reducir la complejidad.


        Conductual

            La mayoría de los patrones de diseño de comportamiento se ocupan específicamente de la comunicación entre objetos.

                La cadena de responsabilidad delega comandos a una cadena de objetos de procesamiento.

                El comando crea objetos que encapsulan acciones y parámetros.

                El intérprete implementa un lenguaje especializado.

                Iterator accede a los elementos de un objeto secuencialmente sin exponer su representación subyacente.

                Mediator permite un acoplamiento flexible entre clases al ser la única clase que tiene un conocimiento detallado de sus métodos.

                Memento brinda la capacidad de restaurar un objeto a su estado anterior (deshacer).

                Observer es un patrón de publicación/suscripción que permite que varios objetos observadores vean un evento.

                El estado permite que un objeto altere su comportamiento cuando cambia su estado interno.

                La estrategia permite seleccionar uno de una familia de algoritmos sobre la marcha en tiempo de ejecución.

                El método de plantilla define el esqueleto de un algoritmo como una clase abstracta, permitiendo que sus subclases proporcionen un comportamiento concreto.

                El visitante separa un algoritmo de una estructura de objeto moviendo la jerarquía de métodos a un objeto.



|| SOLID
    
    En ingeniería de software, SOLID es un acrónimo mnemónico de cinco principios de diseño destinados a hacer que los diseños orientados a objetos sean más comprensibles, flexibles y mantenibles. Los principios son un subconjunto de muchos principios promovidos por el ingeniero e instructor de software estadounidense Robert C. Martin, presentados por primera vez en su artículo de 2000 Principios de diseño y patrones de diseño que analiza la descomposición del software.

    Las ideas son:

        El principio de responsabilidad única: 

            "Nunca debe haber más de una razón para que una clase cambie". 

            En otras palabras, cada clase debería tener una sola responsabilidad.


        Principio abierto-cerrado:

            "Las entidades de software... deben estar abiertas a la extensión, pero cerradas a la modificación".


        El principio de sustitución de Liskov: 

            "Las funciones que utilizan punteros o referencias a clases base deben poder utilizar objetos de clases derivadas sin saberlo". 


        Segregación de interfaces: 

            "No se debe obligar a los clientes a depender de interfaces que no utilizan".


        Inversión de dependencia: 

            "Depende de abstracciones, [no] de concretos".


    El acrónimo SOLID fue introducido más tarde, alrededor de 2004, por Michael Feathers.

    Aunque los principios SOLID se aplican a cualquier diseño orientado a objetos, también pueden formar una filosofía central para metodologías como el desarrollo ágil o el desarrollo de software adaptativo.


    1. Single responsibility principle (SRP):

        El principio de responsabilidad única (SRP) es un principio de programación informática que establece que "un módulo debe ser responsable ante un, y sólo un, actor". 

        El término actor se refiere a un grupo (formado por una o más partes interesadas o usuarios) que requiere un cambio en el módulo.

        Robert C. Martin, el creador del término, expresa el principio como: 

            "Una clase debe tener sólo una razón para cambiar". 

            Debido a la confusión en torno a la palabra "razón", más tarde aclaró su significado en una publicación de blog titulada "El principio de responsabilidad única", en la que mencionó la separación de preocupaciones y afirmó que "Otra redacción para el principio de responsabilidad única es: reunir a los cosas que cambian por las mismas razones. 

            Separa aquellas cosas que cambian por diferentes razones”. 

            En algunas de sus charlas también sostiene que el principio se refiere, en particular, a roles o actores. 

            Por ejemplo, si bien pueden ser la misma persona, la función de un contador es diferente a la de un administrador de base de datos. 

            Por lo tanto, cada módulo debe ser responsable de cada rol.


        Ejemplo:

            Martin define una responsabilidad como una razoneszón para cambiar y concluye que una clase o módulo debe tener una, y sólo una, razón para cambiar (por ejemplo, reescribir).

            Como ejemplo, considere un módulo que compila e imprime un informe. 

            Imagine que un módulo de este tipo se puede cambiar por dos razones. 

            En primer lugar, el contenido del informe podría cambiar.

            En segundo lugar, el formato del informe podría cambiar.

            Estas dos cosas cambian por diferentes causas. 

            El principio de responsabilidad única dice que estos dos aspectos del problema son en realidad dos responsabilidades separadas y, por lo tanto, deberían estar en clases o módulos separados. 

            Sería un mal diseño acoplar dos cosas que cambian por diferentes motivos en diferentes momentos.

            La razón por la que es importante mantener una clase centrada en una única preocupación es que la hace más sólida. 

            Siguiendo con el ejemplo anterior, si hay un cambio en el proceso de compilación del informe, existe un mayor peligro de que el código de impresión se rompa si es parte de la misma clase.


    2. Open-Closed: 

        En la programación orientada a objetos, el principio abierto-cerrado (OCP) establece que "las entidades de software (clases, módulos, funciones, etc.) deben estar abiertas a la extensión, pero cerradas a la modificación"; es decir, dicha entidad puede permitir ampliar su comportamiento sin modificar su código fuente.

        El nombre principio abierto-cerrado se ha utilizado de dos maneras.

        Ambas formas utilizan generalizaciones (por ejemplo, herencia o funciones delegadas) para resolver el aparente dilema, pero los objetivos, técnicas y resultados son diferentes.

        El principio abierto-cerrado es uno de los cinco principios SÓLIDOS del diseño orientado a objetos.


        Principio abierto-cerrado de Meyer

            A Bertrand Meyer generalmente se le atribuye haber originado el término principio abierto-cerrado, que apareció en su libro de 1988 Construcción de software orientada a objetos.

                Se dirá que un módulo está abierto si todavía está disponible para su extensión. 

                Por ejemplo, debería ser posible agregar campos a las estructuras de datos que contiene, o nuevos elementos al conjunto de funciones que realiza.

                Se dirá que un módulo está cerrado si está disponible para que lo utilicen otros módulos. 

                Esto supone que al módulo se le ha dado una descripción estable y bien definida (la interfaz en el sentido de ocultar información).

            En el momento en que Meyer estaba escribiendo, agregar campos o funciones a una biblioteca inevitablemente requería cambios en cualquier programa que dependiera de esa biblioteca. 

            La solución propuesta por Meyer a este problema se basó en la noción de herencia orientada a objetos (específicamente herencia de implementación).

            Una clase está cerrada, ya que puede ser compilada, almacenada en una biblioteca, basada en líneas base y utilizada por clases cliente. 

            Pero también es abierto, ya que cualquier clase nueva puede usarlo como padre, agregando nuevas características. 

            Cuando se define una clase descendiente, no hay necesidad de cambiar la original ni molestar a sus clientes.


        Principio polimórfico abierto-cerrado

            Durante la década de 1990, el principio abierto-cerrado se redefinió popularmente para referirse al uso de interfaces abstractas, donde las implementaciones se pueden cambiar y se pueden crear múltiples implementaciones y sustituirlas polimórficamente entre sí.

            En contraste con el uso de Meyer, esta definición aboga por la herencia de clases base abstractas.

            Las especificaciones de interfaz se pueden reutilizar mediante herencia, pero no es necesario que la implementación lo sea. 

            La interfaz existente está cerrada a modificaciones y las nuevas implementaciones deben, como mínimo, implementar esa interfaz.

            El artículo de Robert C. Martin de 1996, "El principio abierto-cerrado", fue uno de los escritos fundamentales en adoptar este enfoque. 

            En 2001, Craig Larman relacionó el principio abierto-cerrado con el patrón de Alistair Cockburn llamado Variaciones protegidas, y con la discusión de David Parnas sobre el ocultamiento de información.


    3. Liskov:

        El principio de sustitución de Liskov (LSP) es una definición particular de una relación de subtipificación, llamada subtipificación conductual fuerte, que fue introducida inicialmente por Barbara Liskov en un discurso de apertura de una conferencia de 1987 titulada Abstracción y jerarquía de datos. 

        Se basa en el concepto de "sustituibilidad", un principio de programación orientada a objetos que establece que un objeto (como una clase) puede ser reemplazado por un subobjeto (como una clase que extiende la primera clase) sin romper el programa. 

        Es una relación semántica más que meramente sintáctica, porque pretende garantizar la interoperabilidad semántica de tipos en una jerarquía, tipos de objetos en particular. 

        Barbara Liskov y Jeannette Wing describieron el principio sucintamente en un artículo de 1994 de la siguiente manera.


        Principio:

            La noción de Liskov de subtipo conductual define una noción de sustituibilidad de objetos; es decir, si S es un subtipo de T, entonces los objetos de tipo T en un programa pueden reemplazarse con objetos de tipo S sin alterar ninguna de las propiedades deseables de ese programa (por ejemplo, corrección).

            La subtipificación conductual es una noción más sólida que la típica subtipificación de funciones definidas en la teoría de tipos, que se basa únicamente en la contravarianza de los tipos de parámetros y la covarianza del tipo de retorno. 

            La subtipificación de comportamiento es indecidible en general: si q es la propiedad "el método para x siempre termina", entonces es imposible para un programa (por ejemplo, un compilador) verificar que sea cierto para algún subtipo S de T, incluso si q sí se cumple para T.

            No obstante, el principio es útil para razonar sobre el diseño de jerarquías de clases.

            El principio de sustitución de Liskov impone algunos requisitos estándar sobre las firmas que se han adoptado en los lenguajes de programación orientados a objetos más nuevos (normalmente a nivel de clases en lugar de tipos; consulte subtipos nominales versus estructurales para conocer la distinción):

                Contravarianza de los tipos de parámetros del método en el subtipo.

                Covarianza de los tipos de retorno del método en el subtipo.

                Los métodos del subtipo no pueden generar nuevas excepciones, excepto si son subtipos de excepciones lanzadas por los métodos del supertipo.


            Además de los requisitos de firma, el subtipo debe cumplir una serie de condiciones de comportamiento. 

            Estos se detallan en una terminología similar a la de la metodología de diseño por contrato, lo que genera algunas restricciones sobre cómo los contratos pueden interactuar con la herencia:

                Las condiciones previas no se pueden reforzar en el subtipo.

                Las poscondiciones no se pueden debilitar en el subtipo.

                La invariante no se puede debilitar en el subtipo.

                Restricción histórica (la "regla histórica"). 


            Se considera que los objetos son modificables sólo a través de sus métodos (encapsulación).

            Debido a que los subtipos pueden introducir métodos que no están presentes en el supertipo, la introducción de estos métodos puede permitir cambios de estado en el subtipo que no están permitidos en el supertipo. 

            La restricción histórica lo prohíbe. 

            Fue el elemento novedoso introducido por Liskov y Wing. 

            Una violación de esta restricción se puede ejemplificar definiendo un punto mutable como un subtipo de un punto inmutable.

            Esto es una violación de la restricción histórica, porque en la historia del punto inmutable, el estado es siempre el mismo después de la creación, por lo que no puede incluir la historia de un punto mutable en general. 

            Sin embargo, los campos agregados al subtipo se pueden modificar de forma segura porque no son observables mediante los métodos de supertipo. Por lo tanto, se puede definir un círculo con centro inmutable y radio mutable como un subtipo de un punto inmutable sin violar la restricción histórica.


    Design by contract (DbC):

        Prescribe que los diseñadores de software deben definir especificaciones de interfaz formales, precisas y verificables para los componentes de software, que amplían la definición ordinaria de tipos de datos abstractos con condiciones previas, condiciones posteriores e invariantes.

        Estas especificaciones se denominan "contratos", de acuerdo con una metáfora conceptual de las condiciones y obligaciones de los contratos comerciales.

        El enfoque DbC supone que todos los componentes del cliente que invocan una operación en un componente del servidor cumplirán las condiciones previas especificadas como requeridas para esa operación.

        Cuando esta suposición se considera demasiado arriesgada (como en la informática multicanal o distribuida), se adopta el enfoque inverso, lo que significa que el componente del servidor prueba que todas las condiciones previas relevantes sean verdaderas (antes o mientras se procesa la solicitud del componente del cliente) y responde, con un mensaje de error adecuado si no.


    4. Interface segregation:

        En el campo de la ingeniería de software, el principio de segregación de interfaces (ISP) establece que ningún código debe verse obligado a depender de métodos que no utiliza. 

        El ISP divide las interfaces que son muy grandes en otras más pequeñas y específicas para que los clientes sólo tengan que conocer los métodos que les interesan. 

        Estas interfaces reducidas también se denominan interfaces de roles.

        El objetivo del ISP es mantener un sistema desacoplado y, por lo tanto, más fácil de refactorizar, cambiar y volver a implementar. 

        ISP es uno de los cinco principios SÓLIDOS del diseño orientado a objetos, similar al Principio de Alta Cohesión de GRASP.

        Más allá del diseño orientado a objetos, ISP también es un principio clave en el diseño de sistemas distribuidos en general y de microservicios en particular. 

        ISP es uno de los seis principios IDEALES para el diseño de microservicios

        Importancia en el diseño orientado a objetos
        Dentro del diseño orientado a objetos, las interfaces proporcionan capas de abstracción que simplifican el código y crean una barrera que impide el acoplamiento a las dependencias. 

        Un sistema puede llegar a estar tan acoplado en múltiples niveles que ya no sea posible realizar un cambio en un lugar sin requerir muchos cambios adicionales. 

        El uso de una interfaz o una clase abstracta puede evitar este efecto secundario.


        Origen:

            El ISP fue utilizado y formulado por primera vez por Robert C. Martin mientras asesoraba a Xerox.

             Xerox había creado un nuevo sistema de impresión que podía realizar una variedad de tareas como grapar y enviar faxes. 

             El software para este sistema fue creado desde cero. 

             A medida que el software crecía, hacer modificaciones se hacía cada vez más difícil, de modo que incluso el cambio más pequeño requería un ciclo de reimplementación de una hora, lo que hacía que el desarrollo fuera casi imposible.

            El problema de diseño era que casi todas las tareas utilizaban una única clase de Trabajo.

            Cada vez que era necesario realizar un trabajo de impresión o un trabajo de grapado, se realizaba una llamada a la clase Trabajo. 

            Esto resultó en una clase "gorda" con multitud de métodos específicos para una variedad de clientes diferentes. 

            Debido a este diseño, un trabajo de grapas conocería todos los métodos del trabajo de impresión, aunque no fueran útiles.

            La solución sugerida por Martin utilizó lo que hoy se llama el Principio de Segregación de Interfaz.

            Aplicado al software Xerox, se agregó una capa de interfaz entre la clase Trabajo y sus clientes utilizando el Principio de Inversión de Dependencia. 

            En lugar de tener una clase de trabajo grande, se creó una interfaz de trabajo de grapado o una interfaz de trabajo de impresión que serían utilizadas por las clases de grapado o de impresión, respectivamente, llamando a los métodos de la clase de trabajo. 

            Por lo tanto, se creó una interfaz para cada tipo de trabajo, que fue implementada por la clase Job.


        Romper principio de Segregación:

            Se da en Desarrollo ágil de software: principios, patrones y prácticas en 'Ejemplo de transacción ATM' y en un artículo también escrito por Robert C. Martin específicamente sobre el ISP.

            Este ejemplo analiza la interfaz de usuario de un cajero automático, que maneja todas las solicitudes, como una solicitud de depósito o una solicitud de retiro, y cómo esta interfaz debe segregarse en interfaces individuales y más específicas.


    6. Dependency Inversion. 

        En el diseño orientado a objetos, el principio de inversión de dependencia es una metodología específica para módulos de software débilmente acoplados. 

        Al seguir este principio, las relaciones de dependencia convencionales establecidas desde módulos de alto nivel que establecen políticas hasta módulos de dependencia de bajo nivel se invierten, lo que hace que los módulos de alto nivel sean independientes de los detalles de implementación del módulo de bajo nivel. 

        El principio establece:

            Los módulos de alto nivel no deben importar nada de los módulos de bajo nivel. Ambos deberían depender de abstracciones (por ejemplo, interfaces).

            Las abstracciones no deberían depender de los detalles. Los detalles (implementaciones concretas) deberían depender de abstracciones.


        Al dictar que tanto los objetos de alto como los de bajo nivel deben depender de la misma abstracción, este principio de diseño invierte la forma en que algunas personas pueden pensar sobre la programación orientada a objetos.

        La idea detrás de los puntos A y B de este principio es que al diseñar la interacción entre un módulo de alto nivel y uno de bajo nivel, la interacción debe considerarse como una interacción abstracta entre ellos. 

        Esto no sólo tiene implicaciones en el diseño del módulo de alto nivel, sino también en el de bajo nivel: el de bajo nivel debe diseñarse teniendo en cuenta la interacción y puede ser necesario cambiar su interfaz de uso.




|| Agile
    
    En el desarrollo de software, las prácticas ágiles (a veces escritas "Agile") incluyen requisitos, descubrimiento y mejora de soluciones a través del esfuerzo colaborativo de equipos autoorganizados y multifuncionales con sus clientes/usuarios finales. 

    Popularizados en el Manifiesto para el desarrollo de software ágil de 2001, estos valores y principios se derivaron de, y sustentan, una amplia gama de marcos de desarrollo de software, incluidos Scrum y Kanban.

    Si bien hay mucha evidencia anecdótica de que la adopción de prácticas y valores ágiles mejora la efectividad de los profesionales, equipos y organizaciones del software, la evidencia empírica es mixta y difícil de encontrar.


    Manifiesto: 

        Valores del desarrollo de software ágil

        Basándose en su experiencia combinada en el desarrollo de software y en ayudar a otros a hacerlo, los autores del manifiesto declararon que valoraban:

            Individuos e interacciones sobre procesos y herramientas
             
            Software funcional sobre documentación completa
            
            Colaboración del cliente sobre la negociación del contrato.
             
            Responde al cambio sobre el siguiente plan

        
        Es decir, si bien ambos lados tienen valor y los elementos de la derecha deben considerarse, los autores consideraron que los elementos de la izquierda deberían tener más influencia en cómo las personas abordan su trabajo.

        Como explicó Scott Ambler:

            Las herramientas y los procesos son importantes, pero es más importante contar con personas competentes que trabajen juntas de manera efectiva.
            
            Una buena documentación es útil para ayudar a las personas a comprender cómo se construye el software y cómo usarlo, pero el objetivo principal del desarrollo es crear software, no documentación.
            
            Un contrato es importante, pero no sustituye el trabajo en estrecha colaboración con los clientes para descubrir lo que necesitan.
             
            Un plan de proyecto es importante, pero no debe ser demasiado rígido para dar cabida a los cambios en la tecnología o el medio ambiente, las prioridades de las partes interesadas y la comprensión de la gente sobre el problema y su solución.


    Desarrollo de software:

        El Manifiesto para el Desarrollo Ágil de Software se basa en doce principios:

            1. Satisfacción del cliente mediante la entrega temprana y continua de software valioso.

            2. Bienvenidos los requisitos cambiantes, incluso en las últimas etapas del desarrollo.

            3. Entregar software que funcione con frecuencia (semanas en lugar de meses).

            4. Cooperación estrecha y diaria entre empresarios y desarrolladores.

            5. Los proyectos se construyen en torno a personas motivadas en las que se debe confiar.

            6. La conversación cara a cara es la mejor forma de comunicación (coubicación).

            7. El software funcional es la principal medida del progreso.
             
            8. Desarrollo sostenible, capaz de mantener un ritmo constante.

            9. Atención continua a la excelencia técnica y al buen diseño.

            10. La simplicidad (el arte de maximizar la cantidad de trabajo no realizado) es esencial.

            11. Las mejores arquitecturas, requisitos y diseños surgen de equipos autoorganizados.

            12. Periódicamente, el equipo reflexiona sobre cómo ser más eficaz y se adapta en consecuencia.



|| Adaptative
    
    El desarrollo de software adaptativo reemplaza el ciclo en cascada tradicional (waterfall) con una serie repetida de ciclos de especulación, colaboración y aprendizaje. 

    Este ciclo dinámico proporciona un aprendizaje continuo y una adaptación al estado emergente del proyecto. 

    Las características del ciclo de vida de un ASD son que está centrado en la misión, basado en características, iterativo, con límites de tiempo, impulsado por riesgos y tolerante al cambio. 

    Al igual que RAD, ASD también es un antecedente del desarrollo ágil de software.

    La palabra especular se refiere a la paradoja de la planificación: es más probable asumir que todas las partes interesadas están comparativamente equivocadas en ciertos aspectos de la misión del proyecto, al intentar definirla.

    Durante la especulación, se inicia el proyecto y se lleva a cabo la planificación del ciclo adaptativo. 

    La planificación del ciclo adaptativo utiliza información de inicio del proyecto (la declaración de la misión del cliente, las limitaciones del proyecto (por ejemplo, fechas de entrega o descripciones de usuario) y requisitos básicos) para definir el conjunto de ciclos de lanzamiento (incrementos de software) que serán necesarios para el proyecto.

    La colaboración se refiere a los esfuerzos por equilibrar el trabajo basado en partes predecibles del entorno (planificarlas y guiarlas) y adaptarse a la mezcla incierta de cambios causados por diversos factores, como la tecnología, los requisitos, las partes interesadas y los proveedores de software. 

    Los ciclos de aprendizaje, que desafían a todas las partes interesadas, se basan en iteraciones breves de diseño, construcción y pruebas. 

    Durante estas iteraciones, el conocimiento se obtiene cometiendo pequeños errores basados en suposiciones falsas y corrigiéndolos, lo que conduce a una mayor experiencia y, finalmente, a un dominio en el dominio del problema.






|| Objetos
    
    Puede ser una variable, una estructura de datos, una función o un método. 

    Como regiones de la memoria, los objetos contienen un valor y están referenciados por identificadores.

    En el paradigma de programación orientada a objetos, un objeto puede ser una combinación de variables, funciones y estructuras de datos; en particular, en las variaciones del paradigma basadas en clases, un objeto se refiere a una instancia particular de una clase.

    En el modelo relacional de gestión de bases de datos, un objeto puede ser una tabla o columna, o una asociación entre datos y una entidad de base de datos (como relacionar la edad de una persona con una persona específica).


    Lenguajes basados en objetos

        Una distinción importante en los lenguajes de programación es la diferencia entre un lenguaje orientado a objetos y un lenguaje basado en objetos. 

        Generalmente se considera que un lenguaje está basado en objetos si incluye las capacidades básicas de un objeto: identidad, propiedades y atributos. 

        Un lenguaje se considera orientado a objetos si está basado en objetos y también tiene la capacidad de polimorfismo, herencia, encapsulación y, posiblemente, composición. 

        El polimorfismo se refiere a la capacidad de sobrecargar el nombre de una función con múltiples comportamientos según los objetos que se le pasan. 

        El paso de mensajes convencional discrimina sólo en el primer objeto y considera que está "enviando un mensaje" a ese objeto. 

        Sin embargo, algunos lenguajes de programación orientados a objetos, como Flavors y Common Lisp Object System (CLOS), permiten discriminar en más del primer parámetro de la función. 

        La herencia es la capacidad de subclasificar una clase de objeto, de crear una nueva clase que es una subclase de una existente y hereda todas las restricciones de datos y comportamientos de sus padres, pero también agrega nuevos y/o cambia uno o más de ellos.


    Programación orientada a objetos

        En programación orientada a objetos, un objeto es un tipo de datos abstracto con la adición de polimorfismo y herencia. 

        En lugar de estructurar programas como código y datos, un sistema orientado a objetos integra los dos utilizando el concepto de "objeto". 

        Un objeto tiene estado (datos) y comportamiento (código). 

        Los objetos pueden corresponder a cosas que se encuentran en el mundo real.

        Así, por ejemplo, un programa de gráficos tendrá objetos como círculo, cuadrado, menú.

        Un sistema de compras online tendrá objetos como carrito de compras, cliente, producto. 

        El sistema de compras admitirá comportamientos como realizar pedidos, realizar pagos y ofrecer descuentos.

        Los objetos están diseñados como jerarquías de clases.

        Así, por ejemplo, en el sistema de compras puede haber clases de alto nivel, como productos electrónicos, productos de cocina y libros.

        Puede haber más mejoras, por ejemplo, en productos electrónicos: reproductores de CD, reproductores de DVD, etc. 

        Estas clases y subclases corresponden a conjuntos y subconjuntos en lógica matemática.


    Objetos especializados

        Un concepto importante para los objetos es el patrón de diseño. 

        Un patrón de diseño proporciona una plantilla reutilizable para abordar un problema común. 

        Las siguientes descripciones de objetos son ejemplos de algunos de los patrones de diseño más comunes para objetos.


        Objeto de función: 

            un objeto con un solo método (en C++, este método sería el operador de función, "operador()") que actúa de manera muy similar a una función (como un puntero de C/C++ a una función).


        Objeto inmutable: 

            un objeto configurado con un estado fijo en el momento de su creación y que no cambia posteriormente.


        Objeto de primera clase: 

            un objeto que se puede utilizar sin restricciones.


        Objeto contenedor: 

            un objeto que puede contener otros objetos.


        Objeto de fábrica: 

            un objeto cuyo propósito es crear otros objetos.


        Metaobjeto: 

            un objeto a partir del cual se pueden crear otros objetos (compárese con una clase, que no es necesariamente un objeto).


        Objeto prototipo:

            un metaobjeto especializado a partir del cual se pueden crear otros objetos copiándolos.


        Objeto de Dios: 

            un objeto que sabe o hace demasiado (es un ejemplo de antipatrón).

        
        Objeto singleton: 

            un objeto que es la única instancia de su clase durante la vida del programa.

        
        Objeto de filtro: 

            un objeto que recibe un flujo de datos como entrada y lo transforma en la salida del objeto.

            A menudo, los flujos de entrada y salida son flujos de caracteres, pero también pueden ser flujos de objetos arbitrarios. 

            Generalmente se usan en contenedores ya que ocultan la implementación existente con la abstracción requerida en el lado del desarrollador.



|| Reference

    Una referencia es un valor que permite a un programa acceder indirectamente a un dato particular, como el valor de una variable o un registro, en la memoria de la computadora o en algún otro dispositivo de almacenamiento. 

    Se dice que la referencia se refiere al dato y acceder al dato se llama desreferenciar la referencia. 

    Una referencia es distinta del dato mismo.

    Una referencia es un tipo de datos abstracto y puede implementarse de muchas maneras. Normalmente, una referencia se refiere a datos almacenados en la memoria de un sistema determinado y su valor interno es la dirección de memoria de los datos, es decir, una referencia se implementa como un puntero. Por esta razón, a menudo se dice que una referencia "señala" los datos. Otras implementaciones incluyen un desplazamiento (diferencia) entre la dirección del dato y alguna dirección "base" fija, un índice o identificador utilizado en una operación de búsqueda en una matriz o tabla, un identificador del sistema operativo, una dirección física en un dispositivo de almacenamiento o una dirección de red como una URL


    Representación formal

        Una referencia R es un valor que admite una operación, desreferencia(R), que produce un valor. 

        Por lo general, la referencia se escribe de manera que devuelva valores de un tipo específico, por ejemplo:

        ```
        
        interface Reference<T> {
            T value();
        }

        ```
        
        A menudo, la referencia también admite una operación de asignación store(R, x), lo que significa que es una variable abstracta.


    Usos: 

        Las referencias se utilizan ampliamente en programación, especialmente para pasar de manera eficiente datos grandes o mutables como argumentos para procedimientos, o para compartir dichos datos entre varios usos. 

        En particular, una referencia puede apuntar a una variable o registro que contiene referencias a otros datos.

        Esta idea es la base del direccionamiento indirecto y de muchas estructuras de datos vinculados, como las listas vinculadas. 

        Las referencias aumentan la flexibilidad en cuanto a dónde se pueden almacenar los objetos, cómo se asignan y cómo se pasan entre áreas de código. 

        Siempre que se pueda acceder a una referencia a los datos, se puede acceder a los datos a través de ella y no es necesario mover los datos en sí. 

        También facilitan el intercambio de datos entre diferentes áreas de código; cada uno mantiene una referencia a él.

        Las referencias pueden causar una complejidad significativa en un programa, en parte debido a la posibilidad de referencias colgantes y salvajes y en parte porque la topología de los datos con referencias es un gráfico dirigido, cuyo análisis puede ser bastante complicado.

        No obstante, las referencias son aún más sencillas de analizar que los punteros debido a la ausencia de aritmética de punteros.

        El mecanismo de referencias, si varía en su implementación, es una característica fundamental del lenguaje de programación común a casi todos los lenguajes de programación modernos. 

        Incluso algunos lenguajes que no admiten el uso directo de referencias tienen algún uso interno o implícito. 

        Por ejemplo, la convención de llamada por referencia se puede implementar con el uso explícito o implícito de referencias.


        Ejemplos:

            Los punteros son el tipo de referencia más primitivo. 

            Debido a su íntima relación con el hardware subyacente, son uno de los tipos de referencias más potentes y eficientes. 

            Sin embargo, también debido a esta relación, los punteros requieren una sólida comprensión por parte del programador de los detalles de la arquitectura de la memoria. 

            Debido a que los punteros almacenan la dirección de una ubicación de memoria, en lugar de un valor directamente, el uso inadecuado de los punteros puede provocar un comportamiento indefinido en un programa, particularmente debido a punteros colgantes o punteros salvajes. 

            Los punteros inteligentes son estructuras de datos opacas que actúan como punteros pero a las que solo se puede acceder a través de métodos particulares.

            Un identificador es una referencia abstracta y puede representarse de varias maneras. 

            Un ejemplo común son los identificadores de archivos (la estructura de datos FILE en la biblioteca de E/S estándar de C), que se utilizan para abstraer el contenido del archivo.

            Por lo general, representa tanto el archivo en sí, como cuando se solicita un bloqueo en el archivo, como una posición específica dentro del contenido del archivo, como cuando se lee un archivo.

            En informática distribuida, la referencia puede contener más que una dirección o identificador; también puede incluir una especificación integrada de los protocolos de red utilizados para localizar y acceder al objeto al que se hace referencia, la forma en que se codifica o serializa la información. 

            Así, por ejemplo, una descripción WSDL de un servicio web remoto puede verse como una forma de referencia; incluye una especificación completa de cómo localizar y vincularse a un servicio web en particular. 

            Una referencia a un objeto distribuido en vivo es otro ejemplo: es una especificación completa sobre cómo construir un pequeño componente de software llamado proxy que posteriormente participará en una interacción entre pares y a través del cual la máquina local puede obtener acceso a datos que se replican o existen sólo como un flujo de mensajes débilmente consistente. 

            En todos estos casos, la referencia incluye el conjunto completo de instrucciones, o una receta, sobre cómo acceder a los datos; en este sentido, cumple el mismo propósito que un identificador o dirección en la memoria.

            Si tenemos un conjunto de claves K y un conjunto de objetos de datos D, cualquier función bien definida (de un solo valor) de K a D ∪ {nulo} define un tipo de referencia, donde nulo es la imagen de una clave que no hace referencia a algo significativo.

            Una representación alternativa de dicha función es un gráfico dirigido llamado gráfico de alcanzabilidad. 

            Aquí, cada dato está representado por un vértice y hay una arista de u a v si el dato en u se refiere al dato en v.

            El grado máximo de salida es uno. 

            Estos gráficos son valiosos en la recolección de basura, donde se pueden usar para separar objetos accesibles de inaccesibles.


        Almacenamiento externo e interno:

            En muchas estructuras de datos, los objetos grandes y complejos se componen de objetos más pequeños. 

            Estos objetos normalmente se almacenan de dos maneras:

                1. Con el almacenamiento interno, el contenido del objeto más pequeño se almacena dentro del objeto más grande.
                 
                2. Con el almacenamiento externo, los objetos más pequeños se asignan en su propia ubicación y el objeto más grande solo almacena referencias a ellos.


            El almacenamiento interno suele ser más eficiente, porque hay un costo de espacio para las referencias y los metadatos de asignación dinámica, y un costo de tiempo asociado con la desreferenciación de una referencia y con la asignación de memoria para los objetos más pequeños. 

            El almacenamiento interno también mejora la localidad de referencia al mantener juntas en la memoria diferentes partes del mismo objeto grande.

            Sin embargo, existen diversas situaciones en las que se prefiere el almacenamiento externo:

                 Si la estructura de datos es recursiva, significa que puede contenerse a sí misma. Esto no se puede representar de forma interna.
                 
                 Si el objeto más grande se almacena en un área con espacio limitado, como la pila, entonces podemos evitar quedarnos sin almacenamiento almacenando objetos componentes grandes en otra región de memoria y haciendo referencia a ellos mediante referencias.
                 
                 Si los objetos más pequeños pueden variar en tamaño, a menudo resulta inconveniente o costoso cambiar el tamaño del objeto más grande para que aún pueda contenerlos.
                 
                 A menudo es más fácil trabajar con las referencias y se adaptan mejor a los nuevos requisitos.

            Algunos lenguajes, como Java, Smalltalk, Python y Scheme, no admiten almacenamiento interno.

            En estos lenguajes, se accede uniformemente a todos los objetos a través de referencias.


        Lenguajes: 

            Ensamblador: 
                
                En lenguaje ensamblador, es típico expresar referencias utilizando direcciones de memoria sin formato o índices en tablas.

                Funcionan, pero son algo complicados de usar, porque una dirección no dice nada sobre el valor al que apunta, ni siquiera qué tan grande es o cómo interpretarlo; dicha información está codificada en la lógica del programa.

                El resultado es que pueden ocurrir malas interpretaciones en programas incorrectos, causando errores desconcertantes.


            C/C++:

                El puntero sigue siendo uno de los tipos de referencias más populares en la actualidad. 

                Es similar a la representación de ensamblador de una dirección sin formato, excepto que lleva un tipo de datos estático que se puede usar en tiempo de compilación para garantizar que los datos a los que hace referencia no se malinterpreten. 

                Sin embargo, debido a que C tiene un sistema de tipos débil que se puede romper mediante conversiones (conversiones explícitas entre varios tipos de punteros y entre tipos de punteros y números enteros), aún es posible una interpretación errónea, aunque más difícil. 

                Su sucesor C++ intentó aumentar la seguridad de tipos de punteros con nuevos operadores de conversión, un tipo de referencia & y punteros inteligentes en su biblioteca estándar, pero aún conservaba la capacidad de eludir estos mecanismos de seguridad por motivos de compatibilidad.


            Lenguajes orientados a objetos:

                Varios lenguajes orientados a objetos como Eiffel, Java, C# y Visual Basic han adoptado un tipo de referencia mucho más opaco, generalmente denominado simplemente referencia. 

                Estas referencias tienen tipos como punteros C que indican cómo interpretar los datos a los que hacen referencia, pero son seguros en el sentido de que no pueden interpretarse como una dirección sin formato y no se permiten conversiones no seguras. 

                Las referencias se utilizan ampliamente para acceder y asignar objetos. 

                Las referencias también se utilizan en llamadas a funciones/métodos o en el paso de mensajes, y los recuentos de referencias se utilizan con frecuencia para realizar la recolección de basura de objetos no utilizados.


            Python:

                Incluye una amplia gama de referencias.

                Generalmente, los programadores usan id(var) para acceder a la dirección de referencia de una variable var. 

                La referencia en Python es más compleja que C++ u otros lenguajes de programación.

                Una constante (por ejemplo, un número entero 2) es un objeto en Python y, por tanto, tiene una referencia a una dirección fija.

                Cuando el programador llama a a = 2, el programa crea un espacio de memoria para la constante 2 y organiza una referencia a ella.

                Luego, el programa vincula la referencia de a con la dirección de 2, lo que revela que cambiar el valor de una variable numérica cambia la referencia de la misma. 

                Mientras que en los tipos mutables (por ejemplo, un tipo de lista), el cambio de valor no cambiará la referencia de la variable.

                Cuando se pasa una variable como parámetro de función, la función obtiene la referencia de forma predeterminada, no su valor. 

                Para tipos mutables, esto hace que la variable original sea fácil de modificar; para el tipo inmutable, modificar su valor en la función hará que la referencia de la variable temporal en la función se modifique a otro lugar, por lo tanto, no provocará que se cambie la variable original.


    Desreferenciar puntero: 

        Un puntero es una "referencia" a un valor almacenado en la memoria. 

        "Desreferenciar" es obtener el valor.

        ```c

        int a = 4 ;
        int *pA = &a;
        printf( "La REFERENCIA/número de llamada para la variable `a` es %p\n", pA );

        // El * hace que pA DEREFERENCIA... `a` a través del "número de llamada" `pA`.
        printf( "%d\n", *pA ); // imprime 4

        ```


        Desreferenciar un puntero significa obtener el valor almacenado en la ubicación de memoria señalada por el puntero. 

        El operador * se utiliza para hacer esto y se denomina operador de desreferenciación.

        ```c

        int a = 10;
        int*ptr = &a;

        printf("%d", *ptr); 

        // Con *ptr estoy desreferenciando el puntero.
        
        // Lo que significa que estoy preguntando el valor al que apunta el puntero.
        
        // ptr apunta a la ubicación en la memoria de la variable a.
        
        // En la ubicación de a, tenemos 10. Entonces, la desreferenciación da este valor.

        // Como tenemos control indirecto sobre la ubicación de a, podemos modificar su contenido usando el puntero. Esta es una forma indirecta de acceder a.

        
        *ptr = 20; // Ahora el contenido de a ya no es 10 y se ha modificado a 20

        ```


    Llamadas por valor, nombre y referencia: 


        Llamada por valor: 

            Forma normal, los valores de los parámetros reales se copian en parámetros formales.


        Llamada por referencia: 

            En lugar de los parámetros, se pasan sus direcciones y los parámetros formales apuntan a los parámetros reales.


        Llamada por nombre: 

            Al igual que las macros, la definición completa de la función reemplaza la llamada a la función y los parámetros formales son solo otro nombre para los parámetros reales.


        En Llamada por valor, se pasa una copia de la variable, mientras que en Llamada por referencia, se pasa una variable en sí.

        En Llamada por valor, los argumentos reales y formales se crearán en diferentes ubicaciones de memoria, mientras que en Llamada por referencia, los argumentos reales y formales se crearán en la misma ubicación de memoria.




|| Data type
    
    En informática y programación de computadoras, un tipo de datos (o simplemente tipo) es una colección o agrupación de valores de datos, generalmente especificados por un conjunto de valores posibles, un conjunto de operaciones permitidas sobre estos valores y/o una representación de estos valores. como tipos de máquinas. 

    Una especificación de tipo de datos en un programa restringe los posibles valores que puede tomar una expresión, como una variable o una llamada a una función. 

    En datos literales, le dice al compilador o intérprete cómo el programador pretende utilizar los datos.

    La mayoría de los lenguajes de programación admiten tipos de datos básicos de números enteros (de distintos tamaños), números de punto flotante (que se aproximan a los números reales), caracteres y booleanos.

    
    Características: 

        Se puede especificar un tipo de datos por muchas razones: similitud, conveniencia o para centrar la atención. 

        Con frecuencia es una cuestión de buena organización la que ayuda a comprender definiciones complejas. 

        Casi todos los lenguajes de programación incluyen explícitamente la noción de tipo de datos, aunque los tipos de datos posibles suelen estar restringidos por consideraciones de simplicidad, computabilidad o regularidad. 

        Una declaración explícita de tipo de datos normalmente permite al compilador elegir una representación de máquina eficiente, pero no se debe descartar la organización conceptual que ofrecen los tipos de datos.

        Diferentes lenguajes pueden utilizar diferentes tipos de datos o tipos similares con diferente semántica. 

        Por ejemplo, en el lenguaje de programación Python, int representa un número entero de precisión arbitraria que tiene operaciones numéricas tradicionales como suma, resta y multiplicación. 

        Sin embargo, en el lenguaje de programación Java, el tipo int representa el conjunto de números enteros de 32 bits cuyo valor varía entre −2,147,483,648 y 2,147,483,647, con operaciones aritméticas que se ajustan en caso de desbordamiento. 

        En Rust, este tipo de entero de 32 bits se denomina i32 y entra en pánico si se desborda en el modo de depuración.

        La mayoría de los lenguajes de programación también permiten al programador definir tipos de datos adicionales, generalmente combinando múltiples elementos de otros tipos y definiendo las operaciones válidas del nuevo tipo de datos. 

        Por ejemplo, un programador podría crear un nuevo tipo de datos llamado "número complejo" que incluiría partes reales e imaginarias, o un tipo de datos de color representado por tres bytes que denotan las cantidades de rojo, verde y azul, y una cadena que representa el nombre del color.

        Los tipos de datos se utilizan dentro de los sistemas de tipos, que ofrecen varias formas de definirlos, implementarlos y utilizarlos. 

        En un sistema de tipos, un tipo de datos representa una restricción impuesta a la interpretación de datos, que describe la representación, interpretación y estructura de valores u objetos almacenados en la memoria de la computadora. 

        El sistema de tipos utiliza información sobre el tipo de datos para verificar la exactitud de los programas informáticos que acceden a los datos o los manipulan. 

        Un compilador puede utilizar el tipo estático de un valor para optimizar el almacenamiento que necesita y la elección de algoritmos para las operaciones con el valor. 

        En muchos compiladores de C, por ejemplo, el tipo de datos float se representa en 32 bits, según la especificación IEEE para números de coma flotante de precisión simple.

        Por lo tanto, utilizarán operaciones de microprocesador específicas de punto flotante sobre esos valores (suma de punto flotante, multiplicación, etc.).


    Definición:

        Parnas, Shore y Weiss (1976) identificaron cinco definiciones de "tipo" que se utilizaron, a veces implícitamente, en la literatura:


        Sintáctico:

            Un tipo es una etiqueta puramente sintáctica asociada a una variable cuando se declara. 

            Aunque son útiles para sistemas de tipos avanzados, como los sistemas de tipos subestructurales, estas definiciones no proporcionan un significado intuitivo de los tipos.


        Representación:

            Un tipo se define en términos de una composición de tipos más primitivos (a menudo tipos de máquinas).


        Representación y comportamiento:

            Un tipo se define como su representación y un conjunto de operadores que manipulan estas representaciones.


        Espacio de valor:

            Un tipo es un conjunto de posibles valores que puede poseer una variable. 

            Tales definiciones permiten hablar de uniones (disjuntas) o productos de tipos cartesianos.


        Espacio de valores y comportamiento:

            Un tipo es un conjunto de valores que puede poseer una variable y un conjunto de funciones que se pueden aplicar a estos valores.


        La definición en términos de representación se hacía a menudo en lenguajes imperativos como ALGOL y Pascal, mientras que la definición en términos de espacio de valores y comportamiento se usaba en lenguajes de nivel superior como Simula y CLU. 

        Los tipos que incluyen comportamiento se alinean más estrechamente con los modelos orientados a objetos, mientras que un modelo de programación estructurada tendería a no incluir código y se denominan estructuras de datos antiguas y simples.


    Clasificación:

        Los tipos de datos se pueden clasificar según varios factores:

            Los tipos de datos primitivos o tipos de datos integrados son tipos integrados en una implementación de lenguaje. 

            Los tipos de datos definidos por el usuario son tipos no primitivos.

            Por ejemplo, los tipos numéricos de Java son primitivos, mientras que las clases están definidas por el usuario.


            Un valor de tipo atómico es un elemento de datos único que no se puede dividir en partes que lo componen. 

            Un valor de tipo compuesto o tipo agregado es una colección de elementos de datos a los que se puede acceder individualmente. 

            Por ejemplo, un número entero generalmente se considera atómico, aunque consta de una secuencia de bits, mientras que una matriz de números enteros es ciertamente compuesta.


            Los tipos de datos básicos o tipos de datos fundamentales se definen axiomáticamente a partir de nociones fundamentales o mediante la enumeración de sus elementos. 

            Los tipos de datos generados o tipos de datos derivados se especifican, y se definen parcialmente, en términos de otros tipos de datos.

            Todos los tipos básicos son atómicos. 

            Por ejemplo, los números enteros son un tipo básico definido en matemáticas, mientras que una matriz de números enteros es el resultado de aplicar un generador de tipo de matriz al tipo de número entero.


        La terminología varía: en la literatura, primitivo, incorporado, básico, atómico y fundamental pueden usarse indistintamente.


    Ejemplos:

        Tipos de datos de máquina:

            Todos los datos en computadoras basadas en electrónica digital se representan como bits (alternativas 0 y 1) en el nivel más bajo. 

            La unidad de datos direccionable más pequeña suele ser un grupo de bits llamado byte (normalmente un octeto, que tiene 8 bits). 

            La unidad procesada por instrucciones de código de máquina se llama palabra (a partir de 2011, normalmente 32 o 64 bits).

            Los tipos de datos de máquina exponen o ponen a disposición un control detallado sobre el hardware, pero esto también puede exponer detalles de implementación que hacen que el código sea menos portátil. 

            Por lo tanto, los tipos de máquinas se utilizan principalmente en programación de sistemas o lenguajes de programación de bajo nivel. 

            En los lenguajes de nivel superior, la mayoría de los tipos de datos se abstraen porque no tienen una representación de máquina definida por el lenguaje. 

            El lenguaje de programación C, por ejemplo, proporciona tipos como booleanos, enteros, números de punto flotante, etc., pero las representaciones de bits precisas de estos tipos están definidas por la implementación. 

            El único tipo C con una representación mecánica precisa es el tipo char que representa un byte.


        Tipo booleano:

            El tipo booleano representa los valores verdadero y falso. 

            Aunque sólo son posibles dos valores, a menudo se representan como una palabra y no como un solo bit, ya que se requieren más instrucciones de máquina para almacenar y recuperar un bit individual. 

            Muchos lenguajes de programación no tienen un tipo booleano explícito, sino que utilizan un tipo entero e interpretan (por ejemplo) 0 como falso y otros valores como verdadero. 

            Los datos booleanos se refieren a la estructura lógica de cómo se interpreta el lenguaje en el lenguaje de máquina.

            En este caso un booleano 0 se refiere a la lógica Falso. 

            Verdadero siempre es distinto de cero, especialmente uno que se conoce como booleano 1.


        Tipos numéricos:

            Casi todos los lenguajes de programación proporcionan uno o más tipos de datos enteros.

            Pueden proporcionar una pequeña cantidad de subtipos predefinidos restringidos a ciertos rangos (como cortos y largos y sus correspondientes variantes sin firmar en C/C++); o permitir a los usuarios definir libremente subrangos como 1..12 (por ejemplo, Pascal/Ada). 

            Si no existe un tipo nativo correspondiente en la plataforma de destino, el compilador los dividirá en código utilizando los tipos que sí existen. 

            Por ejemplo, si se solicita un entero de 32 bits en una plataforma de 16 bits, el compilador lo tratará tácitamente como una matriz de dos enteros de 16 bits.

            Los tipos de datos de coma flotante representan ciertos valores fraccionarios (números racionales, matemáticamente). 

            Aunque tienen límites predefinidos tanto en sus valores máximos como en su precisión, a veces se les llama engañosamente reales (que evocan los números reales matemáticos). 

            Por lo general, se almacenan internamente en la forma a × 2b (donde a y b son números enteros), pero se muestran en la forma decimal familiar.

            Los tipos de datos de punto fijo son convenientes para representar valores monetarios. 

            A menudo se implementan internamente como números enteros, lo que lleva a límites predefinidos.

            Para independizarse de los detalles arquitectónicos, se puede proporcionar un Bignum o un tipo numérico de precisión arbitraria.

            Esto representa un número entero o racional con una precisión limitada únicamente por la memoria disponible y los recursos computacionales en el sistema. 

            Las implementaciones de Bignum de operaciones aritméticas en valores del tamaño de una máquina son significativamente más lentas que las operaciones de máquina correspondientes.


        Tipos de cadenas y texto

            Las cadenas son una secuencia de caracteres que se utilizan para almacenar palabras o texto sin formato, la mayoría de las veces lenguajes de marcado textuales que representan texto formateado. 

            Los caracteres pueden ser una letra de algún alfabeto, un dígito, un espacio en blanco, un signo de puntuación, etc.

            Los caracteres se extraen de un conjunto de caracteres como ASCII.

            Los tipos de caracteres y cadenas pueden tener diferentes subtipos según la codificación de caracteres. 

            Se descubrió que el ASCII original de 7 bits de ancho era limitado y fue reemplazado por conjuntos de 8, 16 y 32 bits, que pueden codificar una amplia variedad de alfabetos no latinos (como el hebreo y el chino) y otros símbolos.

            Las cadenas pueden ser de longitud variable o fija, y algunos lenguajes de programación tienen ambos tipos. 

            También podrán subtipificarse por su tamaño máximo.

            Dado que la mayoría de los juegos de caracteres incluyen dígitos, es posible tener una cadena numérica, como "1234".

            Estas cadenas numéricas generalmente se consideran distintas de los valores numéricos como 1234, aunque algunos lenguajes realizan conversiones automáticas entre ellos.


        Punteros y referencias:

            El principal tipo derivado no compuesto es el puntero, un tipo de datos cuyo valor se refiere directamente a (o "apunta") a otro valor almacenado en otra parte de la memoria de la computadora usando su dirección. 

            Es un tipo primitivo de referencia. 

            (En términos cotidianos, un número de página de un libro podría considerarse un dato que remite a otro). 

            Los punteros suelen almacenarse en un formato similar a un número entero; sin embargo, intentar eliminar la referencia o "buscar" un puntero cuyo valor nunca fue una dirección de memoria válida provocaría que el programa fallara.

            Para mejorar este problema potencial, los punteros se consideran un tipo separado del tipo de datos al que apuntan, incluso si la representación subyacente es la misma.

    

|| Puntero

    En informática, un puntero es un objeto en muchos lenguajes de programación que almacena una dirección de memoria. 

    Este puede ser el de otro valor ubicado en la memoria de la computadora o, en algunos casos, el del hardware de la computadora asignado en memoria. 

    Un puntero hace referencia a una ubicación en la memoria y obtener el valor almacenado en esa ubicación se conoce como desreferenciar el puntero. 

    Como analogía, el número de página del índice de un libro podría considerarse un indicador de la página correspondiente; La desreferenciación de dicho puntero se haría pasando a la página con el número de página dado y leyendo el texto que se encuentra en esa página. 

    El formato y el contenido reales de una variable de puntero dependen de la arquitectura de la computadora subyacente.

    El uso de punteros mejora significativamente el rendimiento de operaciones repetitivas, como atravesar estructuras de datos iterables (por ejemplo, cadenas, tablas de búsqueda, tablas de control y estructuras de árbol).

    En particular, suele ser mucho más económico en tiempo y espacio copiar y desreferenciar punteros que copiar y acceder a los datos a los que apuntan los punteros.

    Los punteros también se utilizan para contener las direcciones de los puntos de entrada de las subrutinas llamadas en la programación de procedimientos y para vincular en tiempo de ejecución a bibliotecas de vínculos dinámicos (DLL). 

    En la programación orientada a objetos, los punteros a funciones se utilizan para vincular métodos, a menudo utilizando tablas de métodos virtuales.

    Un puntero es una implementación simple y más concreta del tipo de datos de referencia más abstracto. 

    Varios lenguajes, especialmente los de bajo nivel, admiten algún tipo de puntero, aunque algunos tienen más restricciones de uso que otros. 

    Si bien "puntero" se ha utilizado para referirse a referencias en general, se aplica más apropiadamente a estructuras de datos cuya interfaz permite explícitamente manipular el puntero (aritméticamente mediante aritmética de punteros) como una dirección de memoria, a diferencia de una cookie mágica o capacidad (capability) que no lo permite. 

    Debido a que los punteros permiten acceso tanto protegido como desprotegido a direcciones de memoria, existen riesgos asociados con su uso, particularmente en el último caso. 

    Los punteros primitivos suelen almacenarse en un formato similar a un número entero; sin embargo, intentar eliminar la referencia o "buscar" un puntero cuyo valor no sea una dirección de memoria válida podría provocar que el programa falle (o contenga datos no válidos). 

    Para aliviar este problema potencial, como cuestión de seguridad de tipos, los punteros se consideran un tipo separado parametrizado por el tipo de datos al que apuntan, incluso si la representación subyacente es un número entero. 

    También se pueden tomar otras medidas (como validación y verificación de límites) para verificar que la variable de puntero contenga un valor que sea una dirección de memoria válida y esté dentro del rango numérico que el procesador es capaz de direccionar.


    Diagrama de un puntero:

        Un puntero a que apunta a la dirección de memoria asociada con una variable b, es decir, a contiene la dirección de memoria 1008 de la variable b. 

        En este diagrama, la arquitectura informática utiliza el mismo espacio de direcciones y datos primitivos tanto para punteros como para no punteros; esta necesidad no debería ser el caso.


    Descripción formal: 

        En informática, un puntero es una especie de referencia.

        Un dato primitivo (data primitive) es cualquier dato que se puede leer o escribir en la memoria de la computadora mediante un acceso a la memoria (por ejemplo, tanto un byte como una palabra son primitivas).

        Un agregado de datos (data aggregate) es un grupo de primitivos que son lógicamente contiguos en la memoria y que se ven colectivamente como un dato (por ejemplo, un agregado podría consistir en 3 bytes lógicamente contiguos, cuyos valores representan las 3 coordenadas de un punto en el espacio). 

        Cuando un agregado está compuesto enteramente por el mismo tipo de primitivo, el agregado puede denominarse matriz; en cierto sentido, una palabra primitiva de varios bytes es una matriz de bytes y algunos programas usan palabras de esta manera.

        Un puntero es un concepto de programación utilizado en informática para hacer referencia o señalar una ubicación de memoria que almacena un valor o un objeto. 

        Es esencialmente una variable que almacena la dirección de memoria de otra variable o estructura de datos en lugar de almacenar los datos en sí.

        Los punteros se utilizan comúnmente en lenguajes de programación que admiten la manipulación directa de la memoria, como C y C++. 

        Permiten a los programadores trabajar con la memoria directamente, lo que permite una gestión eficiente de la memoria y estructuras de datos más complejas. 

        Al utilizar punteros, puede acceder y modificar datos ubicados en la memoria, pasar datos de manera eficiente entre funciones y crear estructuras de datos dinámicas como listas vinculadas, árboles y gráficos.

        En términos más simples, puedes pensar en un puntero como una flecha que apunta a un lugar específico en la memoria de una computadora, permitiéndote interactuar con los datos almacenados en esa ubicación.

        Un puntero de memoria (o simplemente un puntero) es una primitiva cuyo valor está destinado a ser utilizado como dirección de memoria; se dice que un puntero apunta a una dirección de memoria.

        También se dice que un puntero apunta a un dato [en la memoria] cuando el valor del puntero es la dirección de memoria del dato.

        De manera más general, un puntero es un tipo de referencia, y se dice que un puntero hace referencia a un dato almacenado en algún lugar de la memoria; obtener ese dato es desreferenciar el puntero. 

        La característica que separa los punteros de otros tipos de referencias es que el valor de un puntero debe interpretarse como una dirección de memoria, lo cual es un concepto de bajo nivel.

        Las referencias sirven como nivel de direccionamiento indirecto: el valor de un puntero determina qué dirección de memoria (es decir, qué dato) se utilizará en un cálculo. 

        Debido a que la dirección indirecta es un aspecto fundamental de los algoritmos, los punteros a menudo se expresan como un tipo de datos fundamental en los lenguajes de programación; En lenguajes de programación estáticamente (o fuertemente tipados), el tipo de puntero determina el tipo de dato al que apunta el puntero.


    Arquitectura y punteros: 

        Los punteros son una abstracción muy fina además de las capacidades de direccionamiento proporcionadas por la mayoría de las arquitecturas modernas. 

        En el esquema más simple, se asigna una dirección o un índice numérico a cada unidad de memoria del sistema, donde la unidad suele ser un byte o una palabra, dependiendo de si la arquitectura es direccionable por bytes o por palabras, transformando efectivamente toda la memoria en una matriz muy grande.

        Luego, el sistema también proporcionaría una operación para recuperar el valor almacenado en la unidad de memoria en una dirección determinada (usualmente utilizando los registros de propósito general de la máquina).

        En el caso habitual, un puntero es lo suficientemente grande como para contener más direcciones que unidades de memoria en el sistema. 

        Esto introduce la posibilidad de que un programa intente acceder a una dirección que no corresponde a ninguna unidad de memoria, ya sea porque no hay suficiente memoria instalada (es decir, más allá del rango de memoria disponible) o porque la arquitectura no admite dichas direcciones. 

        El primer caso, en determinadas plataformas como la arquitectura Intel x86, puede denominarse fallo de segmentación (segfault). 

        El segundo caso es posible en la implementación actual de AMD64, donde los punteros tienen una longitud de 64 bits y las direcciones solo se extienden a 48 bits. 

        Los punteros deben ajustarse a ciertas reglas (direcciones canónicas), por lo que si se elimina la referencia a un puntero no canónico, el procesador genera una falla de protección general.

        Por otro lado, algunos sistemas tienen más unidades de memoria que direcciones.

        En este caso, se emplea un esquema más complejo, como segmentación de memoria o paginación, para utilizar diferentes partes de la memoria en diferentes momentos. 

        Las últimas encarnaciones de la arquitectura x86 admiten hasta 36 bits de direcciones de memoria física, que se asignaron al espacio de direcciones lineales de 32 bits a través del mecanismo de paginación PAE. 

        Por lo tanto, sólo se puede acceder a 1/16 de la memoria total posible a la vez. 

        Otro ejemplo en la misma familia de computadoras fue el modo protegido de 16 bits del procesador 80286, que, aunque soportaba sólo 16 MB de memoria física, podía acceder hasta 1 GB de memoria virtual, pero la combinación de dirección de 16 bits y segmento Los registros hacían engorroso el acceso a más de 64 KB en una estructura de datos.

        Para proporcionar una interfaz coherente, algunas arquitecturas proporcionan E/S asignadas en memoria, lo que permite que algunas direcciones se refieran a unidades de memoria mientras que otras se refieren a registros de dispositivos de otros dispositivos en la computadora. 

        Existen conceptos análogos, como desplazamientos de archivos, índices de matrices y referencias a objetos remotos, que sirven para algunos de los mismos propósitos que las direcciones para otros tipos de objetos.


    Usos:

        Los punteros se admiten directamente y sin restricciones en lenguajes como PL/I, C, C++, Pascal, FreeBASIC e implícitamente en la mayoría de los lenguajes ensambladores. 

        Se utilizan principalmente para construir referencias, que a su vez son fundamentales para construir casi todas las estructuras de datos, así como para pasar datos entre diferentes partes de un programa.

        En los lenguajes de programación funcionales que dependen en gran medida de listas, las referencias de datos se gestionan de forma abstracta mediante el uso de construcciones primitivas como constructs (cons) y los elementos correspondientes car y cdr (operaciones primitivas), que pueden considerarse como punteros especializados al primer y segundo componente de una celda de constructs. 

        Esto da lugar a algo del "flavour" idiomático de la programación funcional.

        Al estructurar datos en tales listas construct, estos lenguajes facilitan medios recursivos para construir y procesar datos, por ejemplo, accediendo recursivamente a los elementos principales y finales de listas de listas; p.ej. "llevando el auto del cdr del cdr". 

        Por el contrario, la gestión de la memoria basada en la desreferenciación de punteros en alguna aproximación de una matriz de direcciones de memoria facilita el tratamiento de las variables como ranuras a las que se pueden asignar datos de forma imperativa.

        Cuando se trata de matrices, la operación de búsqueda crítica normalmente implica una etapa llamada cálculo de dirección que implica construir un puntero al elemento de datos deseado en la matriz. 

        En otras estructuras de datos, como las listas enlazadas, los punteros se utilizan como referencias para vincular explícitamente una parte de la estructura a otra.

        Los punteros se utilizan para pasar parámetros por referencia. 

        Esto es útil si el programador desea que las modificaciones de una función a un parámetro sean visibles para quien llama a la función. 

        Esto también es útil para devolver múltiples valores de una función.

        Los punteros también se pueden utilizar para asignar (allocate) y desasignar (deallocate) variables y matrices dinámicas en la memoria. 

        Dado que una variable a menudo se volverá redundante después de haber cumplido su propósito, es un desperdicio de memoria conservarla y, por lo tanto, es una buena práctica desasignarla (usando la referencia del puntero original) cuando ya no sea necesaria. 

        De lo contrario, se puede producir una pérdida de memoria (donde la memoria libre disponible disminuye gradualmente o, en casos graves, rápidamente, debido a la acumulación de numerosos bloques de memoria redundantes).


    Creación de puntero: 

        C pointers: 

            Definición 

        ```c

        int *ptr;

        ```

        Define un puntero: *

        Nombre/identificador: ptr

        Apuntará a un objeto de tipo entero: int


        Puntero nulo: 

            Debido a que el lenguaje C no especifica una inicialización implícita para objetos de duración de almacenamiento automático, a menudo se debe tener cuidado para garantizar que la dirección a la que apunta ptr sea válida; Es por eso que a veces se sugiere que un puntero se inicialice explícitamente con el valor del puntero nulo, que tradicionalmente se especifica en C con la macro estandarizada NULL.

        ```c

        int *ptr = NULL;

        ```


        Eliminar la referencia a un puntero nulo en C produce un comportamiento indefinido, que podría ser catastrófico.

        Sin embargo, la mayoría de las implementaciones simplemente detienen la ejecución del programa en cuestión, generalmente con un error de segmentación.

        Sin embargo, inicializar punteros innecesariamente podría dificultar el análisis del programa, ocultando así errores.

        En cualquier caso, una vez declarado un puntero, el siguiente paso lógico es que apunte a algo:

        ```c

        int a = 5;
        int *ptr = NULL;

        ptr = &a;

        ```

        Esto asigna el valor de la dirección de 'a' a ptr. 

        Por ejemplo, si a se almacena en la ubicación de memoria 0x8130, entonces el valor de ptr será 0x8130 después de la asignación. 

        Para desreferenciar el puntero, se vuelve a utilizar un asterisco:

        ```c

        *ptr = 8;

        ```

        Esto significa tomar el contenido de ptr (que es 0x8130), "localizar" esa dirección en la memoria y establecer su valor en 8. 

        Si más tarde se accede a a, su nuevo valor será 8.


        Este ejemplo puede resultar más claro si se examina la memoria directamente.

        Supongamos que 'a' está ubicado en la dirección 0x8130 en la memoria y ptr en 0x8134; Supongamos también que se trata de una máquina de 32 bits, de modo que un int tiene 32 bits de ancho.

        Lo siguiente es lo que quedaría en la memoria después de ejecutar el siguiente fragmento de código:

        ```c

        int a = 5;
        int *ptr = NULL;

        ```

        Dirección   Contenido
        0x8130      0x00000005
        0x8134      0x00000000 
        

        Asignando la dirección de 'a' a ptr:

        ```c

        ptr = &a;

        ```

        Produce los siguientes valores de memoria:

        Dirección   Contenido 
        0x8130      0x00000005
        0x8134      0x00008130


        Luego, desreferenciando ptr codificando:

        ```c

        *ptr = 8;

        ```

        la computadora tomará el contenido de ptr (que es 0x8130), 'localizará' esa dirección y asignará 8 a esa ubicación, lo que producirá la siguiente memoria:

        Dirección   Contenido 
        0x8130      0x00000008
        0x8134      0x00008130

        Claramente, acceder a 'a' producirá el valor de 8 porque la instrucción anterior modificó el contenido de a mediante el puntero ptr.


    Punteros en estructuras de datos: 

        Al configurar estructuras de datos como listas, colas y árboles, es necesario tener punteros para ayudar a gestionar cómo se implementa y controla la estructura.

        Ejemplos típicos de punteros son los punteros de inicio (start pointers), los punteros de finalización (end pointers) y los punteros de pila (stack pointers). 

        Estos punteros pueden ser absolutos (la dirección física real o una dirección virtual en la memoria virtual) o relativos (un desplazamiento de una dirección inicial absoluta ("base") que normalmente usa menos bits que una dirección completa, pero generalmente requerirá una operación aritmética adicional para resolver).

        Las direcciones relativas son una forma de segmentación de memoria manual y comparten muchas de sus ventajas y desventajas. 

        Se puede utilizar un desplazamiento de dos bytes, que contiene un entero sin signo de 16 bits, para proporcionar un direccionamiento relativo de hasta 64 KiB (2^16 bytes) de una estructura de datos. 

        Esto se puede extender fácilmente a 128, 256 o 512 KiB si la dirección apuntada se fuerza a alinearse en un límite de media palabra, palabra o palabra doble (pero, al requerir una operación bit a bit adicional de "desplazamiento a la izquierda", en 1, 2 o 3 bits para ajustar el desplazamiento en un factor de 2, 4 u 8, antes de su adición a la dirección base).

        Generalmente, sin embargo, tales esquemas causan muchos problemas y, por conveniencia para el programador, se prefieren las direcciones absolutas (y subyacentes a ellas, un espacio de direcciones plano).

        Se puede utilizar un desplazamiento de un byte, como el valor ASCII hexadecimal de un carácter (por ejemplo, X'29') para señalar un valor entero (o índice) alternativo en una matriz (por ejemplo, X'01'). 

        De esta manera, los caracteres se pueden traducir de manera muy eficiente desde 'datos sin procesar' a un índice secuencial utilizable y luego a una dirección absoluta sin una tabla de búsqueda.


        Arrays en c: 

            En C, la indexación de matrices se define formalmente en términos de aritmética de punteros; es decir, la especificación del lenguaje requiere que la matriz[i] sea equivalente a *(matriz + i).

            Por lo tanto, en C, las matrices pueden considerarse como punteros a áreas consecutivas de memoria (sin espacios) y la sintaxis para acceder a las matrices es idéntica a la que se puede utilizar para desreferenciar punteros.

            Por ejemplo, una matriz se puede declarar y utilizar de la siguiente manera:

            ```c

            int array[5]; /* Declara 5 enteros contiguos */

            int *ptr = array; /* Las matrices se pueden utilizar como punteros */

            ptr[0] = 1; /* Los punteros se pueden indexar con sintaxis de matriz */

            *(array + 1) = 2; /* Se puede desreferenciar las matrices con sintaxis de puntero */

            *(1 + array) = 2; /* La suma de punteros es conmutativa */

            2[array] = 4; /* El operador de subíndice es conmutativo */

            ```

            Esto asigna un bloque de cinco números enteros y nombra 'array', que actúa como un puntero al bloque. 

            Otro uso común de los punteros es apuntar a la memoria asignada dinámicamente desde 'malloc', que devuelve un bloque de memoria consecutivo de no menos del tamaño solicitado que se puede usar como una matriz.

            Si bien la mayoría de los operadores en matrices y punteros son equivalentes, el resultado del operador 'sizeof' difiere. 

            En este ejemplo, sizeof(array) se evaluará como 5*sizeof(int) (el tamaño de la matriz), mientras que sizeof(ptr) se evaluará como sizeof(int*), el tamaño del puntero en sí.


            Valores predeterminados: 

            ```c

            int array[5] = {2, 4, 3, 1, 5};

            ```

            Si la matriz está ubicada en la memoria comenzando en la dirección 0x1000 en una máquina little-endian de 32 bits, entonces la memoria contendrá lo siguiente (los valores están en hexadecimal, como las direcciones)


                    0   1   3
            1000    2   0   0
            1004    4   0   0
            1008    3   0   0
            100c    1   0   0
            1010    5   0   0 

            Se representan cinco números enteros: 2, 4, 3, 1 y 5. 

            Estos cinco números enteros ocupan 32 bits (4 bytes), cada uno con el byte menos significativo almacenado primero (esta es una arquitectura de CPU little-endian) y se almacenan consecutivamente, 
            comenzando en la dirección 0x1000.


        Sintaxis en C: 

            array significa 0x1000;
           
            array + 1 significa 0x1004: "+ 1" significa agregar el tamaño de 1 int, que es 4 bytes;
            
            *array significa desreferenciar el contenido de la matriz. Considerando el contenido como una dirección de memoria (0x1000), busque el valor en esa ubicación (0x0002);
            
            array[i] significa el elemento número i, basado en 0, de la matriz que se traduce en *(matriz + i).


        El último ejemplo es cómo acceder al contenido de una matriz. Desglosándolo:

            array + i es la ubicación de memoria del (i)ésimo elemento de la matriz, comenzando en i=0;

            *(array + i) toma esa dirección de memoria y la desreferencia para acceder al valor.


    Punteros seguros:

        Como un puntero permite a un programa intentar acceder a un objeto que puede no estar definido, los punteros pueden ser el origen de una variedad de errores de programación.

        Sin embargo, la utilidad de los punteros es tan grande que puede resultar difícil realizar tareas de programación sin ellos. 

        En consecuencia, muchos lenguajes han creado construcciones diseñadas para proporcionar algunas de las características útiles de los punteros sin algunos de sus inconvenientes, también denominados a veces peligros de puntero. 

        En este contexto, los punteros que se dirigen directamente a la memoria (como se utiliza en este artículo) se denominan punteros sin formato, en contraste con los punteros inteligentes u otras variantes.

        Un problema importante con los punteros es que, siempre que puedan manipularse directamente como un número, se puede hacer que apunten a direcciones no utilizadas o a datos que se utilizan para otros fines. 

        Muchos lenguajes, incluidos la mayoría de los lenguajes de programación funcionales y los lenguajes imperativos recientes como Java, reemplazan los punteros con un tipo de referencia más opaco, generalmente denominado simplemente referencia, que solo puede usarse para referirse a objetos y no manipularse como números, lo que evita error de tipo. 

        La indexación de matrices se trata como un caso especial.

        Un puntero que no tiene ninguna dirección asignada se denomina puntero salvaje.

        Cualquier intento de utilizar dichos punteros no inicializados puede provocar un comportamiento inesperado, ya sea porque el valor inicial no es una dirección válida o porque su uso puede dañar otras partes del programa. 

        El resultado suele ser un error de segmentación, una infracción de almacenamiento o una rama salvaje (si se utiliza como puntero de función o dirección de rama).

        En sistemas con asignación de memoria explícita, es posible crear un puntero colgante desasignando la región de memoria a la que apunta. 

        Este tipo de puntero es peligroso y sutil porque una región de memoria desasignada puede contener los mismos datos que tenía antes de ser desasignada, pero luego puede ser reasignada y sobrescrita por código no relacionado, desconocido para el código anterior. 

        Los lenguajes con recolección de basura evitan este tipo de error porque la desasignación se realiza automáticamente cuando no hay más referencias en el alcance.

        Algunos lenguajes, como C++, admiten punteros inteligentes, que utilizan una forma sencilla de recuento de referencias para ayudar a realizar un seguimiento de la asignación de memoria dinámica además de actuar como referencia. 

        En ausencia de ciclos de referencia, donde un objeto se refiere a sí mismo indirectamente a través de una secuencia de punteros inteligentes, estos eliminan la posibilidad de punteros colgantes y pérdidas de memoria. 

        Las cadenas de Delphi admiten el recuento de referencias de forma nativa.

        El lenguaje de programación Rust introduce un verificador de préstamos, duración de los punteros y una optimización basada en tipos de opciones para punteros nulos para eliminar errores de puntero, sin recurrir a la recolección de basura.



|| Dirección de memoria

    En informática, una dirección de memoria es una referencia a una ubicación de memoria específica utilizada en varios niveles por el software y el hardware.

    Las direcciones de memoria son secuencias de dígitos de longitud fija que se muestran y manipulan convencionalmente como enteros sin signo. 

    Esta semántica numérica se basa en características de la CPU (como el puntero de instrucción y los registros de direcciones incrementales), así como en el uso de la memoria como una matriz respaldada por varios lenguajes de programación.


    Diagrama:

        En una computadora que utiliza memoria virtual, acceder a la ubicación correspondiente a una dirección de memoria puede implicar muchos niveles.


    Direcciones físicas:

        La memoria principal de una computadora digital consta de muchas ubicaciones de memoria. 

        Cada ubicación de memoria tiene una dirección física que es un código. 

        La CPU (u otro dispositivo) puede usar el código para acceder a la ubicación de memoria correspondiente.

        Generalmente, sólo el software del sistema, es decir, el BIOS, los sistemas operativos y algunos programas de utilidad especializados (por ejemplo, probadores de memoria), direccionan la memoria física utilizando operandos de código de máquina o registros de procesador, instruyendo a la CPU para que dirija un dispositivo de hardware, llamado controlador de memoria, a utilice el bus de memoria o el bus del sistema, o buses de control, dirección y datos separados, para ejecutar los comandos del programa. 

        El bus de los controladores de memoria consta de varias líneas paralelas, cada una representada por un dígito binario (bit). 

        El ancho del bus y, por tanto, el número de unidades de almacenamiento direccionables y el número de bits en cada unidad, varían entre computadoras.


    Direcciones lógicas:
        
        Un programa de computadora utiliza direcciones de memoria para ejecutar código de máquina y para almacenar y recuperar datos. 

        En las primeras computadoras, las direcciones lógicas y físicas correspondían, pero desde la introducción de la memoria virtual la mayoría de los programas de aplicación no conocen las direcciones físicas. 

        Más bien, abordan direcciones lógicas, o direcciones virtuales, utilizando la unidad de administración de memoria de la computadora y el mapeo de memoria del sistema operativo.


    Unidad de resolución de direcciones

        La mayoría de las computadoras modernas son direccionables por bytes.

        Cada dirección identifica un único byte (ocho bits) de almacenamiento. 

        Los datos de más de un byte se pueden almacenar en una secuencia de direcciones consecutivas. 

        Existen computadoras direccionables por palabra, donde la unidad mínima de almacenamiento direccionable es exactamente la palabra del procesador. 

        Por ejemplo, la minicomputadora Data General Nova y las microcomputadoras Texas Instruments TMS9900 y National Semiconductor IMP-16 usaban palabras de 16 bits, y había muchas computadoras centrales de 36 bits (por ejemplo, PDP-10) que usaban direccionamiento de palabras de 18 bits, no direccionamiento de bytes, lo que da un espacio de direcciones de 2^18 palabras de 36 bits, aproximadamente 1 megabyte de almacenamiento.

        La eficiencia del direccionamiento de la memoria depende del tamaño de bits del bus utilizado para las direcciones: cuantos más bits se utilicen, más direcciones estarán disponibles para la computadora. 

        Por ejemplo, una máquina direccionable de 8 bits con un bus de direcciones de 20 bits (por ejemplo, Intel 8086) puede direccionar 2^20 (1,048,576) ubicaciones de memoria, o un MiB de memoria, mientras que un bus de 32 bits (por ejemplo, Intel 80386) direcciones 2^32 (4,294,967,296) ubicaciones, o un espacio de direcciones de 4 GiB. 

        Por el contrario, una máquina direccionable por palabras de 36 bits con un bus de direcciones de 18 bits dirige sólo 2^18 (262,144) ubicaciones de 36 bits (9,437,184 bits), equivalente a 1,179,648 bytes de 8 bits, o 1152 KiB, o 1,125 MiB, ligeramente más que el 8086.


    Tamaño de palabra versus tamaño de dirección

        El tamaño de palabra es una característica de la arquitectura de la computadora que indica la cantidad de bits que una CPU puede procesar al mismo tiempo. 

        Los procesadores modernos, incluidos los sistemas integrados, suelen tener un tamaño de palabra de 8, 16, 24, 32 o 64 bits; la mayoría de las computadoras de uso general actuales utilizan 32 o 64 bits. 

        Históricamente se han utilizado muchos tamaños diferentes, incluidos 8, 9, 10, 12, 18, 24, 36, 39, 40, 48 y 60 bits.

        Muy a menudo, cuando nos referimos al tamaño de las palabras de una computadora moderna, también se describe el tamaño del espacio de direcciones en esa computadora. 

        Por ejemplo, una computadora que se dice que es de "32 bits" también suele permitir direcciones de memoria de 32 bits; una computadora de 32 bits direccionable por bytes puede direccionar 2^32 = 4.294.967.296 bytes de memoria, o 4 gibibytes (GiB).

        Esto permite almacenar eficientemente una dirección de memoria en una palabra.

        Sin embargo, esto no siempre es cierto. 

        Las computadoras pueden tener direcciones de memoria mayores o menores que el tamaño de sus palabras. 

        Por ejemplo, muchos procesadores de 8 bits, como el MOS Technology 6502, admitían direcciones de 16 bits; de lo contrario, se habrían limitado a tan solo 256 bytes de direccionamiento de memoria. 

        Los Intel 8088 e Intel 8086 de 16 bits admitían direccionamiento de 20 bits mediante segmentación, lo que les permitía acceder a 1 MiB en lugar de 64 KiB de memoria. 

        Todos los procesadores Intel Pentium desde el Pentium Pro incluyen Extensiones de direcciones físicas (PAE) que admiten la asignación de direcciones físicas de 36 bits a direcciones virtuales de 32 bits. 

        Muchos de los primeros procesadores tenían 2 direcciones por palabra, como los procesadores de 36 bits.

        En teoría, las computadoras modernas de 64 bits direccionables por bytes pueden direccionar 2^64 bytes (16 exbibytes), pero en la práctica la cantidad de memoria está limitada por la CPU, el controlador de memoria o el diseño de la placa de circuito impreso (por ejemplo, la cantidad de memoria física, conectores o cantidad de memoria soldada).


    Contenido de cada ubicación de memoria.

        Cada ubicación de memoria en una computadora con programa almacenado contiene un número binario o decimal de algún tipo. 

        Su interpretación, como dato de algún tipo de datos o como instrucción, y su uso están determinados por las instrucciones que los recuperan y manipulan.

        Algunos de los primeros programadores combinaban instrucciones y datos en palabras como una forma de ahorrar memoria, cuando era caro: el Manchester Mark 1 tenía espacio en sus palabras de 40 bits para almacenar pequeños fragmentos de datos; su procesador ignoraba una pequeña sección en medio de una palabra, y eso a menudo se explotaba como almacenamiento de datos adicional. 

        Los programas autorreplicantes, como los virus, se tratan a sí mismos a veces como datos y otras veces como instrucciones. 

        El código de modificación automática generalmente está en desuso hoy en día, ya que dificulta desproporcionadamente las pruebas y el mantenimiento en comparación con el ahorro de unos pocos bytes, y también puede dar resultados incorrectos debido a las suposiciones del compilador o del procesador sobre el estado de la máquina, pero a veces todavía se usa deliberadamente, con gran cuidado.


    Espacio de direcciones en la programación de aplicaciones.

        En un entorno multitarea moderno, un proceso de aplicación generalmente tiene en su espacio (o espacios) de direcciones fragmentos de memoria de los siguientes tipos:


        Código de máquina, que incluye:


            código propio del programa (históricamente conocido como segmento de código o segmento de texto);
            
            bibliotecas compartidas.
        

        Datos, incluyendo:

            datos inicializados (segmento de datos);
            
            variables no inicializadas (pero asignadas);
            
            pila de tiempo de ejecución;
             
            heap/montón;
            
            Memoria compartida y archivos mapeados en memoria.


        Es posible que algunas partes del espacio de direcciones no estén asignadas en absoluto.

        Algunos sistemas tienen una arquitectura de memoria "dividida" donde el código de máquina, las constantes y los datos se encuentran en diferentes ubicaciones y pueden tener diferentes tamaños de direcciones. 

        Por ejemplo, los microcontroladores PIC18 tienen un contador de programa de 21 bits para direccionar el código de máquina y las constantes en la memoria Flash, y registros de direcciones de 12 bits para direccionar los datos en SRAM.


    Esquemas de direccionamiento:

        Un programa de computadora puede acceder a una dirección dada explícitamente; en programación de bajo nivel, esto generalmente se denomina dirección absoluta o, a veces, dirección específica, y se conoce como tipo de datos de puntero en lenguajes de nivel superior. 

        Pero un programa también puede usar una dirección relativa que especifica una ubicación en relación con otro lugar (la dirección base). 

        Hay muchos más modos de direccionamiento indirecto.

        La asignación de direcciones lógicas a la memoria física y virtual también agrega varios niveles de direccionamiento indirecto.


    Modelos de memoria:

        Muchos programadores prefieren abordar la memoria de manera que no haya distinción entre el espacio de código y el espacio de datos, así como entre la memoria física y virtual; en otras palabras, los punteros numéricamente idénticos se refieren exactamente al mismo byte de RAM.

        Sin embargo, muchas de las primeras computadoras no soportaban un modelo de memoria tan plana; en particular, las máquinas de arquitectura Harvard obligaban a que el almacenamiento de programas estuviera completamente separado del almacenamiento de datos. 

        Muchos DSP modernos (como el Motorola 56000) tienen tres áreas de almacenamiento separadas: almacenamiento de programas, almacenamiento de coeficientes y almacenamiento de datos. 

        Algunas instrucciones de uso común se obtienen de las tres áreas simultáneamente; menos áreas de almacenamiento (incluso si hubiera el mismo total de bytes de almacenamiento) harían que esas instrucciones se ejecutaran más lentamente.


        Modelos de memoria en arquitectura x86.

            Los primeros procesadores x86 utilizan direcciones de modelo de memoria segmentada basadas en una combinación de dos números: un segmento de memoria y un desplazamiento dentro de ese segmento.

            Algunos segmentos se tratan implícitamente como segmentos de código, dedicados a instrucciones, segmentos de pila o segmentos de datos normales. 

            Aunque los usos son diferentes, los segmentos no tienen diferentes protecciones de memoria que reflejen esto. 

            En el modelo de memoria plana, todos los segmentos (registros de segmentos) generalmente se establecen en cero y solo los desplazamientos son variables.


    Memoria: 

        La memoria de la computadora almacena información, como datos y programas, para su uso inmediato en la computadora. 

        El término memoria suele ser sinónimo de los términos RAM, memoria principal o almacenamiento primario. 

        Los sinónimos arcaicos de memoria principal incluyen núcleo (para memoria de núcleo magnético) y almacén.

        La memoria principal funciona a alta velocidad en comparación con el almacenamiento masivo, que es más lento pero menos costoso por bit y de mayor capacidad.

        Además de almacenar programas abiertos y datos que se procesan activamente, la memoria de la computadora sirve como caché de almacenamiento masivo y búfer de escritura para mejorar el rendimiento de lectura y escritura. 

        Los sistemas operativos toman prestada capacidad de RAM para el almacenamiento en caché siempre que no la necesite el software en ejecución. 

        Si es necesario, el contenido de la memoria de la computadora se puede transferir al almacenamiento; Una forma común de hacerlo es mediante una técnica de gestión de memoria llamada memoria virtual.

        La memoria de las computadoras modernas se implementa como una memoria semiconductora, donde los datos se almacenan dentro de celdas de memoria construidas a partir de transistores MOS y otros componentes en un circuito integrado. 

        Hay dos tipos principales de memoria semiconductora: volátil y no volátil.

        Ejemplos de memoria no volátil son la memoria flash y la memoria ROM, PROM, EPROM y EEPROM. 

        Ejemplos de memoria volátil son la memoria dinámica de acceso aleatorio (DRAM) utilizada para el almacenamiento primario y la memoria estática de acceso aleatorio (SRAM) utilizada principalmente para el caché de la CPU.

        La mayor parte de la memoria de semiconductores está organizada en celdas de memoria, cada una de las cuales almacena un bit (0 o 1). 

        La organización de la memoria flash incluye tanto un bit por celda de memoria como una celda de varios niveles capaz de almacenar múltiples bits por celda. 

        Las celdas de memoria se agrupan en palabras de longitud fija, por ejemplo, 1, 2, 4, 8, 16, 32, 64 o 128 bits. 

        Se puede acceder a cada palabra mediante una dirección binaria de N bits, lo que permite almacenar 2^N palabras en la memoria.


    Memoria volatil:

        La memoria volátil es la memoria de la computadora que requiere energía para mantener la información almacenada. 

        La mayoría de la memoria volátil de semiconductores modernos es RAM estática (SRAM) o RAM dinámica (DRAM).

        La DRAM domina la memoria del sistema de escritorio. 

        SRAM se utiliza para el caché de la CPU. 

        La SRAM también se encuentra en pequeños sistemas integrados que requieren poca memoria.

        SRAM conserva su contenido mientras la energía esté conectada y puede usar una interfaz más simple, pero comúnmente usa seis transistores por bit. 

        La RAM dinámica es más complicada para la interfaz y el control, ya que necesita ciclos de actualización regulares para evitar perder su contenido, pero utiliza sólo un transistor y un condensador por bit, lo que le permite alcanzar densidades mucho más altas y costos por bit mucho más económicos.


    Memoria no volátil:

        La memoria no volátil puede retener la información almacenada incluso cuando no está alimentada. 

        Ejemplos de memoria no volátil incluyen memoria de sólo lectura, memoria flash, la mayoría de los tipos de dispositivos magnéticos de almacenamiento informático (por ejemplo, unidades de disco duro, disquetes y cintas magnéticas), discos ópticos y los primeros métodos de almacenamiento informático, como tambores magnéticos y cintas de papel. y tarjetas perforadas.

        Las tecnologías de memoria no volátil en desarrollo incluyen RAM ferroeléctrica, celda de metalización programable (PMC), RAM magnética de par de transferencia de giro, SONOS, memoria resistiva de acceso aleatorio, memoria racetrack (DWM), Nano-RAM, 3D XPoint y memoria millipede.


    Memoria semivolátil:

        Una tercera categoría de memoria es semivolátil. 

        El término se utiliza para describir una memoria que tiene una duración no volátil limitada después de que se corta la energía, pero luego finalmente se pierden los datos. 

        Un objetivo típico al utilizar una memoria semivolátil es proporcionar el alto rendimiento y la durabilidad asociados con las memorias volátiles y, al mismo tiempo, proporcionar algunos beneficios de la memoria no volátil.

        Por ejemplo, algunos tipos de memoria no volátil se desgastan al escribir. 

        Una celda desgastada tiene una mayor volatilidad pero por lo demás continúa funcionando. 

        De este modo, las ubicaciones de datos que se escriben con frecuencia pueden orientarse hacia el uso de circuitos desgastados. 

        Siempre que la ubicación se actualice dentro de un tiempo de retención conocido, los datos seguirán siendo válidos. 

        Después de un período de tiempo sin actualización, el valor se copia a un circuito menos desgastado con una retención más larga. 

        Escribir primero en el área desgastada permite una alta velocidad de escritura y al mismo tiempo evita el desgaste en los circuitos no desgastados.

        Como segundo ejemplo, una STT-RAM puede volverse no volátil construyendo celdas grandes, pero hacerlo aumenta el costo por bit y los requisitos de energía y reduce la velocidad de escritura. 

        El uso de celdas pequeñas mejora el costo, la potencia y la velocidad, pero conduce a un comportamiento semivolátil. 

        En algunas aplicaciones, el aumento de la volatilidad se puede gestionar para proporcionar muchos beneficios de una memoria no volátil, por ejemplo, cortando la energía pero forzando una reactivación antes de que se pierdan los datos; o almacenando en caché datos de solo lectura y descartando los datos almacenados en caché si el tiempo de apagado excede el umbral no volátil.

        El término semivolátil también se utiliza para describir el comportamiento semivolátil construido a partir de otros tipos de memoria, como nvSRAM, que combina SRAM y una memoria no volátil en el mismo chip, donde una señal externa copia datos de la memoria volátil al memoria no volátil, pero si se corta la alimentación antes de que se produzca la copia, los datos se pierden.

        Otro ejemplo es la RAM respaldada por batería, que utiliza una batería externa para alimentar el dispositivo de memoria en caso de una pérdida de energía externa.

        Si la energía está apagada durante un período prolongado, la batería puede agotarse y provocar la pérdida de datos.


    Gestión de memoria:

        La gestión adecuada de la memoria es vital para que un sistema informático funcione correctamente. 

        Los sistemas operativos modernos cuentan con sistemas complejos para administrar adecuadamente la memoria. 

        No hacerlo puede provocar errores o un rendimiento lento.


    Bugs: 

        La gestión inadecuada de la memoria es una causa común de errores y vulnerabilidades de seguridad, incluidos los siguientes tipos:

            Una pérdida de memoria ocurre cuando un programa solicita memoria del sistema operativo y nunca la devuelve cuando termina con ella. Un programa con este error requerirá gradualmente más y más memoria hasta que el programa falle cuando el sistema operativo se agote.

            Se produce un error de segmentación cuando un programa intenta acceder a una memoria a la que no tiene permiso de acceso. Generalmente, el sistema operativo finalizará un programa que haga esto.

            Un desbordamiento del búfer ocurre cuando un programa escribe datos hasta el final de su espacio asignado y luego continúa escribiendo datos más allá de este en la memoria que ha sido asignada para otros fines. Esto puede provocar un comportamiento errático del programa, incluidos errores de acceso a la memoria, resultados incorrectos, un bloqueo o una violación de la seguridad del sistema. Por tanto, son la base de muchas vulnerabilidades de software y pueden explotarse maliciosamente.


    Memoria virtual:

        La memoria virtual es un sistema en el que el sistema operativo administra la memoria física, generalmente con la ayuda de una unidad de administración de memoria, que forma parte de muchas CPU modernas. 

        Permite utilizar múltiples tipos de memoria. 

        Por ejemplo, algunos datos se pueden almacenar en la RAM mientras que otros se almacenan en un disco duro (por ejemplo, en un archivo de intercambio/swapfile/memory paging), funcionando como una extensión de la jerarquía de caché. 

        Esto ofrece varias ventajas.

        Los programadores de computadoras ya no necesitan preocuparse por dónde se almacenan físicamente sus datos o si la computadora del usuario tendrá suficiente memoria. 

        El sistema operativo colocará los datos utilizados activamente en la RAM, que es mucho más rápida que los discos duros. 

        Cuando la cantidad de RAM no es suficiente para ejecutar todos los programas actuales, puede resultar en una situación en la que la computadora pasa más tiempo moviendo datos de la RAM al disco y viceversa que realizando tareas; esto se conoce como paliza/thrashing.


    Memoria protegida:

        La memoria protegida es un sistema en el que a cada programa se le asigna un área de memoria para usar y se le impide salir de ese rango. 

        Si el sistema operativo detecta que un programa ha intentado alterar la memoria que no le pertenece, el programa se finaliza (o se restringe o redirige de otro modo). 

        De esta manera, sólo el programa infractor falla y otros programas no se ven afectados por el mal comportamiento (ya sea accidental o intencional). 

        El uso de memoria protegida mejora enormemente tanto la confiabilidad como la seguridad de un sistema informático.

        Sin memoria protegida, es posible que un error en un programa altere la memoria utilizada por otro programa.

        Esto hará que ese otro programa se ejecute en la memoria dañada con resultados impredecibles. 

        Si la memoria del sistema operativo está dañada, es posible que todo el sistema informático falle y sea necesario reiniciarlo. 

        En ocasiones, los programas alteran intencionadamente la memoria utilizada por otros programas. 

        Esto lo hacen virus y malware para apoderarse de las computadoras. 

        También puede ser utilizado de forma benigna por programas deseables destinados a modificar otros programas, depuradores, por ejemplo, para insertar puntos de interrupción o ganchos/hooks.


|| Unidades de información
    
    En informática y telecomunicaciones digitales una unidad de información es la capacidad de algún sistema de almacenamiento de datos estándar o canal de comunicación, utilizado para medir las capacidades de otros sistemas y canales. 

    En teoría de la información, las unidades de información también se utilizan para medir la información contenida en los mensajes y la entropía de variables aleatorias.

    Las unidades de capacidad de almacenamiento de datos más utilizadas son el bit, la capacidad de un sistema que tiene sólo dos estados, y el byte (u octeto), que equivale a ocho bits. 

    Se pueden formar múltiplos de estas unidades a partir de éstas con los prefijos SI (prefijos de potencia de diez) o los prefijos binarios IEC más nuevos (prefijos de potencia de dos).


    Unidades primarias

        En 1928, Ralph Hartley observó un principio fundamental de almacenamiento, que fue formalizado aún más por Claude Shannon en 1945: la información que se puede almacenar en un sistema es proporcional al logaritmo de N posibles estados de ese sistema, denotado logb N.

        Cambiar la base del logaritmo de b a un número diferente c tiene el efecto de multiplicar el valor del logaritmo por una constante fija, es decir logc N = (logc b)*logb N. 

        Por lo tanto, la elección de la base b determina la unidad utilizada para medir información. 

        En particular, si b es un número entero positivo, entonces la unidad es la cantidad de información que se puede almacenar en un sistema con b estados posibles.

        Cuando b es 2, la unidad es el shannon, igual al contenido de información de un "bit" (un acrónimo de dígito binario). 

        Un sistema con 8 estados posibles, por ejemplo, puede almacenar hasta log2 8 = 3 bits de información. 

        Otras unidades que han sido nombradas incluyen:

        Base b = 3
             
            la unidad se llama "trit" y es igual a log2 3 (≈ 1,585) bits.


        Base b = 10

            la unidad se llama dígito decimal, hartley, ban, decit o dit, y es igual a log2 10 (≈ 3,322) bits.


        Base b = e, la base de los logaritmos naturales
            
            la unidad se llama nat, nit o nepit (del neperiano) y vale log2 e (≈ 1,443) bits.


        Los términos trit, ban y nat rara vez se utilizan para medir la capacidad de almacenamiento; pero el nat, en particular, se usa a menudo en teoría de la información, porque los logaritmos naturales son matemáticamente más convenientes que los logaritmos en otras bases.


    Unidades derivadas del bit

        Se utilizan varios nombres convencionales para colecciones o grupos de bits.


        Byte:

            Históricamente, un byte era la cantidad de bits utilizados para codificar un carácter de texto en la computadora, lo que dependía de la arquitectura del hardware de la computadora; pero hoy casi siempre significa ocho bits, es decir, un octet. 

            Un byte puede representar 256 (2^8) valores distintos, como números enteros no negativos de 0 a 255 o enteros con signo de −128 a 127. 

            El estándar IEEE 1541-2002 especifica "B" (mayúscula) como símbolo del byte. 

            (IEC 80000-13 usa "o" para octeto en francés, pero también permite "B" en inglés, que es lo que realmente se usa). 

            Los bytes, o múltiplos de ellos, casi siempre se utilizan para especificar el tamaño de los archivos informáticos y la capacidad de las unidades de almacenamiento. 

            La mayoría de las computadoras y dispositivos periféricos modernos están diseñados para manipular datos en bytes completos o grupos de bytes, en lugar de bits individuales.


        Nibble:

            Un grupo de cuatro bits, o medio byte, a veces se denomina nibble, nybble o nyble. 

            Esta unidad se utiliza con mayor frecuencia en el contexto de representaciones de números hexadecimales, ya que un nibble tiene la misma cantidad de información que un dígito hexadecimal.


        Crumb:

            Un grupo de dos bits o un cuarto de byte se llamaba crumb, y se usaba a menudo en las primeras computadoras de 8 bits (ver Atari 2600, ZX Spectrum).

            Ahora está en gran parte desaparecido.


        Word, block y page:

            Las computadoras suelen manipular bits en grupos de un tamaño fijo, llamados convencionalmente 'word'. 

            La cantidad de bits en una palabra generalmente se define por el tamaño de los registros en la CPU de la computadora o por la cantidad de bits de datos que se obtienen de su memoria principal en una sola operación. 

            En la arquitectura IA-32 más comúnmente conocida como x86-32, una palabra tiene 32 bits, pero otras arquitecturas pasadas y actuales usan palabras con 4, 8, 9, 12, 13, 16, 18, 20, 21, 22, 24. , 25, 29, 30, 31, 32, 33, 35, 36, 38, 39, 40, 42, 44, 48, 50, 52, 54, 56, 60, 64, 72 bits u otros.

            Algunas instrucciones de máquina y formatos de números de computadora utilizan dos palabras (una "palabra doble" o "dword") o cuatro palabras (una "quad word" o "quad").

            Los cachés de memoria de las computadoras generalmente operan en bloques de memoria que constan de varias palabras consecutivas.

            Estas unidades se denominan habitualmente bloques de caché o, en los cachés de CPU, líneas de caché.

            Los sistemas de memoria virtual dividen el almacenamiento principal de la computadora en unidades aún más grandes, tradicionalmente llamadas páginas.


        Sistemas de multiplos:

            Los términos para grandes cantidades de bits se pueden formar usando el rango estándar de prefijos SI para potencias de 10, por ejemplo, kilo = 10^3 = 1000 (como kilobit o kbit), mega = 10^6 = 1000000 (como megabit o Mbit) y giga = 10^9 = 1000000000 (como en gigabit o Gbit). 

            Estos prefijos se utilizan con mayor frecuencia para múltiplos de bytes, como en kilobyte (1 kB = 8000 bits), megabyte (1 MB = 8000000 bits) y gigabyte (1 GB = 8000000000 bits).

            Sin embargo, por razones técnicas, las capacidades de las memorias de las computadoras y de algunas unidades de almacenamiento suelen ser múltiplos de una potencia grande de dos, como 2^28 = 268435456 bytes. 

            Para evitar números tan difíciles de manejar, la gente a menudo ha reutilizado los prefijos SI para que signifiquen la potencia de dos más cercana, por ejemplo, usando el prefijo kilo para 2^10 = 1.024, mega para 2^20 = 1.048.576 y giga para 2^30 = 1.073.741.824, etc. 

            Por ejemplo, un chip de memoria de acceso aleatorio con una capacidad de 228 bytes se denominaría chip de 256 megabytes. 

            k   kilo    10^3   = 1.000^1   2^10 = 1.024^1     2.40%

            M   mega    10^6   = 1.000^2   2^20 = 1.024^2     4.86%

            G   giga    10^9   = 1.000^3   2^30 = 1.024^3     7.37%

            T   tera    10^12 = 1.000^4    2^40 = 1.024^4     9.95%

            P   peta    1015 = 1.000^5    2^50 = 1.024^5     12.59%

            E   exa     10^18 = 1.000^6    2^60 = 1.024^6     15.29%

            Z   zetta   10^21 = 1.000^7    2^70 = 1.024^7     18.06%

            Y   yotta   10^24 = 1.000^8    2^80 = 1.024^8     20.89%

            R   ronna   10^27 = 1.000^9    2^90 = 1.024^9     23.79%

            Q   quetta  10^30 = 1.000^10   2^100 = 1.024^10   26.77% 

            En el pasado, se usaba la K mayúscula en lugar de la k minúscula para indicar 1024 en lugar de 1000. 

            Sin embargo, este uso nunca se aplicó de manera consistente.

            Por otro lado, para los sistemas de almacenamiento externo (como los discos ópticos), se suelen utilizar los prefijos SI con sus valores decimales (potencias de 10). 

            Muchos intentos han buscado resolver la confusión proporcionando notaciones alternativas para múltiplos de potencia de dos. 


            En 1998, la Comisión Electrotécnica Internacional (IEC) emitió un estándar para este propósito definiendo una serie de prefijos binarios que utilizan 1024 en lugar de 1000 como base principal.

            Ki  kibi, binary kilo   1 kibibyte (KiB)    2^10 bytes   1024 B

            Mi  mebi, binary mega   1 mebibyte (MiB)    2^20 bytes   1024 KiB

            Gi  gibi, binary giga   1 gibibyte (GiB)    2^30 bytes   1024 MiB

            Ti  tebi, binary tera   1 tebibyte (TiB)    2^40 bytes   1024 GiB

            Pi  pebi, binary peta   1 pebibyte (PiB)    2^50 bytes   1024 TiB

            Ei  exbi, binary exa    1 exbibyte (EiB)    2^60 bytes   1024 PiB 


        Ejemplos actuales y obsoletos: 

            Actuales: 

            1 bit: respuesta a una pregunta de sí/no

            1 byte: un número del 0 al 255

            90 bytes: suficiente para almacenar una línea típica de texto de un libro

            512 bytes = 0,5 KiB: el sector típico de un disco duro

            1024 bytes = 1 KiB: el tamaño de bloque clásico en los sistemas de archivos UNIX
            
            2048 bytes = 2 KiB: un sector de CD-ROM
            
            4096 bytes = 4 KiB: una página de memoria en x86 (desde Intel 80386)
            
            4 kB: Aproximadamente una página de texto de una novela
            
            120 kB: El texto de un típico libro de bolsillo.
            
            1 MiB: una imagen de mapa de bits de 1024 × 1024 píxeles con 256 colores (profundidad de color de 8 bpp)

            3 MB: una canción de tres minutos (133 kbit/s)

            650–900 MB: un CD-ROM
            
            1 GB: 114 minutos de audio con calidad de CD sin comprimir a 1,4 Mbit/s
             
            32/64/128 GB: tres tamaños comunes de unidades flash USB
             
            6 TB: el tamaño de un disco duro de 100 dólares (a principios de 2022)
            
            20 TB: unidad de disco duro más grande (a principios de 2022)
            
            100 TB: la unidad de estado sólido más grande disponible comercialmente (a principios de 2022)
            
            200 TB: la unidad de estado sólido más grande construida (predicción para mediados de 2022)
            
            1.3 ZB: Predicción del volumen de todo Internet en 2016


            Obsoletos:  

            1 bit: unibit, sniff

            2 bits: dibit, crumb, quartic digit, quad, quarter, taste, tayste, tidbit, tydbit, lick, lyck, semi-nibble, snort, nyp

            3 bits: tribit, triad, triade, tribble

            4 bits: character (on Intel 4004 – however, characters are typically 8 bits wide or larger on other processors),

            5 bits: pentad, pentade, nickel, nyckle

            6 bits: byte (in early IBM machines using BCD alphamerics), hexad, hexade, sextet
            
            7 bits: heptad, heptade
            
            8 bits: octet, commonly also called byte


    Bit: 

        El bit es la unidad de información más básica en informática y comunicaciones digitales. 

        El nombre es un acrónimo de dígito binario. 

        El bit representa un estado lógico con uno de dos valores posibles.

        Estos valores se representan más comúnmente como "1" o "0", pero también se utilizan ampliamente otras representaciones como verdadero/falso, sí/no, activado/desactivado o +/−.

        La relación entre estos valores y los estados físicos del almacenamiento o dispositivo subyacente es una cuestión de convención y se pueden utilizar diferentes asignaciones incluso dentro del mismo dispositivo o programa. 

        Puede implementarse físicamente con un dispositivo de dos estados.

        Un grupo contiguo de dígitos binarios se denomina comúnmente cadena de bits (bit string), vector de bits o matriz de bits unidimensional (o multidimensional) -bit array/bitmap-. 

        Un grupo de ocho bits se denomina byte, pero históricamente el tamaño del byte no está estrictamente definido. 

        Con frecuencia, las palabras medias, completas, dobles y cuádruples constan de un número de bytes que es una potencia baja de dos. 

        Una cadena de cuatro bits suele ser un nibble.

        En teoría de la información, un bit es la entropía de información de una variable binaria aleatoria que es 0 o 1 con igual probabilidad, o la información que se obtiene cuando se conoce el valor de dicha variable. 

        Como unidad de información, el bit también se conoce como Shannon, en honor a Claude E. Shannon.

        El símbolo del dígito binario es "bit", según el estándar IEC 80000-13:2008, o el carácter minúsculo "b", según el estándar IEEE 1541-2002.

        El uso de este último puede crear confusión con la "B" mayúscula, que es el símbolo estándar internacional para el byte.


        Historia: 

            La codificación de datos mediante bits discretos se utilizó en las tarjetas perforadas inventadas por Basile Bouchon y Jean-Baptiste Falcon (1732), desarrolladas por Joseph Marie Jacquard (1804) y adoptadas más tarde por Semyon Korsakov, Charles Babbage, Herman Hollerith y los primeros fabricantes de ordenadores como IBM. 

            Una variante de esa idea fue la cinta de papel perforada. 

            En todos esos sistemas, el medio (tarjeta o cinta) conceptualmente llevaba una serie de posiciones de agujeros; cada posición podría perforarse o no, transportando así un bit de información. 

            La codificación de texto por bits también se utilizó en el código Morse (1844) y en las primeras máquinas de comunicaciones digitales, como los teletipos y las máquinas de teletipo (1870).

            Ralph Hartley sugirió el uso de una medida de información logarítmica en 1928.

            Claude E. Shannon utilizó por primera vez la palabra "bit" en su artículo fundamental de 1948 "Una teoría matemática de la comunicación". 

            Atribuyó su origen a John W. Tukey, quien había escrito un memorando de los Laboratorios Bell el 9 de enero de 1947 en el que contraía "dígito de información binaria" para simplemente "bit.


        Representación física:

            Un bit puede ser almacenado por un dispositivo digital u otro sistema físico que exista en cualquiera de dos posibles estados distintos. 

            Estos pueden ser los dos estados estables de un flip-flop, dos posiciones de un interruptor eléctrico, dos niveles distintos de voltaje o corriente permitidos por un circuito, dos niveles distintos de intensidad de luz, dos direcciones de magnetización o polarización, la orientación de dobles reversibles ADN trenzado, etc.

            Los bits se pueden implementar de varias formas. 

            En la mayoría de los dispositivos informáticos modernos, un bit suele estar representado por un voltaje eléctrico o un pulso de corriente, o por el estado eléctrico de un circuito biestable (flip-flop).

            Para dispositivos que usan lógica positiva, un valor de dígito de 1 (o un valor lógico de verdadero) se representa mediante un voltaje más positivo en relación con la representación de 0.

            Diferentes familias lógicas requieren diferentes voltajes y se permiten variaciones para tener en cuenta el envejecimiento de los componentes y inmunidad al ruido. 

            Por ejemplo, en lógica transistor-transistor (TTL) y circuitos compatibles, los valores de dígitos 0 y 1 en la salida de un dispositivo están representados por no más de 0,4 voltios ni menos de 2,6 voltios, respectivamente; mientras que las entradas TTL están especificadas para reconocer 0,8 voltios o menos como 0 y 2,2 voltios o más como 1.


        Transmisión y procesamiento

            Los bits se transmiten uno a la vez en la transmisión en serie y mediante un número múltiple de bits en la transmisión en paralelo.

            Una operación bit a bit (bitwise operation) procesa opcionalmente los bits uno a la vez. 

            Las velocidades de transferencia de datos generalmente se miden en múltiplos SI decimales de la unidad bit por segundo (bit/s), como kbit/s.


        Almacenamiento

            En los primeros dispositivos de procesamiento de información no electrónicos, como el telar de Jacquard o la máquina analítica de Babbage, un bit a menudo se almacenaba como la posición de una palanca o engranaje mecánico, o la presencia o ausencia de un agujero en un punto específico de una tarjeta de papel o cinta. 

            Los primeros dispositivos eléctricos para lógica discreta (como los circuitos de control de ascensores y semáforos, interruptores telefónicos y la computadora de Konrad Zuse) representaban bits como los estados de relés eléctricos que podían estar "abiertos" o "cerrados". 

            Cuando los relés fueron reemplazados por tubos de vacío, a partir de la década de 1940, los fabricantes de computadoras experimentaron con una variedad de métodos de almacenamiento, como pulsos de presión que viajaban a lo largo de una línea de retardo de mercurio, cargas almacenadas en la superficie interior de un tubo de rayos catódicos o puntos opacos, impreso en discos de vidrio mediante técnicas fotolitográficas.

            En las décadas de 1950 y 1960, estos métodos fueron reemplazados en gran medida por dispositivos de almacenamiento magnético, como memorias de núcleo magnético, cintas magnéticas, tambores y discos, donde un bit estaba representado por la polaridad de magnetización de un área determinada de una película ferromagnética, o por un cambio de polaridad de una dirección a la otra. 

            El mismo principio se utilizó más tarde en la memoria de burbuja magnética desarrollada en la década de 1980, y todavía se encuentra en varios artículos con banda magnética, como billetes de metro y algunas tarjetas de crédito.

            En la memoria de semiconductores moderna, como la memoria dinámica de acceso aleatorio (DRAM), los dos valores de un bit pueden representarse mediante dos niveles de carga eléctrica almacenados en un condensador. 

            En ciertos tipos de matrices lógicas programables y memorias de sólo lectura, un bit puede estar representado por la presencia o ausencia de una ruta conductora en un determinado punto de un circuito. 

            En los discos ópticos, un bit se codifica como la presencia o ausencia de un hoyo microscópico en una superficie reflectante. 

            En los códigos de barras unidimensionales, los bits se codifican como el grosor de líneas blancas y negras alternas.


        Unidad y símbolo

            El bit no está definido en el Sistema Internacional de Unidades (SI). 

            Sin embargo, la Comisión Electrotécnica Internacional emitió la norma IEC 60027, que especifica que el símbolo del dígito binario debe ser "bit", y debe usarse en todos los múltiplos, como "kbit", para kilobit. 

            Sin embargo, la letra minúscula 'b' también se usa ampliamente y fue recomendada por el estándar IEEE 1541 (2002). 

            Por el contrario, la letra mayúscula 'B' es el símbolo estándar y habitual de byte.


        Varios bits

            Se pueden expresar y representar múltiples bits de varias maneras.

            Por conveniencia de representar grupos de bits que se repiten comúnmente en la tecnología de la información, tradicionalmente se han utilizado varias unidades de información. 

            El más común es el byte unitario, acuñado por Werner Buchholz en junio de 1956, que históricamente se utilizó para representar el grupo de bits utilizados para codificar un solo carácter de texto (hasta que tomó el relevo la codificación multibyte UTF-8) en una computadora y para ello razón por la que se utilizó como elemento direccionable básico en muchas arquitecturas de computadoras. 

            La tendencia en el diseño de hardware convergió en la implementación más común de utilizar ocho bits por byte, como se usa ampliamente en la actualidad. Sin embargo, debido a la ambigüedad de depender del diseño del hardware subyacente, el octeto unitario se definió para denotar explícitamente una secuencia de ocho bits.

            Las computadoras suelen manipular bits en grupos de un tamaño fijo, llamados convencionalmente "words". 

            Al igual que el byte, el número de bits de una palabra también varía según el diseño del hardware y suele oscilar entre 8 y 80 bits, o incluso más en algunas computadoras especializadas. 

            En el siglo XXI, las computadoras personales o de servidor minoristas tienen un tamaño de palabra de 32 o 64 bits.

            El Sistema Internacional de Unidades define una serie de prefijos decimales para múltiplos de unidades estandarizadas que también se utilizan comúnmente con el bit y el byte. 

            Los prefijos kilo (10^3) a yotta (102^4) se incrementan en múltiplos de mil, y las unidades correspondientes son del kilobit (kbit) al yottabit (Ybit).


        Capacidad de información y compresión de información.

            Cuando la capacidad de información de un sistema de almacenamiento o de un canal de comunicación se presenta en bits o bits por segundo, esto suele referirse a dígitos binarios (bit), que es una capacidad del hardware de una computadora para almacenar datos binarios (0 o 1, arriba o abajo, actuales o no, etc.)

            La capacidad de información de un sistema de almacenamiento es sólo un límite superior a la cantidad de información almacenada en él. 

            Si los dos valores posibles de un bit de almacenamiento no son igualmente probables, ese bit de almacenamiento contiene menos de un bit de información. 

            Si el valor es completamente predecible, entonces la lectura de ese valor no proporciona ninguna información (bits entrópicos cero, porque no se produce ninguna resolución de la incertidumbre y, por lo tanto, no hay información disponible). 

            Si un archivo de computadora que utiliza n bits de almacenamiento contiene sólo m < n bits de información, entonces esa información, en principio, puede codificarse en aproximadamente m bits, al menos en promedio.

            Este principio es la base de la tecnología de compresión de datos.

            Usando una analogía, los dígitos binarios del hardware se refieren a la cantidad de espacio de almacenamiento disponible (como la cantidad de cubos disponibles para almacenar cosas) y el contenido de información del relleno, que viene en diferentes niveles de granularidad (fino o grueso, es decir, información comprimida o sin comprimir). 

            Cuando la granularidad es más fina (cuando la información está más comprimida), el mismo depósito puede contener más.


        Computación basada en bits

            Ciertas instrucciones de procesador de computadora bit a bit (como el conjunto de bits) operan al nivel de manipulación de bits en lugar de manipular datos interpretados como un agregado de bits.

            En la década de 1980, cuando las pantallas de computadora con mapas de bits se hicieron populares, algunas computadoras proporcionaban instrucciones especializadas de transferencia de bloques de bits para configurar o copiar los bits que correspondían a un área rectangular determinada en la pantalla.

            En la mayoría de las computadoras y lenguajes de programación, cuando se hace referencia a un bit dentro de un grupo de bits, como un byte o una palabra, generalmente se especifica mediante un número de 0 en adelante correspondiente a su posición dentro del byte o palabra. 

            Sin embargo, 0 puede referirse al bit más o menos significativo según el contexto.


    Byte: 

        El byte es una unidad de información digital que normalmente consta de ocho bits. 

        Históricamente, el byte era el número de bits utilizados para codificar un solo carácter de texto en una computadora y, por esta razón, es la unidad de memoria direccionable más pequeña en muchas arquitecturas de computadora.

        Para eliminar la ambigüedad de los bytes de tamaño arbitrario de la definición común de 8 bits, los documentos de protocolo de red como el Protocolo de Internet (RFC 791) se refieren a un byte de 8 bits como octeto. 

        Los bits de un octeto generalmente se cuentan con una numeración del 0 al 7 o del 7 al 0, dependiendo del endianidad de los bits.

        Históricamente, el tamaño del byte ha dependido del hardware y no existían estándares definitivos que exigieran el tamaño. 

        Se han utilizado tamaños de 1 a 48 bits. 

        El código de caracteres de seis bits era una implementación de uso frecuente en los primeros sistemas de codificación, y las computadoras que usaban bytes de seis y nueve bits eran comunes en la década de 1960. 

        Estos sistemas a menudo tenían palabras de memoria de 12, 18, 24, 30, 36, 48 o 60 bits, correspondientes a 2, 3, 4, 5, 6, 8 o 10 bytes de seis bits. 

        En esta era, las agrupaciones de bits en el flujo de instrucciones a menudo se denominaban sílabas o slab, antes de que el término byte se volviera común.

        El moderno estándar de facto de ocho bits, como se documenta en ISO/IEC 2382-1:1993, es una conveniente potencia de dos que permite valores codificados en binario del 0 al 255 para un byte, ya que 2 elevado a 8 es 256. 

        La norma internacional IEC 80000-13 codificó este significado común. 

        Muchos tipos de aplicaciones utilizan información representable en ocho o menos bits y los diseñadores de procesadores suelen optimizar para este uso. 

        La popularidad de las principales arquitecturas informáticas comerciales ha contribuido a la aceptación ubicua del byte de 8 bits.

        Las arquitecturas modernas suelen utilizar palabras de 32 o 64 bits, compuestas por cuatro u ocho bytes, respectivamente.

        El símbolo de unidad del byte fue designado como la letra B mayúscula por la Comisión Electrotécnica Internacional (IEC) y el Instituto de Ingenieros Eléctricos y Electrónicos (IEEE). 

        A nivel internacional, el octeto unitario, símbolo o, define explícitamente una secuencia de ocho bits, eliminando la posible ambigüedad del término "byte".


        Multiples sistemas: 

            Existe más de un sistema para definir múltiplos de unidades según el byte.

            Algunos sistemas se basan en potencias de 10, siguiendo el Sistema Internacional de Unidades (SI), que define por ejemplo el prefijo kilo como 1000 (10^3); otros sistemas se basan en potencias de 2. 

            La nomenclatura de estos sistemas es confusa. 

            Los sistemas basados en potencias de 10 utilizan prefijos estándar del SI (kilo, mega, giga,...) y sus correspondientes símbolos (k, M, G,...). Los sistemas basados en potencias de 2, sin embargo, pueden utilizar prefijos binarios (kibi, mebi, gibi, ...) y sus símbolos correspondientes (Ki, Mi, Gi, ...) o pueden utilizar los prefijos K, M y G, creando ambigüedad cuando se utilizan los prefijos M o G.

            Si bien la diferencia entre las interpretaciones decimal y binaria es relativamente pequeña para el kilobyte (aproximadamente un 2% más pequeño que el kibibyte), los sistemas se desvían cada vez más a medida que las unidades crecen (la desviación relativa crece un 2,4% por cada tres órdenes de magnitud). 

            Por ejemplo, un terabyte basado en una potencia de 10 es aproximadamente un 9 % más pequeño que un tebibyte basado en una potencia de 2.


        Unidades basadas en potencias de 10:

            La Comisión Electrotécnica Internacional (IEC) recomienda la definición de prefijos utilizando potencias de 10, en la que 1 kilobyte (símbolo kB) se define como igual a 1.000 bytes. 

            El estándar IEC define ocho de estos múltiplos, hasta 1 yottabyte (YB), equivalente a 1000^8 bytes. 

            Los prefijos adicionales ronna- para 1000^9 y quetta- para 1000^10 fueron adoptados por la Oficina Internacional de Pesas y Medidas (BIPM) en 2022.

            Esta definición se usa más comúnmente para unidades de velocidad de datos en redes de computadoras, bus interno, velocidades de transferencia de discos duros y medios flash, y para las capacidades de la mayoría de los medios de almacenamiento, particularmente discos duros, almacenamiento basado en flash y DVD.

            Los sistemas operativos que utilizan esta definición incluyen macOS, iOS, Ubuntu y Debian. 

            También es coherente con otros usos de los prefijos SI en informática, como velocidades de reloj de CPU o medidas de rendimiento.


        Unidades basadas en potencias de 2

            Un sistema de unidades basado en potencias de 2 en el que 1 kibibyte (KiB) es igual a 1.024 (es decir, 2^10) bytes está definido por la norma internacional IEC 80000-13 y está respaldado por organismos de normalización nacionales e internacionales (BIPM, IEC, NIST ). 

            El estándar IEC define ocho de estos múltiplos, hasta 1 yobibyte (YiB), equivalente a 1024^8 bytes. 

            Las contrapartes binarias naturales de ronna- y quetta- se dieron en un documento de consulta del Comité Consultivo de Unidades (CCU) del Comité Internacional de Pesas y Medidas como robi- (Ri, 1024^9) y quebi- (Qi, 1024^10), pero aún no han sido adoptados por IEC e ISO.

            Un sistema alternativo de nomenclatura para las mismas unidades (denominado aquí convención habitual), en el que 1 kilobyte (KB) equivale a 1.024 bytes, 1 megabyte (MB) equivale a 1.024^2 bytes y 1 gigabyte (GB) equivale a a 1024^3 bytes se menciona en un estándar JEDEC de la década de 1990. 

            El estándar JEDEC solo menciona los primeros tres múltiplos (hasta GB), que no menciona TB y mayores. 

            Aunque confusa e incorrecta, la convención habitual es utilizada por el sistema operativo Microsoft Windows y la capacidad de la memoria de acceso aleatorio, como la memoria principal y el tamaño de la caché de la CPU, y en marketing y facturación por parte de empresas de telecomunicaciones, como Vodafone, AT&T, Orange y Telstra. 

            Para la capacidad de almacenamiento, macOS e iOS utilizaron la convención habitual hasta Mac OS X 10.6 Snow Leopard e iOS 10, después de lo cual cambiaron a unidades basadas en potencias de 10.


        Origen del conflicto: 

            La memoria de las computadoras contemporáneas tiene una arquitectura binaria, lo que hace que una definición de unidades de memoria basada en potencias de 2 sea lo más práctico. 

            El uso del prefijo métrico kilo para múltiplos binarios surgió por conveniencia, porque 1.024 es aproximadamente 1.000.

            Esta definición fue popular en las primeras décadas de la informática personal, y productos como el formato de disquete DD Tandon de 51⁄4 pulgadas (con capacidad para 368.640 bytes) se anunciaban como "360 KB", siguiendo la convención de 1.024 bytes. 

            Sin embargo, no fue universal. 

            El disquete Shugart SA-400 de 51⁄4 pulgadas contenía 109.375 bytes sin formato,[47] y se anunciaba como "110 Kbyte", utilizando la convención 1000.

            Asimismo, el disquete DEC RX01 de 8 pulgadas (1975) tenía 256.256 bytes formateados y se anunciaba como "256k".

            Otros discos se anunciaron utilizando una combinación de las dos definiciones: en particular, 3+Los discos HD de 1⁄2 pulgadas anunciados como "1,44 MB" en realidad tienen una capacidad de 1440 KiB, el equivalente a 1,47 MB o 1,41 MiB.

            En 1995, el Comité Interdivisional de Nomenclatura y Símbolos de la Unión Internacional de Química Pura y Aplicada (IUPAC) intentó resolver esta ambigüedad proponiendo un conjunto de prefijos binarios para las potencias de 1024, incluidos kibi (kilobinario), mebi (megabinario) y gibi (gigabinario).

            En diciembre de 1998, la IEC abordó estos múltiples usos y definiciones adoptando los prefijos propuestos por la IUPAC (kibi, mebi, gibi, etc.) para denotar sin ambigüedades las potencias de 1024.

            Así, un kibibyte (1 KiB) son 1024^1 bytes = 1024 bytes, un mebibyte (1 MiB) son 1024^2 bytes = 1.048.576 bytes, y así sucesivamente.


        Usos comunes: 

            Muchos lenguajes de programación definen el tipo de datos byte.

            Los lenguajes de programación C y C++ definen byte como una "unidad direccionable de almacenamiento de datos lo suficientemente grande como para contener cualquier miembro del conjunto de caracteres básico del entorno de ejecución" (cláusula 3.6 del estándar C). 

            El estándar C requiere que el tipo de datos integral unsigned char contenga al menos 256 valores diferentes y esté representado por al menos ocho bits (cláusula 5.2.4.2.1). 

            Varias implementaciones de C y C++ reservan 8, 9, 16, 32 o 36 bits para el almacenamiento de un byt.

            Además, los estándares C y C++ exigen que no haya espacios entre dos bytes. Esto significa que cada bit en la memoria es parte de un byte.

            El tipo de datos primitivo de Java, byte, se define como ocho bits.

            Es un tipo de datos con signo que contiene valores de −128 a 127.

            Los lenguajes de programación .NET, como C#, definen byte como un tipo sin signo y sbyte como un tipo de datos con signo, con valores de 0 a 255 y −128 a 127, respectivamente.

            En los sistemas de transmisión de datos, el byte se utiliza como una secuencia contigua de bits en un flujo de datos en serie, que representa la unidad de datos más pequeña distinguida. 

            Para la comunicación asíncrona, una unidad de transmisión completa normalmente incluye además un bit de inicio, 1 o 2 bits de parada y posiblemente un bit de paridad y, por tanto, su tamaño puede variar de siete a doce bits para cinco a ocho bits de datos reales. 

            Para la comunicación síncrona, la comprobación de errores suele utilizar bytes al final de un frame.


    Binary number: 

        Un número binario es un número expresado en el sistema de numeración de base 2 o sistema de numeración binario, un método de expresión matemática que utiliza sólo dos símbolos: normalmente "0" (cero) y "1" (uno).

        El sistema numérico de base 2 es una notación posicional con una base de 2. 
        
        Cada dígito se denomina bit o dígito binario. 

        Debido a su sencilla implementación en circuitos electrónicos digitales que utilizan puertas lógicas, el sistema binario es utilizado por casi todas las computadoras y dispositivos basados en computadoras modernos, como un sistema de uso preferido, sobre varias otras técnicas humanas de comunicación, debido a la simplicidad de la lenguaje y la inmunidad al ruido en la implementación física.

        Los números negativos se representan comúnmente en binario usando two's complements. 


        Representación:

            Cualquier número puede representarse mediante una secuencia de bits (dígitos binarios), que a su vez puede representarse mediante cualquier mecanismo capaz de estar en dos estados mutuamente excluyentes.

            Cualquiera de las siguientes filas de símbolos se puede interpretar como el valor numérico binario de 667

            1 0 1 0 0 1 1 0 1 1
            | - | ― ― | | - | |

            El valor numérico representado en cada caso depende del valor asignado a cada símbolo.

            En los primeros tiempos de la informática, se utilizaban interruptores, agujeros perforados y cintas de papel perforadas para representar valores binarios.

            En una computadora moderna, los valores numéricos pueden estar representados por dos voltajes diferentes; en un disco magnético, se pueden utilizar polaridades magnéticas.

            Un estado "positivo", "sí" o "encendido" no es necesariamente equivalente al valor numérico de uno; Depende de la arquitectura en uso.

            De acuerdo con la representación habitual de los números arábigos, los números binarios se escriben comúnmente utilizando los símbolos 0 y 1. 

            Cuando se escriben, los números binarios suelen tener subíndices, prefijos o sufijos para indicar su base o base.

            Las siguientes notaciones son equivalentes:

                100101 binario (declaración explícita de formato)
                
                100101b (un sufijo que indica formato binario; también conocido como convención Intel)
                 
                00101B (un sufijo que indica formato binario)
                 
                bin 100101 (un prefijo que indica formato binario)
                
                100101_2 (un subíndice que indica notación base 2 (binaria))
                
                %100101 (un prefijo que indica formato binario; también conocido como convención de Motorola[33][34])
                
                0b100101 (un prefijo que indica formato binario, común en lenguajes de programación)
                
                6b100101 (un prefijo que indica el número de bits en formato binario, común en los lenguajes de programación)
                
                #b100101 (un prefijo que indica formato binario, común en los lenguajes de programación Lisp)


            Cuando se hablan, los números binarios generalmente se leen dígito por dígito para distinguirlos de los números decimales. 

            Por ejemplo, el número binario 100 se pronuncia uno cero cero, en lugar de cien, para hacer explícita su naturaleza binaria y con fines de corrección. 

            Dado que el número binario 100 representa el valor cuatro, sería confuso referirse al número como cien (una palabra que representa un valor o cantidad completamente diferente).

            Alternativamente, el número binario 100 se puede leer como "cuatro" (el valor correcto), pero esto no hace explícita su naturaleza binaria.


        Conteo en binario: 

            Contar en binario es similar a contar en cualquier otro sistema numérico. 

            Comenzando con un solo dígito, el conteo continúa a través de cada símbolo, en orden creciente. 

            Antes de examinar el conteo binario, es útil analizar brevemente el sistema de conteo decimal, más familiar, como marco de referencia.


            Conteo decimal:

            El conteo decimal utiliza los diez símbolos del 0 al 9. 

            El conteo comienza con la sustitución incremental del dígito menos significativo (el dígito más a la derecha), que a menudo se denomina primer dígito. 

            Cuando se agotan los símbolos disponibles para esta posición, el dígito menos significativo se restablece a 0 y el siguiente dígito de mayor significado (una posición a la izquierda) se incrementa (desbordamiento) y se reanuda la sustitución incremental del dígito de orden inferior. 

            Este método de reinicio y desbordamiento se repite para cada dígito de importancia. 

            El conteo avanza de la siguiente manera:

                 000, 001, 002, ... 007, 008, 009 (el dígito más a la derecha se restablece a cero y el dígito a su izquierda se incrementa)
                 010, 011, 012, ...
                    ...
                 090, 091, 092, ... 097, 098, 099 (los dos dígitos más a la derecha se restablecen a cero y el siguiente dígito se incrementa)
                 100, 101, 102, ...


            El conteo binario sigue exactamente el mismo procedimiento y nuevamente la sustitución incremental comienza con el dígito o bit binario menos significativo (el que está más a la derecha, también llamado primer bit), excepto que solo los dos símbolos 0 y 1 están disponibles. 

            Por lo tanto, después de que un bit llega a 1 en binario, un incremento lo restablece a 0 pero también provoca un incremento del siguiente bit a la izquierda:

                 0000,
                 0001, (el bit más a la derecha comienza de nuevo y se incrementa el siguiente bit)
                 0010, 0011 (los dos bits más a la derecha comienzan de nuevo y el siguiente bit se incrementa)
                 0100, 0101, 0110, 0111 (los tres bits más a la derecha comienzan de nuevo y el siguiente bit se incrementa)
                 1000, 1001, 1010, 1011, 1100, 1101, 1110, 1111...

            En el sistema binario, cada bit representa una potencia creciente de 2, donde el bit más a la derecha representa 2^0, el siguiente representa 2^1, luego 2^2 y así sucesivamente.

            El valor de un número binario es la suma de las potencias de 2 representadas por cada bit "1". 

            Por ejemplo, el número binario 100101 se convierte a formato decimal de la siguiente manera:

                 100101_2 = [ ( 1 ) × 2^5 ] + [ ( 0 ) × 2^4 ] + [ ( 0 ) × 2^3 ] + [ ( 1 ) × 2^2 ] + [ ( 0 ) × 2^1 ] + [ ( 1 ) × 2^0 ]

                 100101_2 = [1 × 32] + [0 × 16] + [0 × 8] + [1 × 4] + [0 × 2] + [1 × 1]

                 100101_2 = 37_10


    Bitwise/operación bit a bit:

        Aunque no están directamente relacionados con la interpretación numérica de los símbolos binarios, las secuencias de bits pueden manipularse utilizando operadores lógicos booleanos.

        Cuando una cadena de símbolos binarios se manipula de esta manera, se denomina operación bit a bit; los operadores lógicos AND, OR y XOR se pueden realizar en los bits correspondientes en dos números binarios proporcionados como entrada.

        La operación lógica NOT se puede realizar en bits individuales en un único número binario proporcionado como entrada. 

        A veces, estas operaciones pueden utilizarse como atajos aritméticos y también pueden tener otros beneficios computacionales. 

        Por ejemplo, un desplazamiento aritmético hacia la izquierda de un número binario es equivalente a la multiplicación por una potencia (positiva, integral) de 2.


    Two's complement: 

        El complemento a dos es el método más común para representar números enteros con signo (positivos, negativos y cero) en computadoras y, más generalmente, valores binarios de punto fijo. 

        El complemento a dos utiliza el dígito binario con el mayor valor posicional como signo para indicar si el número binario es positivo o negativo. 

        Cuando el bit más significativo es 1, el número tiene signo negativo; y cuando el bit más significativo es 0 el número tiene signo positivo.

        A diferencia del esquema de complemento a uno, el esquema de complemento a dos tiene una sola representación para el cero. 

        Además, las implementaciones aritméticas se pueden utilizar tanto en enteros con signo como sin signo y difieren sólo en las situaciones de desbordamiento de enteros.


        Enteros con signo/signed number: 

            En informática, se requieren representaciones de números con signo para codificar números negativos en sistemas numéricos binarios.

            En matemáticas, los números negativos en cualquier base se representan precediéndolos con un signo menos ("-"). 

            Sin embargo, en los registros de RAM o CPU, los números se representan sólo como secuencias de bits, sin símbolos adicionales. 

            Los cuatro métodos más conocidos para extender el sistema de numeración binaria para representar números con signo son: signo-magnitud, complemento a uno, complemento a dos y binario compensado.

            Algunos de los métodos alternativos utilizan signos implícitos en lugar de explícitos, como el binario negativo, que utiliza la base −2. 

            Se pueden idear métodos correspondientes para otras bases, ya sean elaboraciones positivas, negativas, fraccionarias u otras elaboraciones sobre dichos temas.

            No existe un criterio definitivo por el cual alguna de las representaciones sea universalmente superior.

            Para los números enteros, la representación utilizada en la mayoría de los dispositivos informáticos actuales es el complemento a dos, aunque los mainframes de la serie Unisys ClearPath Dorado utilizan el complemento a uno.


        Binario punto fijo/fixed number binary

            En informática, el punto fijo es un método para representar números fraccionarios (no enteros) almacenando un número fijo de dígitos de su parte fraccionaria.

            Las cantidades en dólares, por ejemplo, a menudo se almacenan con exactamente dos dígitos fraccionarios, que representan los centavos (1/100 de dólar). 

            De manera más general, el término puede referirse a la representación de valores fraccionarios como múltiplos enteros de alguna unidad pequeña fija, p. una cantidad fraccionaria de horas como un múltiplo entero de intervalos de diez minutos. 

            La representación de números en punto fijo a menudo se contrasta con la representación en punto flotante, más complicada y exigente desde el punto de vista computacional.

            En la representación de punto fijo, la fracción a menudo se expresa en la misma base numérica que la parte entera, pero usando potencias negativas de la base b.

            Las variantes más comunes son decimal (base 10) y binaria (base 2).

            Este último también se conoce comúnmente como escalado binario. 

            Por lo tanto, si se almacenan n dígitos de fracción, el valor siempre será un múltiplo entero de b^−n. 

            La representación de punto fijo también se puede utilizar para omitir los dígitos de orden inferior de valores enteros, p. al representar grandes valores en dólares como múltiplos de $1000.

            Cuando se muestran números decimales de coma fija para lectura humana, los dígitos de fracción generalmente están separados de los de la parte entera por un carácter de base (generalmente '.' en inglés, pero ',' o algún otro símbolo en muchos otros idiomas).

            Internamente, sin embargo, no hay separación y la distinción entre los dos grupos de dígitos está definida únicamente por los programas que manejan dichos números.

            La representación de punto fijo era la norma en las calculadoras mecánicas. 

            Dado que la mayoría de los procesadores modernos tienen una unidad de punto flotante (FPU) rápida, las representaciones de punto fijo en implementaciones basadas en procesadores ahora se utilizan sólo en situaciones especiales, como en microprocesadores y microcontroladores integrados de bajo costo; en aplicaciones que exigen alta velocidad o bajo consumo de energía o área de chip pequeña, como procesamiento de imágenes, video y señales digitales; o cuando su uso sea más natural para el problema. 

            Ejemplos de esto último son la contabilidad de cantidades en dólares, cuando las fracciones de centavos deben redondearse a centavos enteros de maneras estrictamente prescritas; y la evaluación de funciones mediante búsqueda de tablas, o cualquier aplicación donde los números racionales deban representarse sin errores de redondeo (lo que hace el punto fijo, pero no el punto flotante). 

            La representación de punto fijo sigue siendo la norma para las implementaciones de matrices de puertas programables en campo (FPGA), ya que el soporte de punto flotante en una FPGA requiere muchos más recursos que el soporte de punto fijo.



        FPU: 

            Una unidad de punto flotante (FPU, coloquialmente un coprocesador matemático) es una parte de un sistema informático especialmente diseñado para realizar operaciones con números de punto flotante. 

            Las operaciones típicas son suma, resta, multiplicación, división y raíz cuadrada. 

            Algunas FPU también pueden realizar varias funciones trascendentales, como cálculos exponenciales o trigonométricos, pero la precisión puede ser baja, por lo que algunos sistemas prefieren calcular estas funciones en software.

            En arquitecturas informáticas de propósito general, se pueden integrar una o más FPU como unidades de ejecución dentro de la unidad central de procesamiento; sin embargo, muchos procesadores integrados no tienen soporte de hardware para operaciones de punto flotante (aunque cada vez más las tienen como estándar).

            Cuando una CPU está ejecutando un programa que requiere una operación de punto flotante, existen tres formas de realizarlo:

                 Un emulador de unidad de punto flotante (una biblioteca de punto flotante en software)
                 
                 Hardware FPU adicional
                 
                 FPU integrada (en hardware)


        FPGA:

            Una matriz de puertas programables en campo (FPGA) es un tipo de circuito integrado configurable que se puede programar o reprogramar después de la fabricación. 

            Los FPGA son parte de un conjunto más amplio de dispositivos lógicos denominados dispositivos lógicos programables (PLD). 

            Consisten en una serie de bloques lógicos programables e interconexiones que se pueden configurar para realizar diversas funciones digitales. 

            Los FPGA se utilizan comúnmente en aplicaciones donde se requieren flexibilidad, velocidad y capacidades de procesamiento paralelo, como en los sectores de telecomunicaciones, automoción, aeroespacial e industrial.

            La configuración de FPGA generalmente se especifica mediante un lenguaje de descripción de hardware (HDL), similar al utilizado para un circuito integrado de aplicación específica (ASIC). 

            Anteriormente se utilizaban diagramas de circuitos para especificar la configuración.

            Los bloques lógicos de una FPGA se pueden configurar para realizar funciones combinacionales complejas o actuar como puertas lógicas simples como AND y XOR. 

            En la mayoría de los FPGA, los bloques lógicos también incluyen elementos de memoria, que pueden ser simples flip-flops o bloques de memoria más completos.

            Muchos FPGA se pueden reprogramar para implementar diferentes funciones lógicas, lo que permite una computación flexible y reconfigurable como la que se realiza en el software de computadora.

            Los FPGA también desempeñan un papel en el desarrollo de sistemas integrados debido a su capacidad para iniciar el desarrollo del software del sistema simultáneamente con el hardware, permitir simulaciones de rendimiento del sistema en una fase muy temprana del desarrollo y permitir varias pruebas del sistema e iteraciones de diseño antes de finalizar la arquitectura del sistema.

            Los FPGA también se utilizan comúnmente durante el desarrollo de ASIC para acelerar el proceso de simulación.


    Sistema numerico:

        Un sistema de numeración es un conjunto de símbolos y reglas de generación que permiten construir todos los números válidos. Un sistema de numeración puede obtenerse como:

            N = (S,R)

        donde:

            N: 
                es el sistema de numeración considerado (p.ej. decimal, binario, hexadecimal, etc.).

            S: 

                es el conjunto de símbolos permitidos en el sistema. 

                En el caso del sistema decimal son {0,1,2...9}; en el binario son {0,1}; en el octal son {0,1,...7}; en el hexadecimal son {0,1,...9,A,B,C,D,E,F}.
            
            R:

                Son las reglas que nos indican qué números y qué operaciones son válidos en el sistema, y cuáles no.

                En un sistema de numeración posicional las reglas son bastante simples, mientras que la numeración romana requiere reglas algo más elaboradas.

        Estas reglas son diferentes para cada sistema de numeración considerado, pero una regla común a todos es que para construir números válidos en un sistema de numeración determinado solo se pueden utilizar los símbolos permitidos en ese sistema.

        Para indicar en qué sistema de numeración se representa con una letra que se añade como subíndice a la derecha el número de símbolos que se pueden representar en dicho sistema.

        Se conoce como un sistema de numeración a un conjunto finito de símbolos que se emplea con algún método para asignar numerales , o símbolos numéricos.

        Pueden clasificarse en dos grandes grupos: posicionales y no posicionales:

            En los sistemas no posicionales los dígitos tienen el valor del símbolo utilizado, que no depende de la posición (columna) que ocupan en el número.

            En los sistemas de numeración ponderados o posicionales el valor de un dígito depende tanto del símbolo utilizado, como de la posición que ese símbolo ocupa en el número


        Teorema fundamental de la numeración

            Este teorema establece la forma general de construir números en un sistema de numeración posicional. 

            Primero estableceremos unas definiciones básicas:

                N: 

                    Número válido en el sistema de numeración.


                b: 

                    Base del sistema de numeración.

                    Número de símbolos permitidos en el sistema.


                d_i:

                    un símbolo cualquiera de los permitidos en el sistema de numeración.


                n: 

                    Número de dígitos de la parte entera.

                    Coma fraccionaria. 

                    Símbolo utilizado para separar la parte entera de un número de su parte fraccionaria.

                k: 

                    Número de dígitos de la parte decimal.


            La fórmula general para construir un número N, con un número finito de decimales, en un sistema de numeración posicional de base b es la siguiente: 

                N = 
                    {

                        <d_(n-1)>...d_1, d_0, d_-1...d_-k>

                        = 

                        n-1
                        Z   d_i b^i
                        i=-k

                        N = d_n-1 b^n-1 + ... + d_1 b^1 + d_0 b^0 + d_-1 b^-1 + ... + d_-k b^-k

                    }


            El valor total del número será la suma de cada dígito multiplicado por la potencia de la base correspondiente a la posición que ocupa en el número.

            Esta representación posibilita la realización de sencillos algoritmos para la ejecución de operaciones aritméticas. 


        En informática, las bases binaria (base-2), octal (base-8) y hexadecimal (base-16) son las más utilizadas. 

        Las computadoras, en el nivel más básico, trabajan sólo con secuencias de ceros y unos convencionales, por lo que en este sentido es más fácil trabajar con potencias de dos. 

        El sistema hexadecimal se utiliza como "taquigrafía" del binario: cada 4 dígitos binarios (bits) se relacionan con uno y sólo un dígito hexadecimal. 

        En hexadecimal, los seis dígitos después del 9 se indican con A, B, C, D, E y F (y, a veces, a, b, c, d, e y f).

        El sistema de numeración octal también se utiliza como otra forma de representar números binarios. 

        En este caso la base es 8 y por tanto sólo se utilizan los dígitos 0, 1, 2, 3, 4, 5, 6 y 7. 

        Al convertir de binario a octal, cada 3 bits se relacionan con un solo dígito octal.

        Se han utilizado bases hexadecimales, decimales, octales y una amplia variedad de otras para codificación de binario a texto, implementaciones de aritmética de precisión arbitraria y otras aplicaciones.


    Notación posicional:

        La notación posicional (o notación de valor posicional, o sistema numérico posicional) generalmente denota la extensión a cualquier base del sistema numérico hindú-árabe (o sistema decimal). 

        De manera más general, un sistema posicional es un sistema numérico en el que la contribución de un dígito al valor de un número es el valor del dígito multiplicado por un factor determinado por la posición del dígito. 

        En los primeros sistemas de numeración, como los números romanos, un dígito tenía un solo valor: I significa uno, X significa diez y C cien (sin embargo, el valor puede negarse si se coloca antes de otro dígito). 

        En los sistemas posicionales modernos, como el sistema decimal, la posición del dígito significa que su valor debe multiplicarse por algún valor: en 555, los tres símbolos idénticos representan cinco centenas, cinco decenas y cinco unidades, respectivamente, debido a su diferentes posiciones en la cadena de dígitos.

        Hoy en día, el sistema de numeración hindú-árabe (base diez) es el sistema más utilizado a nivel mundial. Sin embargo, el sistema de numeración binaria (base dos) se utiliza en casi todas las computadoras y dispositivos electrónicos porque es más fácil de implementar de manera eficiente en circuitos electrónicos.

        El uso de un punto de base (punto decimal en base diez), se extiende para incluir fracciones y permite representar cualquier número real con precisión arbitraria. 

        Con la notación posicional, los cálculos aritméticos son mucho más sencillos que con cualquier sistema numérico antiguo.

        Base: 

            Cantidad de simbolos en un sistema numerico posicional. 

            Se incluye el 0. 


        Indice:

            Posición al que pertenece un simbolo o cifra. 

            Generalmente, en un sistema numerico posicional se empieza el simbolo más a la derecha, al que se le asigna 0 y va incrementando. 


        Notación:

            Al describir la base en notación matemática, la letra b se usa generalmente como símbolo para este concepto, por lo que, para un sistema binario, b es igual a 2.

            Otra forma común de expresar la base es escribirla como un subíndice decimal después del número que es siendo representado (esta notación se utiliza en este artículo). 

            1111011_2 implica que el número 1111011 es un número de base 2, igual a 123_10 (una representación de notación decimal), 173_8 (octal) y 7B_16 (hexadecimal). 

            En libros y artículos, cuando se utilizan inicialmente abreviaturas escritas de bases numéricas, la base no se imprime posteriormente: se supone que el binario 1111011 es lo mismo que 1111011_2.

            La base b también puede indicarse mediante la frase "base-b". 

            Entonces los números binarios son "base-2"; los números octales son "base 8"; los números decimales son "base-10"; etcétera.

            Para una base b dada, el conjunto de dígitos {0, 1, ..., b−2, b−1} se denomina conjunto estándar de dígitos. 

            Así, los números binarios tienen dígitos {0, 1}; los números decimales tienen dígitos {0, 1, 2, ..., 8, 9}; etcétera. Por lo tanto, los siguientes son errores de notación: 52_2, 2_2, 1A_9. 

            (En todos los casos, uno o más dígitos no están en el conjunto de dígitos permitidos para la base dada). 


        Exponenciacion: 

            Los sistemas de numeración posicional funcionan utilizando la exponenciación de la base. 

            El valor de un dígito es el dígito multiplicado por el valor de su lugar.

            Los valores posicionales son el número de la base elevado a la enésima potencia, donde n es el número de otros dígitos entre un dígito dado y el punto de la base. 

            Si un dígito dado está en el lado izquierdo del punto de la base (es decir, su valor es un número entero), entonces n es positivo o cero; si el dígito está en el lado derecho del punto de la base (es decir, su valor es fraccionario), entonces n es negativo.


        Digits y números: 

            Un dígito es un símbolo que se utiliza para la notación posicional y un número consta de uno o más dígitos que se utilizan para representar un número con notación posicional. 

            Los dígitos más comunes en la actualidad son los dígitos decimales "0", "1", "2", "3", "4", "5", "6", "7", "8" y "9". 

            La distinción entre un dígito y un número es más pronunciada en el contexto de una base numérica.

            Un número distinto de cero con más de una posición de dígito significará un número diferente en una base numérica diferente, pero en general, los dígitos significarán lo mismo.

            Por ejemplo, el número de base 8 23_8 contiene dos dígitos, "2" y "3", y con un número de base (subíndice) "8". 

            Cuando se convierte a base 10, 23_8 equivale a 19_10, es decir, 23_8 = 19_10. En nuestra notación aquí, el subíndice "8" del número 238 es parte del número, pero puede que no siempre sea así.

            Imagine que el número "23" tiene un número base ambiguo. 

            Entonces "23" probablemente podría ser cualquier base, desde la base 4 hacia arriba. 

            En base 4, el "23" significa 1110, es decir, 234 = 1110. En base 60, el "23" significa el número 123_10, es decir, 23_60 = 123_10. 

            El número "23", entonces, en este caso, corresponde al conjunto de números de base 10 {11, 13, 15, 17, 19, 21, 23, ..., 121, 123} mientras que sus dígitos "2" y "3" siempre conservan su significado original: el "2" significa "dos de", y el "3" significa "tres de".


        Punto de base/Radix point: 

            La notación se puede extender a los exponentes negativos de la base b.

            Por lo tanto, el llamado punto de base, generalmente ».«, se utiliza como separador de las posiciones con exponente no negativo de aquellas con exponente negativo.

            Los números que no son enteros usan lugares más allá del punto de base.

            Para cada posición detrás de este punto (y por tanto después del dígito de las unidades), el exponente n de la potencia bn disminuye en 1 y la potencia se acerca a 0. 

            Por ejemplo, el número 2,35 es igual a:

                 2 × 10^0 + 3 × 10^−1 + 5 × 10^−2

        
        Signo: 

            Si la base y todos los dígitos del conjunto de dígitos no son negativos, no se pueden expresar números negativos. Para superar esto, se añade un signo menos, aquí »-«, al sistema numérico. 

            En la notación habitual, se antepone a la cadena de dígitos que representan el número que de otro modo no sería negativo.


    Código binario: 

        Representa texto, instrucciones del procesador de una computadora o cualquier otro dato que utilice un sistema de dos símbolos. 

        El sistema de dos símbolos utilizado suele ser "0" y "1" del sistema numérico binario. 

        El código binario asigna un patrón de dígitos binarios, también conocidos como bits, a cada carácter, instrucción, etc. 

        Por ejemplo, una cadena binaria de ocho bits (que también se llama byte) puede representar cualquiera de los 256 valores posibles y puede, por lo tanto, representan una amplia variedad de artículos diferentes.

        En informática y telecomunicaciones, los códigos binarios se utilizan para diversos métodos de codificación de datos, como cadenas de caracteres, en cadenas de bits. 

        Esos métodos pueden utilizar cadenas de ancho fijo o variable. 

        En un código binario de ancho fijo, cada letra, dígito u otro carácter está representado por una cadena de bits de la misma longitud; esa cadena de bits, interpretada como un número binario, generalmente se muestra en tablas de códigos en notación octal, decimal o hexadecimal. 

        Hay muchos conjuntos de caracteres y muchas codificaciones de caracteres para ellos.

        Una cadena de bits, interpretada como un número binario, se puede traducir a un número decimal. 

        Por ejemplo, la a minúscula, si está representada por la cadena de bits 01100001 (como está en el código ASCII estándar), también se puede representar como el número decimal "97".


        ACII code:

            Es un estándar de codificación de caracteres para comunicaciones electrónicas. 

            Los códigos ASCII representan texto en computadoras, equipos de telecomunicaciones y otros dispositivos.

            Debido a las limitaciones técnicas de los sistemas informáticos en el momento de su invención, ASCII tiene sólo 128 puntos de código (), de los cuales sólo 95 son caracteres imprimibles, lo que limitó gravemente su alcance. 

            Los sistemas informáticos modernos han evolucionado para utilizar Unicode, que tiene millones de puntos de código, pero los primeros 128 de ellos son iguales al conjunto ASCII.



            The American Standard Code for Information Interchange (ASCII) utiliza un código binario de 7 bits para representar texto y otros caracteres dentro de computadoras, equipos de comunicaciones y otros dispositivos. 

            A cada letra o símbolo se le asigna un número del 0 al 127. 

            Por ejemplo, la "a" minúscula se representa por 1100001 como una cadena de bits (que es "97" en decimal).


        Unicode: 

            El estándar Unicode es un estándar de codificación de texto mantenido por Unicode Consortium diseñado para respaldar el uso de texto escrito en todos los principales sistemas de escritura del mundo. 

            La versión 15.1 del estándar define 149813 caracteres y 161 escrituras utilizadas en diversos contextos ordinarios, literarios, académicos y técnicos.

            Muchos caracteres comunes, incluidos los números, la puntuación y otros símbolos, están unificados dentro del estándar y no se tratan como específicos de ningún sistema de escritura determinado.

            Unicode codifica miles de emoji, cuyo desarrollo continuo lo lleva a cabo el Consorcio como parte del estándar. 

            Además, la adopción generalizada de Unicode fue en gran parte responsable de la popularización inicial de los emoji fuera de Japón.

            En última instancia, Unicode es capaz de codificar más de 1,1 millones de caracteres.

            Unicode ha suplantado en gran medida el entorno anterior de innumerables conjuntos de caracteres incompatibles, cada uno utilizado en diferentes configuraciones regionales y en diferentes arquitecturas informáticas. 

            Unicode se utiliza para codificar la gran mayoría del texto en Internet, incluida la mayoría de las páginas web, y el soporte relevante de Unicode se ha convertido en una consideración común en el desarrollo de software contemporáneo.

            El repertorio de caracteres Unicode está sincronizado con ISO/IEC 10646, siendo cada código idéntico entre sí. 

            Sin embargo, el estándar Unicode es más que un simple repertorio dentro del cual se asignan caracteres. 

            Para ayudar a los desarrolladores y diseñadores, el estándar también proporciona gráficos y datos de referencia, así como anexos que explican conceptos relacionados con varios scripts y brindan orientación para su implementación. 

            Los temas cubiertos por estos anexos incluyen la normalización de caracteres, la composición y descomposición de caracteres, la intercalación y la direccionalidad.

            El texto Unicode se procesa y almacena como datos binarios utilizando una de varias codificaciones, que definen cómo traducir los códigos abstractos de caracteres del estándar en secuencias de bytes.

            El propio estándar Unicode define tres codificaciones: UTF-8, UTF-16 y UTF-32, aunque existen varias otras. 

            De estos, UTF-8 es el más utilizado por un amplio margen, en parte debido a su compatibilidad con versiones anteriores de ASCII.


        Code point: 

            Un punto de código, punto de código o posición de código es una posición única en un espacio n-dimensional cuantificado a la que se le ha asignado un significado semántico.

            En otras palabras, un punto de código es una posición particular en una tabla, donde a la posición se le ha asignado un significado.

            La tabla tiene posiciones discretas (1, 2, 3, 4, pero no fracciones) y puede ser unidimensional (una columna), bidimensional (como celdas en una hoja de cálculo), tridimensional (hojas en un libro de trabajo), etc. ... en cualquier número de dimensiones.

            Los puntos de código se utilizan en una multitud de estándares formales de telecomunicaciones y procesamiento de información. 

            Por ejemplo, la Recomendación UIT-T T.35 contiene un conjunto de códigos de país para equipos de telecomunicaciones (originalmente máquinas de fax) que permiten al equipo indicar su país de fabricación u operación.

            En T.35, Argentina está representada por el punto de código 0x07, Canadá por 0x20, Gambia por 0x41, etc.



        Binary-coded decimal: 

            Es una representación codificada en binario de valores enteros que utiliza un cuarteto de 4 bits para codificar dígitos decimales. 

            Cuatro bits binarios pueden codificar hasta 16 valores distintos; pero, en números codificados en BCD, sólo diez valores en cada nibble son legales y codifican los dígitos decimales del cero al nueve. 

            Los seis valores restantes son ilegales y pueden provocar una excepción en la máquina o un comportamiento no especificado, dependiendo de la implementación informática de la aritmética BCD.

            A veces se prefiere la aritmética BCD a los formatos numéricos de punto flotante en aplicaciones comerciales y financieras donde los complejos comportamientos de redondeo de los números de punto flotante son inapropiados.


        Peso del código binario: 

            Tal como se define en la tabla de códigos de peso constante, es el peso Hamming de las palabras binarias que codifican las palabras o secuencias representadas.


        String: 

            Es tradicionalmente una secuencia de caracteres, ya sea como una constante literal o como algún tipo de variable. 

            Este último puede permitir que sus elementos sean mutados y cambiar la longitud, o puede ser fijo (después de la creación). 

            Una cadena generalmente se considera un tipo de datos y a menudo se implementa como una estructura de datos de matriz de bytes (o palabras) que almacena una secuencia de elementos, generalmente caracteres, utilizando alguna codificación de caracteres. 

            Cadena también puede denotar matrices más generales u otros tipos y estructuras de datos de secuencia (o lista).

            Dependiendo del lenguaje de programación y del tipo de datos preciso utilizado, una variable declarada como una cadena puede hacer que el almacenamiento en la memoria se asigne estáticamente para una longitud máxima predeterminada o emplear una asignación dinámica para permitirle contener un número variable de elementos.

            Cuando una cadena aparece literalmente en el código fuente, se la conoce como cadena literal o cadena anónima.

            En los lenguajes formales, que se utilizan en lógica matemática e informática teórica, una cadena es una secuencia finita de símbolos que se eligen de un conjunto llamado alfabeto.

    
        Códificación de caracter. 

            Históricamente, los tipos de datos de cadena han asignado un byte por carácter y, aunque el conjunto de caracteres exacto variaba según la región, las codificaciones de caracteres eran lo suficientemente similares como para que los programadores a menudo pudieran ignorar esto, ya que los caracteres que un programa trataba de manera especial (como el punto, el espacio y la coma) estaban en el mismo lugar en todas las codificaciones que encontraría un programa.

            Estos conjuntos de caracteres normalmente se basaban en ASCII o EBCDIC. 

            Si el texto en una codificación se mostraba en un sistema que utilizaba una codificación diferente, el texto a menudo estaba alterado, aunque a menudo era algo legible y algunos usuarios de computadoras aprendían a leer el texto alterado.

            Los lenguajes logográficos como el chino, el japonés y el coreano (conocidos colectivamente como CJK) necesitan mucho más de 256 caracteres (el límite de una codificación de un byte de 8 bits por carácter) para una representación razonable.

            Las soluciones normales implicaban mantener representaciones de un solo byte para ASCII y utilizar representaciones de dos bytes para los ideogramas CJK. 

            El uso de estos con el código existente generó problemas con la coincidencia y el corte de cadenas, cuya gravedad dependía de cómo se diseñó la codificación de caracteres. 

            Algunas codificaciones, como la familia EUC, garantizan que un valor de byte en el rango ASCII representará solo ese carácter ASCII, lo que hace que la codificación sea segura para sistemas que utilizan esos caracteres como separadores de campos. Otras codificaciones, como ISO-2022 y Shift-JIS, no ofrecen tales garantías, lo que hace que la coincidencia de códigos de bytes sea insegura. 

            Estas codificaciones tampoco eran "autosincronizadas", por lo que localizar los límites de los caracteres requería hacer una copia de seguridad hasta el inicio de una cadena, y pegar dos cadenas juntas podría provocar la corrupción de la segunda cadena.

            Unicode ha simplificado un poco el panorama. 

            La mayoría de los lenguajes de programación ahora tienen un tipo de datos para cadenas Unicode. 

            El formato de flujo de bytes preferido de Unicode, UTF-8, está diseñado para no tener los problemas descritos anteriormente para codificaciones multibyte más antiguas. 

            UTF-8, UTF-16 y UTF-32 requieren que el programador sepa que las unidades de código de tamaño fijo son diferentes de los "caracteres", la principal dificultad actualmente son las API diseñadas incorrectamente que intentan ocultar esta diferencia (UTF-32 no hace que los puntos de código tengan un tamaño fijo, pero estos no son "caracteres" debido a la composición de los códigos).


        Representación: 

            Las representaciones de cadenas dependen en gran medida de la elección del repertorio de caracteres y del método de codificación de caracteres. 

            Las implementaciones de cadenas más antiguas se diseñaron para funcionar con el repertorio y la codificación definidos por ASCII o extensiones más recientes como la serie ISO 8859. 

            Las implementaciones modernas suelen utilizar el extenso repertorio definido por Unicode junto con una variedad de codificaciones complejas como UTF-8 y UTF-16.

            El término cadena de bytes generalmente indica una cadena de bytes de propósito general, en lugar de cadenas de solo caracteres (legibles), cadenas de bits o similares. 

            Las cadenas de bytes a menudo implican que los bytes pueden tomar cualquier valor y que cualquier dato puede almacenarse tal cual, lo que significa que no debe haber ningún valor interpretado como un valor de terminación.

            La mayoría de las implementaciones de cadenas son muy similares a las matrices de longitud variable con las entradas que almacenan los códigos de caracteres de los caracteres correspondientes.

            La principal diferencia es que, con determinadas codificaciones, un único carácter lógico puede ocupar más de una entrada en la matriz. 

            Esto sucede, por ejemplo, con UTF-8, donde los códigos únicos (puntos de código UCS) pueden ocupar de uno a cuatro bytes, y los caracteres individuales pueden ocupar un número arbitrario de códigos. 

            En estos casos, la longitud lógica de la cadena (número de caracteres) difiere de la longitud física de la matriz (número de bytes en uso), UTF-32 evita la primera parte del problema


    Binary file: 

        Es un archivo de computadora que no es un archivo de texto. 

        El término "archivo binario" se utiliza a menudo como un término que significa "archivo que no es de texto". 

        Muchos formatos de archivos binarios contienen partes que pueden interpretarse como texto; por ejemplo, algunos archivos de documentos de computadora que contienen texto formateado, como los archivos de documentos más antiguos de Microsoft Word, contienen el texto del documento pero también contienen información de formato en formato binario.


        Estructura

            Generalmente se piensa que los archivos binarios son una secuencia de bytes, lo que significa que los dígitos binarios (bits) se agrupan en ochos. 

            Los archivos binarios normalmente contienen bytes que deben interpretarse como algo más que caracteres de texto. 

            Los programas informáticos compilados son ejemplos típicos; de hecho, a veces, especialmente los programadores, se refieren a las aplicaciones compiladas como binarias. 

            Pero los archivos binarios también pueden significar que contienen imágenes, sonidos, versiones comprimidas de otros archivos, etc.; en resumen, cualquier tipo de contenido de archivo.

            Algunos archivos binarios contienen encabezados, bloques de metadatos utilizados por un programa informático para interpretar los datos del archivo. 

            El encabezado suele contener una firma o un número mágico que puede identificar el formato.

            Por ejemplo, un archivo GIF puede contener varias imágenes y los encabezados se utilizan para identificar y describir cada bloque de datos de imagen. 

            Los bytes iniciales del encabezado contendrán texto como GIF87a o GIF89a que puede identificar el binario como un archivo GIF. 

            Si un archivo binario no contiene encabezados, se le puede llamar archivo binario plano.

            Un archivo de texto puede consistir total o parcialmente en información binaria codificada. 

            Al enviar archivos binarios a través de la red, es posible que se codifiquen para que utilicen únicamente caracteres imprimibles.

            Esto suele ser necesario debido a las limitaciones de los protocolos de red utilizados para la navegación por Internet y la comunicación por correo electrónico. 

            Una de esas codificaciones es Base64.

            Además, los archivos que contienen información de clave pública y privada para su uso en sistemas que emplean criptografía asimétrica (como certificados de sitios web) también pueden almacenarse con la información binaria codificada en caracteres imprimibles.


        Manipulación: 

            Para enviar archivos binarios a través de ciertos sistemas (como el correo electrónico) que no permiten todos los valores de datos, a menudo se traducen a una representación de texto plano (usando, por ejemplo, Base64).

            Codificar los datos tiene la desventaja de aumentar el tamaño del archivo durante la transferencia (por ejemplo, el uso de Base64 aumentará el tamaño del archivo en aproximadamente un 30%), además de requerir una traducción nuevamente al binario después de la recepción. 

            El aumento de tamaño puede contrarrestarse mediante una compresión de enlaces de nivel inferior, ya que los datos de texto resultantes tendrán tanta menos entropía a medida que aumentan de tamaño, por lo que los datos reales transferidos en este escenario probablemente serían muy cercanos al tamaño del original datos binarios.

            Microsoft Windows y sus bibliotecas estándar para los lenguajes de programación C y C++ permiten al programador especificar un parámetro que indica si se espera que un archivo sea texto plano o binario al abrirlo; esto afecta las llamadas de biblioteca estándar para leer y escribir desde el archivo en el sentido de que el sistema convierte entre el carácter de "fin de línea" C/C++ (el carácter de salto de línea ASCII) y la secuencia de fin de línea que Windows espera en los archivos (el carácter ASCII),  caracteres de retorno de carro y salto de línea en secuencia. 

            En sistemas tipo Unix, las bibliotecas estándar C y C++ en esos sistemas también permiten al programador especificar si se espera que un archivo sea de texto o binario, pero las bibliotecas pueden ignorar ese parámetro, y lo hacen, como la secuencia de fin de línea en sistemas tipo Unix es solo el carácter de final de línea C/C++.


        Vista:

            Se puede utilizar un editor o visor hexadecimal para ver datos de archivos como una secuencia de valores hexadecimales (o caracteres decimales, binarios o ASCII) para los bytes correspondientes de un archivo binario.

            Si se abre un archivo binario en un editor de texto, cada grupo de ocho bits normalmente se traducirá como un solo carácter y el usuario verá una visualización (probablemente ininteligible) de caracteres textuales. 

            Si el archivo se abre en alguna otra aplicación, esa aplicación tendrá su propio uso para cada byte: tal vez la aplicación trate cada byte como un número y genere un flujo de números entre 0 y 255, o tal vez interprete los números en los bytes como colores y mostrar la imagen correspondiente.

            Otro tipo de visores (llamados "extractores de palabras") simplemente reemplazan los caracteres no imprimibles con espacios que revelan sólo el texto legible por humanos. 

            Este tipo de vista es útil para una inspección rápida de un archivo binario con el fin de encontrar contraseñas en juegos, encontrar texto oculto en archivos que no son de texto y recuperar documentos corruptos.

            Incluso se puede utilizar para inspeccionar archivos (software) sospechosos en busca de efectos no deseados. 

            Por ejemplo, el usuario vería cualquier URL/correo electrónico al que el software sospechoso pueda intentar conectarse para cargar datos no aprobados (para robar).

            Si el archivo se trata como ejecutable y se ejecuta, entonces el sistema operativo intentará interpretar el archivo como una serie de instrucciones en su lenguaje de máquina.


        Interpretación:

            Los estándares son muy importantes para los archivos binarios. 

            Por ejemplo, un archivo binario interpretado por el juego de caracteres ASCII dará como resultado que se muestre texto. 

            Una aplicación personalizada puede interpretar el archivo de manera diferente: un byte puede ser un sonido, un píxel o incluso una palabra completa. 

            El binario en sí no tiene sentido, hasta el momento en que un algoritmo ejecutado defina qué se debe hacer con cada bit, byte, palabra o bloque.

            Por lo tanto, simplemente examinar el binario e intentar compararlo con formatos conocidos puede llevar a una conclusión equivocada sobre lo que realmente representa.

            Este hecho se puede utilizar en esteganografía, donde un algoritmo interpreta un archivo de datos binarios de manera diferente para revelar contenido oculto.

            Sin el algoritmo, es imposible saber si existe contenido oculto.


        Compatibilidad: 

            Dos archivos que sean compatibles con binarios tendrán la misma secuencia de ceros y unos en la parte de datos del archivo. 

            Sin embargo, el encabezado del archivo puede ser diferente.

            El término se utiliza más comúnmente para indicar que los archivos de datos producidos por una aplicación son exactamente iguales a los archivos de datos producidos por otra aplicación. 

            Por ejemplo, algunas empresas de software producen aplicaciones para Windows y Macintosh que son compatibles con binarios, lo que significa que un archivo producido en un entorno Windows es intercambiable con un archivo producido en un Macintosh. 

            Esto evita muchos de los problemas de conversión causados por la importación y exportación de datos.

            Un posible problema de compatibilidad binaria entre diferentes computadoras es el endianidad de la computadora. 

            Algunas computadoras almacenan los bytes de un archivo en un orden diferente.



|| Word
    
    En informática, word es la unidad natural de datos utilizada por un diseño de procesador particular. 

    Es un dato de tamaño fijo manejado como una unidad por el conjunto de instrucciones o el hardware del procesador. 

    El número de bits o dígitos en una palabra (el tamaño de la palabra, el ancho de la palabra o la longitud de la palabra) es una característica importante de cualquier diseño de procesador o arquitectura de computadora específica.

    El tamaño de una palabra se refleja en muchos aspectos de la estructura y funcionamiento de una computadora; la mayoría de los registros en un procesador suelen tener el tamaño de una palabra y el dato más grande que se puede transferir hacia y desde la memoria de trabajo en una sola operación es una palabra en muchas (no todas) arquitecturas.

    El tamaño de dirección más grande posible, utilizado para designar una ubicación en la memoria, suele ser una palabra de hardware (aquí, "palabra de hardware" significa la palabra natural de tamaño completo del procesador, a diferencia de cualquier otra definición utilizada).

    La documentación para computadoras más antiguas con un tamaño de palabra fijo comúnmente indica los tamaños de memoria en palabras en lugar de bytes o caracteres. 

    La documentación a veces usa prefijos métricos correctamente, a veces con redondeo, por ejemplo, 65 kiloword (kW) que significan 65536 palabras, y a veces los usa incorrectamente, con kiloword (kW) que significan 1024 palabras (2^10) y megaword (MW) que significan 1,048,576 palabras ( 2^20). 

    Con la estandarización de los bytes de 8 bits y la direccionabilidad de bytes, indicar los tamaños de memoria en bytes, kilobytes y megabytes con potencias de 1024 en lugar de 1000 se ha convertido en la norma, aunque existe cierto uso de los prefijos binarios IEC.

    Varias de las primeras computadoras (y algunas modernas también) usan decimales codificados en binario en lugar de binario simple, y generalmente tienen un tamaño de palabra de 10 o 12 dígitos decimales, y algunas de las primeras computadoras decimales no tienen ninguna longitud de palabra fija. 

    Los primeros sistemas binarios tendían a utilizar longitudes de palabras que eran múltiplos de 6 bits, siendo la palabra de 36 bits especialmente común en las computadoras centrales. 

    La introducción de ASCII condujo a la transición a sistemas con longitudes de palabras múltiplos de 8 bits, siendo populares las máquinas de 16 bits en la década de 1970 antes de la transición a procesadores modernos de 32 o 64 bits. 

    Los diseños para fines especiales, como los procesadores de señales digitales, pueden tener cualquier longitud de palabra de 4 a 80 bits.

    El tamaño de una palabra a veces puede diferir del esperado debido a la compatibilidad con computadoras anteriores. 

    Si varias variaciones compatibles o una familia de procesadores comparten una arquitectura y un conjunto de instrucciones comunes pero difieren en el tamaño de las palabras, su documentación y software pueden volverse notablemente complejos para adaptarse a la diferencia ( Familias de tamaños).
        

    Usos: 

        Dependiendo de cómo esté organizada una computadora, las unidades de tamaño de palabra se pueden usar para:


        Números de coma fija:

            Los titulares/holders de valores numéricos de punto fijo, generalmente enteros, pueden estar disponibles en uno o varios tamaños diferentes, pero uno de los tamaños disponibles casi siempre será la palabra (word, 32/64). 

            Es probable que los otros tamaños, si los hay, sean múltiplos o fracciones del tamaño de la palabra.

            Los tamaños más pequeños normalmente se utilizan sólo para un uso eficiente de la memoria; cuando se cargan en el procesador, sus valores generalmente van a un contenedor más grande, del tamaño de una palabra.


        Números coma flotante:

            Los titulares/holders de valores numéricos de punto flotante suelen ser una palabra o un múltiplo de una palabra.


        Direcciones

            Los titulares de direcciones de memoria deben tener un tamaño capaz de expresar el rango de valores necesario, pero no ser excesivamente grandes, por lo que a menudo el tamaño utilizado es la palabra, aunque también puede ser un múltiplo o una fracción del tamaño de la palabra.


        Registros

            Los registros del procesador están diseñados con un tamaño apropiado para el tipo de datos que contienen, p. números enteros, números de punto flotante o direcciones. 

            Muchas arquitecturas informáticas utilizan registros de propósito general que son capaces de almacenar datos en múltiples representaciones.


        Transferencia de memoria-procesador

            Cuando el procesador lee del subsistema de memoria en un registro o escribe el valor de un registro en la memoria, la cantidad de datos transferidos suele ser una palabra.

            Históricamente, esta cantidad de bits que podían transferirse en un ciclo también se denominaba catena en algunos entornos (como el Bull GAMMA 60). 

            En los subsistemas de memoria simples, la palabra se transfiere a través del bus de datos de la memoria, que normalmente tiene un ancho de una palabra o media palabra. 

            En los subsistemas de memoria que utilizan cachés, la transferencia del tamaño de una palabra es la que se realiza entre el procesador y el primer nivel de caché; en niveles inferiores de la jerarquía de memoria normalmente se utilizan transferencias más grandes (que son múltiplos del tamaño de la palabra).


        Unidad de resolución de direcciones

            En una arquitectura dada, los valores de direcciones sucesivos casi siempre designan unidades de memoria sucesivas; esta unidad es la unidad de resolución de direcciones. 

            En la mayoría de las computadoras, la unidad es un carácter (por ejemplo, un byte) o una palabra. 

            (Algunas computadoras han usado resolución de bits). 

            Si la unidad es una palabra, entonces se puede acceder a una mayor cantidad de memoria usando una dirección de un tamaño determinado a costa de una mayor complejidad para acceder a caracteres individuales. 

            Por otro lado, si la unidad es un byte, entonces se pueden direccionar caracteres individuales (es decir, seleccionarlos durante la operación de memoria).


        Instrucciones

            Las instrucciones de máquina normalmente tienen el tamaño de la palabra de la arquitectura, como en las arquitecturas RISC, o un múltiplo del tamaño "char", que es una fracción del mismo. 

            Esta es una elección natural ya que las instrucciones y los datos suelen compartir el mismo subsistema de memoria. 

            En las arquitecturas de Harvard, los tamaños de palabras de instrucciones y datos no necesitan estar relacionados, ya que las instrucciones y los datos se almacenan en memorias diferentes; por ejemplo, el procesador del conmutador telefónico electrónico 1ESS tiene instrucciones de 37 bits y palabras de datos de 23 bits.


    Elección del tamaño de la palabra

        Cuando se diseña la arquitectura de una computadora, la elección del tamaño de palabra es de gran importancia. 

        Hay consideraciones de diseño que alientan tamaños particulares de grupos de bits para usos particulares (por ejemplo, para direcciones), y estas consideraciones apuntan a diferentes tamaños para diferentes usos. 

        Sin embargo, consideraciones de economía en el diseño presionan fuertemente a favor de un tamaño, o muy pocos tamaños relacionados por múltiplos o fracciones (submúltiplos) con un tamaño primario. 

        Ese tamaño preferido se convierte en el tamaño de palabra de la arquitectura.

        El tamaño de los caracteres era en el pasado (codificación de caracteres de tamaño variable anterior) una de las influencias en la unidad de resolución de direcciones y la elección del tamaño de las palabras. 

        Antes de mediados de la década de 1960, los caracteres se almacenaban con mayor frecuencia en seis bits; esto no permitía más de 64 caracteres, por lo que el alfabeto se limitaba a mayúsculas. 

        Dado que es eficiente en el tiempo y el espacio que el tamaño de la palabra sea un múltiplo del tamaño del carácter, los tamaños de las palabras en este período solían ser múltiplos de 6 bits (en máquinas binarias).

        Una elección común entonces era la palabra de 36 bits, que también es un buen tamaño para las propiedades numéricas de un formato de punto flotante.

        Después de la introducción del diseño IBM System/360, que utiliza caracteres de ocho bits y admite letras minúsculas, el tamaño estándar de un carácter (o más exactamente, un byte) pasa a ser de ocho bits. 

        A partir de entonces, los tamaños de las palabras son naturalmente múltiplos de ocho bits, siendo comúnmente utilizados 16, 32 y 64 bits.: 


        Arquitecturas de palabras variables:

            Los primeros diseños de máquinas incluían algunas que utilizaban lo que a menudo se denomina longitud de palabra variable. 

            En este tipo de organización, un operando no tiene una longitud fija. 

            Dependiendo de la máquina y de la instrucción, la longitud puede indicarse mediante un campo de recuento, mediante un carácter delimitador o mediante un bit adicional llamado, por ejemplo, bandera o marca denominativa. 

            Estas máquinas suelen utilizar decimales codificados en binario en dígitos de 4 bits o en caracteres de 6 bits para los números. 

            Esta clase de máquinas incluye IBM 702, IBM 705, IBM 7080, IBM 7010, UNIVAC 1050, IBM 1401, IBM 1620 y RCA 301.

            La mayoría de estas máquinas funcionan con una unidad de memoria a la vez y, dado que cada instrucción o dato tiene varias unidades de longitud, cada instrucción requiere varios ciclos solo para acceder a la memoria.

            Estas máquinas suelen ser bastante lentas debido a esto. 

            Por ejemplo, la instrucción se recupera en un IBM 1620 Modelo.

            Tomo 8 ciclos (160 μs) solo para leer los 12 dígitos de la instrucción (el Modelo II redujo esto a 6 ciclos, o 4 ciclos si la instrucción no necesitaba ambos campos de dirección). 

            La ejecución de la instrucción requiere un número variable de ciclos, dependiendo del tamaño de los operandos.


        Direccionamiento de palabra, bit y byte

            El modelo de memoria de una arquitectura está fuertemente influenciado por el tamaño de las palabras. 

            En particular, a menudo se ha elegido como palabra la resolución de una dirección de memoria, es decir, la unidad más pequeña que puede ser designada por una dirección. 

            En este enfoque, el enfoque de máquina direccionable por palabras, los valores de dirección que difieren en uno designan palabras de memoria adyacentes. 

            Esto es natural en máquinas que casi siempre trabajan con unidades de palabras (o de varias palabras) y tiene la ventaja de permitir que las instrucciones utilicen campos de tamaño mínimo para contener direcciones, lo que puede permitir un tamaño de instrucción más pequeño o una variedad mayor de instrucciones.

            Cuando el procesamiento de bytes va a ser una parte importante de la carga de trabajo, suele ser más ventajoso utilizar el byte, en lugar de la palabra, como unidad de resolución de direcciones. 

            Los valores de dirección que difieren en uno designan bytes adyacentes en la memoria. 

            Esto permite abordar directamente un carácter arbitrario dentro de una cadena de caracteres. 

            Aún se puede direccionar una palabra, pero la dirección que se utilizará requiere unos cuantos bits más que la alternativa de resolución de palabras. 

            El tamaño de la palabra debe ser un múltiplo entero del tamaño de los caracteres en esta organización. 

            Este enfoque de direccionamiento se utilizó en IBM 360 y ha sido el enfoque más común en las máquinas diseñadas desde entonces.

            Cuando la carga de trabajo implica procesar campos de diferentes tamaños, puede resultar ventajoso dirigirse al bit. 

            Las máquinas con direccionamiento de bits pueden tener algunas instrucciones que utilizan un tamaño de bytes definido por el programador y otras instrucciones que operan con tamaños de datos fijos. 

            Como ejemplo, en IBM 7030 ("Stretch"), una instrucción de punto flotante sólo puede direccionar palabras, mientras que una instrucción aritmética de enteros puede especificar una longitud de campo de 1 a 64 bits, un tamaño de byte de 1 a 8 bits y un desplazamiento del acumulador de 0-127 bits.

            En una máquina direccionable por bytes con instrucciones de almacenamiento a almacenamiento (SS), normalmente hay instrucciones de movimiento para copiar uno o varios bytes de una ubicación arbitraria a otra. 

            En una máquina orientada a bytes (direccionable por bytes) sin instrucciones SS, mover un solo byte de una ubicación arbitraria a otra suele ser:

                 CARGAR el byte de origen

                 ALMACENE el resultado nuevamente en el byte de destino

            Se puede acceder a los bytes individuales en una máquina orientada a palabras de dos maneras.

            Los bytes se pueden manipular mediante una combinación de operaciones de desplazamiento y máscara en los registros. 

            Mover un solo byte de una ubicación arbitraria a otra puede requerir el equivalente de lo siguiente:

                 CARGAR la palabra que contiene el byte de origen

                 CAMBIAR la palabra de origen para alinear el byte deseado con la posición correcta en la palabra de destino
                 Y la palabra fuente con una máscara para poner a cero todos menos los bits deseados

                 CARGAR la palabra que contiene el byte de destino
                 Y la palabra objetivo con una máscara para poner a cero el byte objetivo
                 O los registros que contienen las palabras de origen y de destino para insertar el byte de origen

                 GUARDAR el resultado en la ubicación de destino                 

            Alternativamente, muchas máquinas orientadas a palabras implementan operaciones de bytes con instrucciones que utilizan punteros de bytes especiales en registros o memoria. 

            Por ejemplo, el puntero de bytes PDP-10 contenía el tamaño del byte en bits (permitiendo acceder a bytes de diferentes tamaños), la posición del bit del byte dentro de la palabra y la dirección de palabra de los datos. 

            Las instrucciones podrían ajustar automáticamente el puntero al siguiente byte, por ejemplo, en operaciones de carga y depósito (almacenamiento).


        Potencias de dos
            
            Se utilizan diferentes cantidades de memoria para almacenar valores de datos con diferentes grados de precisión. 

            Los tamaños comúnmente utilizados suelen ser una potencia de dos múltiplos de la unidad de resolución de dirección (byte o palabra).

            Convertir el índice de un elemento en una matriz en el desplazamiento de la dirección de memoria del elemento requiere solo una operación de desplazamiento en lugar de una multiplicación. 

            En algunos casos esta relación también puede evitar el uso de operaciones de división.

            Como resultado, la mayoría de los diseños de computadoras modernos tienen tamaños de palabras (y otros tamaños de operandos) que son una potencia de dos veces el tamaño de un byte.


        Familia de tamaños: 

            A medida que los diseños informáticos se han vuelto más complejos, la importancia central del tamaño de una sola palabra para una arquitectura ha disminuido. 

            Aunque un hardware más capaz puede utilizar una variedad más amplia de tamaños de datos, las fuerzas del mercado ejercen presión para mantener la compatibilidad con versiones anteriores y al mismo tiempo ampliar la capacidad del procesador.

            Como resultado, lo que podría haber sido el tamaño de palabra central en un diseño nuevo tiene que coexistir como un tamaño alternativo al tamaño de palabra original en un diseño compatible con versiones anteriores. 

            El tamaño original de la palabra seguirá estando disponible en diseños futuros, formando la base de una familia de tamaños.

            A mediados de la década de 1970, DEC diseñó el VAX para que fuera un sucesor de 32 bits del PDP-11 de 16 bits. 

            Usaron palabra para una cantidad de 16 bits, mientras que palabra larga se refería a una cantidad de 32 bits; esta terminología es la misma que la terminología utilizada para el PDP-11.

            Esto contrastaba con las máquinas anteriores, donde la unidad natural de direccionamiento de la memoria se llamaría palabra, mientras que una cantidad que fuera media palabra se llamaría media palabra. 

            De acuerdo con este esquema, una palabra cuádruple VAX es de 64 bits. 

            Continuaron con esta terminología de palabra de 16 bits/palabra larga de 32 bits/palabra cuádruple de 64 bits con el Alpha de 64 bits.

            Otro ejemplo es la familia x86, de la que se han lanzado procesadores con tres longitudes de palabra diferentes (16 bits, luego 32 y 64 bits), mientras que palabra sigue designando una cantidad de 16 bits.

            Como el software se traslada habitualmente de una longitud de palabra a la siguiente, algunas API y documentación definen o hacen referencia a una longitud de palabra anterior (y por lo tanto más corta) que la longitud completa de la palabra en la CPU para la que se puede compilar el software. 

            Además, de manera similar a cómo se usan los bytes para números pequeños en muchos programas, se puede usar una palabra más corta (16 o 32 bits) en contextos donde no se necesita el rango de una palabra más amplia (especialmente cuando esto puede ahorrar un considerable espacio de pila o caché, espacio de memoria).

            Por ejemplo, la API de Windows de Microsoft mantiene la definición del lenguaje de programación de WORD como 16 bits, a pesar de que la API puede usarse en un procesador x86 de 32 o 64 bits, donde el tamaño de palabra estándar sería de 32 o 64 bits, respectivamente. 

            Las estructuras de datos que contienen palabras de diferentes tamaños se refieren a ellas como:

                 PALABRA (16 bits/2 bytes)
                 DWORD (32 bits/4 bytes)
                 QWORD (64 bits/8 bytes)

            Un fenómeno similar se ha desarrollado en el lenguaje ensamblador x86 de Intel: debido a la compatibilidad con varios tamaños (y la compatibilidad con versiones anteriores) en el conjunto de instrucciones, algunos mnemotécnicos de instrucción llevan identificadores "d" o "q" que denotan "doble", "cuádruple". o "doble cuádruple", que están en términos del tamaño de palabra de 16 bits original de la arquitectura.

            Un ejemplo con un tamaño de palabra diferente es la familia IBM System/360. 

            En la arquitectura System/360, la arquitectura System/370 y la arquitectura System/390, hay bytes de 8 bits, medias palabras de 16 bits, palabras de 32 bits y palabras dobles de 64 bits. z/Architecture, que es el miembro de 64 bits de esa familia de arquitectura, continúa haciendo referencia a medias palabras de 16 bits, palabras de 32 bits y palabras dobles de 64 bits, y además presenta palabras cuádruples de 128 bits.

            En general, los procesadores nuevos deben utilizar las mismas longitudes de palabras de datos y anchos de direcciones virtuales que un procesador más antiguo para tener compatibilidad binaria con ese procesador más antiguo.

            A menudo, el código fuente cuidadosamente escrito (escrito teniendo en cuenta la compatibilidad del código fuente y la portabilidad del software) puede recompilarse para ejecutarse en una variedad de procesadores, incluso aquellos con diferentes longitudes de palabras de datos o diferentes anchos de direcciones, o ambos.


    Datum: 

        En informática, datos (tratados como singular, plural o como sustantivo masivo) son cualquier secuencia de uno o más símbolos; datum es un símbolo único de datos. 

        Los datos requieren interpretación para convertirse en información.

        Los datos digitales son datos que se representan utilizando el sistema numérico binario de unos (1) y ceros (0), en lugar de una representación analógica. 

        En los sistemas informáticos modernos (posteriores a 1960), todos los datos son digitales.

        Los datos existen en tres estados: datos en reposo, datos en tránsito y datos en uso. 

        Los datos dentro de una computadora, en la mayoría de los casos, se mueven como datos paralelos. 

        Los datos que se mueven hacia o desde una computadora, en la mayoría de los casos, se mueven como datos en serie.

        Los datos obtenidos de un dispositivo analógico, como un sensor de temperatura, se pueden convertir a digitales mediante un convertidor de analógico a digital. 

        Los datos que representan cantidades, caracteres o símbolos sobre los cuales realiza operaciones una computadora se almacenan y registran en medios de registro magnéticos, ópticos, electrónicos o mecánicos, y se transmiten en forma de señales eléctricas u ópticas digitales. 

        Los datos entran y salen de las computadoras a través de dispositivos periféricos.

        Los elementos físicos de la memoria de la computadora constan de una dirección y un byte/palabra de almacenamiento de datos. 

        Los datos digitales a menudo se almacenan en bases de datos relacionales, como tablas o bases de datos SQL, y generalmente se pueden representar como pares clave/valor abstractos. 

        Los datos se pueden organizar en muchos tipos diferentes de estructuras de datos, incluidos matrices, gráficos y objetos. 

        Las estructuras de datos pueden almacenar datos de muchos tipos diferentes, incluidos números, cadenas e incluso otras estructuras de datos.


        Características: 

            Los metadatos ayudan a traducir datos en información. 

            Los metadatos son datos sobre los datos. 

            Los metadatos pueden ser implícitos, especificados o proporcionados.

            Los datos relativos a eventos o procesos físicos tendrán un componente temporal. 

            Este componente temporal puede estar implícito.

            Este es el caso cuando un dispositivo como un registrador de temperatura recibe datos de un sensor de temperatura. 

            Cuando se recibe la temperatura se supone que el dato tiene una referencia temporal de ahora. 

            De este modo, el dispositivo registra la fecha, la hora y la temperatura juntas. 

            Cuando el registrador de datos comunica temperaturas, también debe informar la fecha y la hora como metadatos para cada lectura de temperatura.

            Básicamente, las computadoras siguen una secuencia de instrucciones que se les dan en forma de datos.

            Un conjunto de instrucciones para realizar una tarea (o tareas) determinada se denomina programa. 

            Un programa son datos en forma de instrucciones codificadas para controlar el funcionamiento de una computadora u otra máquina. 

            En el caso nominal, el programa, tal como lo ejecuta la computadora, consistirá en código de máquina. 

            También son datos los elementos de almacenamiento manipulados por el programa, pero no ejecutados realmente por la unidad central de procesamiento (CPU). 

            En su forma más esencial, un dato único es un valor almacenado en una ubicación específica. 

            Por lo tanto, es posible que los programas informáticos funcionen sobre otros programas informáticos manipulando sus datos programáticos.

            Para almacenar bytes de datos en un archivo, deben serializarse en un formato de archivo.

            Normalmente, los programas se almacenan en tipos de archivos especiales, distintos de los que se utilizan para otros datos. 

            Los archivos ejecutables contienen programas; todos los demás archivos también son archivos de datos. 

            Sin embargo, los archivos ejecutables también pueden contener datos utilizados por el programa integrado en el programa. 

            En particular, algunos archivos ejecutables tienen un segmento de datos, que nominalmente contiene constantes y valores iniciales para variables, los cuales pueden considerarse datos.

            La línea entre el programa y los datos puede volverse borrosa.

            Un intérprete, por 
            ejemplo, es un programa, los datos de entrada a un intérprete son en sí mismos un programa, pero no uno expresado en lenguaje de máquina nativo. 

            En muchos casos, el programa interpretado será un archivo de texto legible por humanos, que se manipula con un programa de edición de texto. 

            De manera similar, la metaprogramación implica programas que manipulan otros programas como datos. 

            Programas como compiladores, enlazadores, depuradores, actualizadores de programas, escáneres de virus y similares utilizan otros programas como datos.

            Por ejemplo, un usuario podría primero indicarle al sistema operativo que cargue un programa de procesador de textos desde un archivo y luego usar el programa en ejecución para abrir y editar un documento almacenado en otro archivo. 

            En este ejemplo, el documento se consideraría datos. 

            Si el procesador de textos también incluye un corrector ortográfico, entonces el diccionario (lista de palabras) del corrector ortográfico también se considerará datos. 

            Los algoritmos utilizados por el corrector ortográfico para sugerir correcciones serían datos de código de máquina o texto en algún lenguaje de programación interpretable.

            En un uso alternativo, los archivos binarios (que no son legibles por humanos) a veces se denominan datos para distinguirlos del texto legible por humanos.


        Claves y valores de datos, estructuras y persistencia:

            Las claves de los datos proporcionan el contexto para los valores.

            Independientemente de la estructura de los datos, siempre hay un componente clave presente. 

            Las claves en los datos y las estructuras de datos son esenciales para dar significado a los valores de los datos. 

            Sin una clave que esté directa o indirectamente asociada con un valor, o una colección de valores en una estructura, los valores pierden sentido y dejan de ser datos. 

            Es decir, tiene que haber un componente clave vinculado a un componente de valor para que se considere dato.

            Los datos se pueden representar en las computadoras de varias maneras, según los siguientes ejemplos.


            RAM:

                La memoria de acceso aleatorio (RAM) contiene datos a los que la CPU tiene acceso directo. 

                Una CPU sólo puede manipular datos dentro de los registros o la memoria de su procesador. 

                Esto es lo opuesto al almacenamiento de datos, donde la CPU debe dirigir la transferencia de datos entre el dispositivo de almacenamiento (disco, cinta...) y la memoria. 

                La RAM es una matriz de ubicaciones lineales contiguas que un procesador puede leer o escribir proporcionando una dirección para la operación de lectura o escritura. 

                El procesador puede operar en cualquier ubicación de la memoria en cualquier momento y en cualquier orden. 

                En la RAM, el elemento de datos más pequeño es el bit binario. 

                Las capacidades y limitaciones de acceso a la RAM son específicas del procesador. 

                En general, la memoria principal está organizada como una matriz de ubicaciones que comienzan en la dirección 0 (hexadecimal 0). 

                Cada ubicación puede almacenar normalmente 8 o 32 bits, según la arquitectura de la computadora.


            Llaves/claves (keys):

                Las claves de datos no necesitan ser una dirección de hardware directa en la memoria. 

                Los códigos de claves indirectas, abstractas y lógicas se pueden almacenar en asociación con valores para formar una estructura de datos. 

                Las estructuras de datos tienen desplazamientos (o enlaces o rutas) predeterminados desde el inicio de la estructura, en la que se almacenan los valores de los datos.

                Por lo tanto, la clave de datos consta de la clave de la estructura más el desplazamiento (o enlaces o rutas) dentro de la estructura. 

                Cuando se repite una estructura de este tipo, almacenando variaciones de los valores de datos y las claves de datos dentro de la misma estructura repetitiva, se puede considerar que el resultado se asemeja a una tabla, en la que cada elemento de la estructura repetitiva se considera una columna y cada repetición de la estructura se considera como una fila de la tabla. 

                En tal organización de datos, la clave de datos suele ser un valor en una (o una combinación de los valores en varias) de las columnas.


            Estructuras de datos recurrentes organizadas:
            
                La vista tabular de estructuras de datos repetidas es sólo una de muchas posibilidades. 

                Las estructuras de datos repetidas se pueden organizar jerárquicamente, de modo que los nodos estén vinculados entre sí en una cascada de relaciones padre-hijo. 

                Los valores y estructuras de datos potencialmente más complejas están vinculados a los nodos. 

                Por tanto, la jerarquía nodal proporciona la clave para abordar las estructuras de datos asociadas con los nodos. 

                Esta representación puede considerarse como un árbol invertido. 

                Los sistemas de archivos de los sistemas operativos de computadora modernos son un ejemplo común; y XML es otra.


            Datos ordenados u orden

                Los datos tienen algunas características inherentes cuando se clasifican según una clave. 

                Todos los valores de los subconjuntos de la clave aparecen juntos. 

                Cuando se pasa secuencialmente a través de grupos de datos con la misma clave, o un subconjunto de cambios de clave, esto se denomina en los círculos de procesamiento de datos una interrupción o una interrupción de control. 

                Facilita particularmente la agregación de valores de datos en subconjuntos de una clave.


            Almacenamiento periférico

                Hasta la llegada de la memoria no volátil masiva como la flash, el almacenamiento persistente de datos se lograba tradicionalmente escribiendo los datos en dispositivos de bloque externos como cintas magnéticas y unidades de disco.

                Estos dispositivos normalmente buscan una ubicación en el medio magnético y luego leen o escriben bloques de datos de un tamaño predeterminado. 

                En este caso, la ubicación de búsqueda en el medio es la clave de datos y los bloques son los valores de datos. 

                Los primeros sistemas de archivos de datos de disco sin formato o sistemas operativos de disco utilizados anteriormente reservaban bloques contiguos en la unidad de disco para archivos de datos. 

                En esos sistemas, los archivos podían llenarse y quedarse sin espacio para datos antes de que se hubieran escrito todos los datos en ellos.


                Por lo tanto, gran parte del espacio de datos no utilizado se reservó de manera improductiva para garantizar el espacio libre adecuado para cada archivo. 

                Los sistemas de archivos posteriores introdujeron particiones.

                Reservaron bloques de espacio de datos en disco para particiones y utilizaron los bloques asignados de manera más económica, asignando dinámicamente bloques de una partición a un archivo según fuera necesario. 

                Para lograr esto, el sistema de archivos tenía que realizar un seguimiento de qué bloques usaban o no los archivos de datos en un catálogo o tabla de asignación de archivos. 

                Aunque esto hizo un mejor uso del espacio de datos del disco, resultó en la fragmentación de archivos en todo el disco y una sobrecarga de rendimiento concomitante debido al tiempo de búsqueda adicional para leer los datos. 

                Los sistemas de archivos modernos reorganizan los archivos fragmentados de forma dinámica para optimizar los tiempos de acceso a los archivos. 

                Otros desarrollos en los sistemas de archivos dieron como resultado la virtualización de las unidades de disco, es decir, donde una unidad lógica se puede definir como particiones de varias unidades físicas.


            Datos indexados:

                Recuperar un pequeño subconjunto de datos de un conjunto mucho más grande puede implicar una búsqueda ineficiente de los datos de forma secuencial. 

                Los índices son una forma de copiar claves y direcciones de ubicación de estructuras de datos en archivos, tablas y conjuntos de datos, y luego organizarlos utilizando estructuras de árbol invertidas para reducir el tiempo necesario para recuperar un subconjunto de los datos originales.

                Para hacer esto, se debe conocer la clave del subconjunto de datos que se van a recuperar antes de que comience la recuperación. 

                Los índices más populares son el árbol B y los métodos de indexación de clave hash dinámica.

                La indexación es una tarea indirecta para archivar y recuperar datos. 

                Hay otras formas de organizar índices, p. clasificando las claves y utilizando un algoritmo de búsqueda binaria.


            Abstracción e indirección:

                La programación orientada a objetos utiliza dos conceptos básicos para comprender los datos y el software:

                La estructura taxonómica de rangos de clases, que es un ejemplo de estructura de datos jerárquica; y
                en tiempo de ejecución, la creación de referencias a estructuras de datos en memoria de objetos que han sido instanciados desde una biblioteca de clases.

                Sólo después de la creación de instancias existe un objeto de una clase específica. 

                Una vez que se borra la referencia de un objeto, el objeto también deja de existir. 

                Las ubicaciones de memoria donde se almacenaron los datos del objeto son basura y se reclasifican como memoria no utilizada disponible para su reutilización.


            Datos de la base de datos:

                La llegada de las bases de datos introdujo una capa adicional de abstracción para el almacenamiento de datos persistente.

                Las bases de datos utilizan metadatos y un protocolo de lenguaje de consulta estructurado entre los sistemas cliente y servidor, comunicándose a través de una red informática, utilizando un sistema de registro de confirmación de dos fases para garantizar la integridad de las transacciones al guardar datos.


            Procesamiento de datos distribuido en paralelo:

                Las tecnologías modernas de persistencia de datos escalables y de alto rendimiento, como Apache Hadoop, se basan en un procesamiento de datos distribuido masivamente en paralelo a través de muchas computadoras básicas en una red de gran ancho de banda.

                En tales sistemas, los datos se distribuyen entre varias computadoras y, por lo tanto, cualquier computadora particular del sistema debe estar representada en la clave de los datos, ya sea directa o indirectamente. 

                Esto permite diferenciar entre dos conjuntos de datos idénticos, cada uno de los cuales se procesa en una computadora diferente al mismo tiempo.


    Instruction set:

        Una arquitectura de conjunto de instrucciones (ISA) es parte del modelo abstracto de una computadora, que generalmente define cómo el software controla la CPU. 

        Un dispositivo que ejecuta instrucciones descritas por ese ISA, como una unidad central de procesamiento (CPU), se denomina implementación.

        En general, una ISA define las instrucciones admitidas, los tipos de datos, los registros, el soporte de hardware para administrar la memoria principal, las características fundamentales (como la consistencia de la memoria, los modos de direccionamiento, la memoria virtual) y el modelo de entrada/salida de una familia de implementaciones de la ISA.

        Una ISA especifica el comportamiento del código de máquina que se ejecuta en implementaciones de esa ISA de una manera que no depende de las características de esa implementación, proporcionando compatibilidad binaria entre implementaciones. 

        Esto permite múltiples implementaciones de una ISA que difieren en características como rendimiento, tamaño físico y costo monetario (entre otras cosas), pero que son capaces de ejecutar el mismo código de máquina, de modo que una máquina de menor rendimiento y menor costo pueda ser reemplazado por una máquina de mayor costo y mayor rendimiento sin tener que reemplazar el software.

        También permite la evolución de las microarquitecturas de las implementaciones de esa ISA, de modo que una implementación más nueva y de mayor rendimiento de una ISA pueda ejecutar software que se ejecuta en generaciones anteriores de implementaciones.

        Si un sistema operativo mantiene una interfaz binaria de aplicación (ABI) estándar y compatible para una ISA en particular, el código de máquina se ejecutará en futuras implementaciones de esa ISA y sistema operativo.

        Sin embargo, si una ISA admite la ejecución de múltiples sistemas operativos, no garantiza que el código de máquina para un sistema operativo se ejecute en otro sistema operativo, a menos que el primer sistema operativo admita la ejecución de código de máquina creado para el otro sistema operativo.

        Una ISA se puede ampliar agregando instrucciones u otras capacidades, o agregando soporte para direcciones y valores de datos más grandes; una implementación de ISA extendida aún podrá ejecutar código de máquina para versiones de ISA sin esas extensiones. 

        El código de máquina que utiliza esas extensiones solo se ejecutará en implementaciones que admitan esas extensiones.

        La compatibilidad binaria que proporcionan convierte a las ISA en una de las abstracciones más fundamentales de la informática.


        Descripción general:

            Una arquitectura de conjunto de instrucciones se distingue de una microarquitectura, que es el conjunto de técnicas de diseño de procesador utilizadas, en un procesador particular, para implementar el conjunto de instrucciones. 

            Los procesadores con diferentes microarquitecturas pueden compartir un conjunto de instrucciones común. 

            Por ejemplo, Intel Pentium y AMD Athlon implementan versiones casi idénticas del conjunto de instrucciones x86, pero tienen diseños internos radicalmente diferentes.

            El concepto de arquitectura, distinta del diseño de una máquina específica, fue desarrollado por Fred Brooks en IBM durante la fase de diseño de System/360.

                Antes de NPL [System/360], los diseñadores de computadoras de la compañía habían tenido libertad para cumplir con los objetivos de costos no sólo seleccionando tecnologías sino también diseñando mejoras funcionales y arquitectónicas.

                El objetivo de compatibilidad SPREAD, por el contrario, postulaba una arquitectura única para una serie de cinco procesadores que abarcaban una amplia gama de costos y rendimiento.

                Ninguno de los cinco equipos de diseño de ingeniería podía contar con poder realizar ajustes en las especificaciones arquitectónicas como una forma de aliviar las dificultades para lograr los objetivos de costos y desempeño.

            Algunas máquinas virtuales que admiten código de bytes como su ISA, como Smalltalk, la máquina virtual Java y Common Language Runtime de Microsoft, implementan esto traduciendo el código de bytes de las rutas de código de uso común al código de máquina nativo. 

            Además, estas máquinas virtuales ejecutan rutas de código utilizadas con menos frecuencia mediante interpretación ( Compilación just-in-time). 

            Transmeta implementó el conjunto de instrucciones x86 sobre procesadores VLIW de esta manera.


        Clasificación de las ISA:

            Una ISA se puede clasificar de varias maneras diferentes. 

            Una clasificación común es por complejidad arquitectónica. 

            Una computadora con conjunto de instrucciones complejas (CISC) tiene muchas instrucciones especializadas, algunas de las cuales rara vez se usan en programas prácticos. 

            Una computadora con conjunto de instrucciones reducido (RISC) simplifica el procesador al implementar de manera eficiente solo las instrucciones que se usan con frecuencia en los programas, mientras que las operaciones menos comunes se implementan como subrutinas, lo que compensa el tiempo adicional de ejecución del procesador resultante por el uso poco frecuente.

            Otros tipos incluyen arquitecturas de palabra de instrucción muy larga (VLIW), y las arquitecturas de palabra de instrucción larga (LIW) estrechamente relacionadas y de computación de instrucción explícitamente paralela (EPIC). 

            Estas arquitecturas buscan explotar el paralelismo a nivel de instrucciones con menos hardware que RISC y CISC haciendo que el compilador sea responsable de la emisión y programación de las instrucciones.

            Se han estudiado arquitecturas con una complejidad aún menor, como la computadora con conjunto mínimo de instrucciones (MISC) y la computadora con un conjunto de instrucciones (OISC). 

            Estos son tipos teóricamente importantes, pero no se han comercializado.


        Instrucciones:

            El lenguaje de máquina se construye a partir de declaraciones o instrucciones discretas.

            En la arquitectura de procesamiento, una instrucción dada puede especificar:

                código de operación (la instrucción a realizar), p.e. agregar, copiar, probar
                 
                cualquier operando explícito:

                    registros
                    
                    valores literales/constantes
                    
                    Modos de direccionamiento utilizados para acceder a la memoria.

            Se construyen operaciones más complejas combinando estas instrucciones simples, que se ejecutan secuencialmente o según lo indiquen las instrucciones de flujo de control.


        Tipos de instrucción:

            Ejemplos de operaciones comunes a muchos conjuntos de instrucciones incluyen:
            

            Manejo de datos y operaciones de memoria.

                Establezca un registro en un valor constante fijo.
                
                Copie datos desde una ubicación de memoria o un registro a una ubicación de memoria o un registro (una instrucción de máquina a menudo se llama mover; sin embargo, el término es engañoso). 

                Se utilizan para almacenar el contenido de un registro, el contenido de otra ubicación de memoria o el resultado de un cálculo, o para recuperar datos almacenados para realizar un cálculo con ellos más adelante. A menudo se les llama operaciones de carga y almacenamiento.

                Leer y escribir datos desde dispositivos de hardware.


            Operaciones aritméticas y lógicas:

                Sumar, restar, multiplicar o dividir los valores de dos registros, colocando el resultado en un registro, posiblemente estableciendo uno o más códigos de condición en un registro de estado.

                    incrementar, disminuir en algunas ISA, guardar la búsqueda de operandos en casos triviales.

                Realice operaciones bit a bit, por ejemplo, tomando la conjunción y disyunción de los bits correspondientes en un par de registros, tomando la negación de cada bit en un registro.

                Comparar dos valores en registros (por ejemplo, para ver si uno es menor o si son iguales).
                
                Instrucciones de punto flotante para aritmética sobre números de punto flotante.


            Controlar las operaciones de flujo:

                Vaya a otra ubicación del programa y ejecute las instrucciones allí.
                
                Bifurcar condicionalmente a otra ubicación si se cumple una determinada condición.
                
                Ramificar indirectamente a otra ubicación.
                
                Llame a otro bloque de código y guarde la ubicación de la siguiente instrucción como punto al que regresar.


            Instrucciones del coprocesador:

                Cargar/almacenar datos hacia y desde un coprocesador o intercambiarlos con registros de CPU.
                
                Realizar operaciones de coprocesador.


            Instrucciones complejas:

            Los procesadores pueden incluir instrucciones "complejas" en su conjunto de instrucciones. 

            Una sola instrucción "compleja" hace algo que puede requerir muchas instrucciones en otras computadoras. 

            Dichas instrucciones se caracterizan por instrucciones que toman múltiples pasos, controlan múltiples unidades funcionales o aparecen en una escala mayor que la mayor parte de instrucciones simples implementadas por el procesador dado. 

            Algunos ejemplos de instrucciones "complejas" incluyen:

                transferir múltiples registros hacia o desde la memoria (especialmente la pila) a la vez
                
                mover grandes bloques de memoria (por ejemplo, copia de cadena o transferencia DMA)
                
                aritmética complicada de enteros y coma flotante (por ejemplo, raíz cuadrada o funciones trascendentales como logaritmo, seno, coseno, etc.)
                
                Instrucciones SIMD, una sola instrucción que realiza una operación en muchos valores homogéneos en paralelo, posiblemente en registros SIMD dedicados.
                
                realizar una instrucción atómica de prueba y configuración u otra instrucción atómica de lectura, modificación y escritura
                
                Instrucciones que realizan operaciones de ALU con un operando de la memoria en lugar de un registro.

            Las instrucciones complejas son más comunes en los conjuntos de instrucciones CISC que en los conjuntos de instrucciones RISC, pero los conjuntos de instrucciones RISC también pueden incluirlas. 

            Los conjuntos de instrucciones RISC generalmente no incluyen operaciones ALU con operandos de memoria o instrucciones para mover grandes bloques de memoria, pero la mayoría de los conjuntos de instrucciones RISC incluyen instrucciones SIMD o vectoriales que realizan la misma operación aritmética en múltiples datos al mismo tiempo. 

            Las instrucciones SIMD tienen la capacidad de manipular vectores y matrices grandes en un tiempo mínimo. 

            Las instrucciones SIMD permiten una fácil paralelización de algoritmos comúnmente involucrados en el procesamiento de sonido, imágenes y video. 

            Se han lanzado al mercado varias implementaciones de SIMD con nombres comerciales como MMX, 3DNow! y AltiVec.


        Registrar presión:

            La presión de registros mide la disponibilidad de registros libres en cualquier momento durante la ejecución del programa. 

            La presión de registro es alta cuando se utiliza una gran cantidad de registros disponibles; por lo tanto, cuanto mayor sea la presión del registro, más a menudo el contenido del registro deberá derramarse en la memoria. 

            Aumentar el número de registros en una arquitectura disminuye la presión de los registros pero aumenta el costo.

            Mientras que los conjuntos de instrucciones integradas, como Thumb, sufren una presión de registro extremadamente alta porque tienen conjuntos de registros pequeños, los ISA RISC de uso general como MIPS y Alpha disfrutan de una presión de registro baja. 

            Los ISA CISC como x86-64 ofrecen una presión de registro baja a pesar de tener conjuntos de registros más pequeños.

            Esto se debe a los numerosos modos de direccionamiento y optimizaciones (como direccionamiento de subregistro, operandos de memoria en instrucciones ALU, direccionamiento absoluto, direccionamiento relativo a PC y derrames de registro a registro) que ofrecen los CISC ISA.


        Longitud de la instrucción:

            El tamaño o la longitud de una instrucción varía ampliamente, desde tan solo cuatro bits en algunos microcontroladores hasta muchos cientos de bits en algunos sistemas VLIW.

            Los procesadores utilizados en computadoras personales, mainframes y supercomputadoras tienen tamaños de instrucción mínimos entre 8 y 64 bits. 

            La instrucción más larga posible en x86 es de 15 bytes (120 bits). 

            Dentro de un conjunto de instrucciones, diferentes instrucciones pueden tener diferentes longitudes. 

            En algunas arquitecturas, en particular en la mayoría de las computadoras con conjunto de instrucciones reducido (RISC), las instrucciones tienen una longitud fija, que generalmente se corresponde con el tamaño de palabra de esa arquitectura. 

            En otras arquitecturas, las instrucciones tienen una longitud variable, normalmente múltiplos integrales/enteros de un byte o media palabra. 

            Algunos, como ARM con extensión Thumb, tienen codificación variable mixta, es decir, dos codificaciones fijas, generalmente de 32 y 16 bits, donde las instrucciones no se pueden mezclar libremente sino que se deben alternar en una rama (o límite de excepción en ARMv8).

            Las instrucciones de longitud fija son menos complicadas de manejar que las de longitud variable por varias razones (por ejemplo, no tener que comprobar si una instrucción se extiende a lo largo de una línea de caché o de un límite de página de memoria virtual) y, por lo tanto, son algo más fáciles de optimizar para lograr velocidad.


        Densidad de código:

            A principios de la década de 1960, la memoria principal era cara y muy limitada, incluso en los mainframes. 

            Minimizar el tamaño de un programa para asegurarse de que encajara en la memoria limitada era a menudo fundamental. 

            Por tanto, el tamaño de las instrucciones necesarias para realizar una tarea particular, la densidad del código, era una característica importante de cualquier conjunto de instrucciones. 

            Siguió siendo importante en las memorias inicialmente pequeñas de las minicomputadoras y luego de los microprocesadores. 

            La densidad sigue siendo importante hoy en día, para aplicaciones de teléfonos inteligentes, aplicaciones descargadas en navegadores a través de conexiones lentas a Internet y en ROM para aplicaciones integradas.

            Una ventaja más general de una mayor densidad es la eficacia mejorada de las cachés y la captación previa de instrucciones.

            Las computadoras con alta densidad de código a menudo tienen instrucciones complejas para la entrada de procedimientos, retornos parametrizados, bucles, etc. (por lo que retroactivamente se denominan Computadoras con conjunto de instrucciones complejas, CISC). 

            Sin embargo, las instrucciones "CISC" más típicas o frecuentes simplemente combinan una operación ALU básica, como "agregar", con el acceso de uno o más operandos en la memoria (usando modos de direccionamiento como directo, indirecto, indexado, etc.) . 

            Ciertas arquitecturas pueden permitir dos o tres operandos (incluido el resultado) directamente en la memoria o pueden realizar funciones como el incremento automático del puntero, etc. 

            Los conjuntos de instrucciones implementados por software pueden tener instrucciones aún más complejas y potentes.

            Las computadoras con conjunto de instrucciones reducido, RISC, se implementaron ampliamente por primera vez durante un período de subsistemas de memoria en rápido crecimiento. 

            Sacrifican la densidad del código para simplificar los circuitos de implementación e intentan aumentar el rendimiento mediante frecuencias de reloj más altas y más registros.

            Una única instrucción RISC normalmente realiza una sola operación, como "agregar" registros o "cargar" desde una ubicación de memoria a un registro. 

            Un conjunto de instrucciones RISC normalmente tiene una longitud de instrucción fija, mientras que un conjunto de instrucciones CISC típico tiene instrucciones de longitud muy variable. 

            Sin embargo, como las computadoras RISC normalmente requieren más instrucciones y a menudo más largas para implementar una tarea determinada, inherentemente hacen un uso menos óptimo del ancho de banda del bus y de las memorias caché.

            Ciertos RISC ISA integrados, como Thumb y AVR32, suelen exhibir una densidad muy alta debido a una técnica llamada compresión de código.

            Esta técnica empaqueta dos instrucciones de 16 bits en una palabra de 32 bits, que luego se descomprime en la etapa de decodificación y se ejecuta como dos instrucciones.

            Las computadoras con conjunto mínimo de instrucciones (MISC) son comúnmente una forma de máquina apilada, donde hay pocas instrucciones separadas (8 a 32), de modo que se pueden colocar varias instrucciones en una sola palabra de máquina. 

            Estos tipos de núcleos a menudo requieren poco silicio para implementarse, por lo que se pueden realizar fácilmente en una FPGA o en forma de múltiples núcleos. 

            La densidad de código de MISC es similar a la densidad de código de RISC; el aumento de la densidad de instrucción se compensa al requerir más instrucciones primitivas para realizar una tarea.

            Se han realizado investigaciones sobre la compresión ejecutable como mecanismo para mejorar la densidad del código. 

            Las matemáticas de la complejidad de Kolmogorov describen los desafíos y límites de esta.

            En la práctica, la densidad del código también depende del compilador. 

            La mayoría de los compiladores de optimización tienen opciones que controlan si se optimiza la generación de código para la velocidad de ejecución o para la densidad del código. 

            Por ejemplo, GCC tiene la opción -Os para optimizar el tamaño del código de máquina pequeño y -O3 para optimizar la velocidad de ejecución a costa de un código de máquina más grande.


        Representación:

            Las instrucciones que constituyen un programa rara vez se especifican utilizando su forma numérica interna (código de máquina); pueden ser especificados por programadores que utilizan un lenguaje ensamblador o, más comúnmente, pueden ser generados a partir de lenguajes de programación de alto nivel por parte de compiladores.


        Diseño:

            El diseño de conjuntos de instrucciones es un tema complejo. 

            Hubo dos etapas en la historia del microprocesador. 

            El primero fue el CISC (Computadora con conjunto de instrucciones complejas), que tenía muchas instrucciones diferentes. 

            Sin embargo, en la década de 1970, empresas como IBM investigaron y descubrieron que muchas instrucciones del conjunto podían eliminarse. 

            El resultado fue el RISC (Computadora con conjunto de instrucciones reducido), una arquitectura que utiliza un conjunto más pequeño de instrucciones. 

            Un conjunto de instrucciones más simple puede ofrecer la posibilidad de lograr velocidades más altas, un tamaño de procesador reducido y un consumo de energía reducido. 

            Sin embargo, un conjunto más complejo puede optimizar las operaciones comunes, mejorar la eficiencia de la memoria y la caché o simplificar la programación.

            Algunos diseñadores de conjuntos de instrucciones reservan uno o más códigos de operación para algún tipo de llamada al sistema o interrupción del software. 

            Por ejemplo, MOS Technology 6502 usa 00H, Zilog Z80 usa los ocho códigos C7,CF,D7,DF,E7,EF,F7,FFH mientras que Motorola 68000 usa códigos en el rango A000..AFFFH.

            Las máquinas virtuales rápidas son mucho más fáciles de implementar si un conjunto de instrucciones cumple con los requisitos de virtualización de Popek y Goldberg.

            La diapositiva NOP utilizada en la programación consciente de la inmunidad es mucho más fácil de implementar si el estado "no programado" de la memoria se interpreta como un NOP.

            En sistemas con múltiples procesadores, los algoritmos de sincronización sin bloqueo son mucho más fáciles de implementar si el conjunto de instrucciones incluye soporte para algo como "buscar y agregar", "enlace de carga/almacenamiento condicional" (LL/ SC), o "comparación e intercambio atómico".


        Implementación del conjunto de instrucciones:

            Un conjunto de instrucciones determinado se puede implementar de diversas formas. 

            Todas las formas de implementar un conjunto de instrucciones en particular proporcionan el mismo modelo de programación y todas las implementaciones de ese conjunto de instrucciones pueden ejecutar los mismos ejecutables. 

            Las diversas formas de implementar un conjunto de instrucciones ofrecen diferentes compensaciones entre costo, rendimiento, consumo de energía, tamaño, etc.

            Al diseñar la microarquitectura de un procesador, los ingenieros utilizan bloques de circuitos electrónicos "cableados" (a menudo diseñados por separado), como sumadores, multiplexores, contadores, registros, ALU, etc. 

            A menudo se utiliza algún tipo de lenguaje de transferencia de registros para describir la decodificación y secuenciación de cada instrucción de un ISA utilizando esta microarquitectura física.

            Hay dos formas básicas de construir una unidad de control para implementar esta descripción (aunque muchos diseños utilizan formas intermedias o compromisos):

                Algunos diseños de computadora "conectan" el conjunto completo de instrucciones decodificadas y secuenciadas (al igual que el resto de la microarquitectura).
                 
                Otros diseños emplean rutinas o tablas de microcódigo (o ambas) para hacer esto, usando ROM o RAM grabables (almacén de control grabable), PLA o ambos.

            Algunos diseños de CPU microcodificados con un almacén de control grabable lo utilizan para permitir cambiar el conjunto de instrucciones (por ejemplo, el procesador Rekursiv y el Imsys Cjip).

            Las CPU diseñadas para informática reconfigurable pueden utilizar matrices de puertas programables en campo (FPGA).

            Un intérprete también puede emular una ISA en software. 

            Naturalmente, debido a la sobrecarga de interpretación, esto es más lento que ejecutar programas directamente en el hardware emulado, a menos que el hardware que ejecuta el emulador sea un orden de magnitud más rápido. 

            Hoy en día, es una práctica común que los proveedores de nuevas ISA o microarquitecturas pongan emuladores de software a disposición de los desarrolladores de software antes de que la implementación del hardware esté lista.

            A menudo, los detalles de la implementación tienen una fuerte influencia en las instrucciones particulares seleccionadas para el conjunto de instrucciones. 

            Por ejemplo, muchas implementaciones de la canalización de instrucciones solo permiten una única carga de memoria o almacenamiento de memoria por instrucción, lo que lleva a una arquitectura de almacenamiento de carga (RISC). 

            Para poner otro ejemplo, algunas de las primeras formas de implementar el proceso de instrucción condujeron a un intervalo de retraso.

            Las demandas del procesamiento de señales digitales de alta velocidad han ido en la dirección opuesta: obligando a que las instrucciones se implementen de una manera particular. 

            Por ejemplo, para realizar filtros digitales lo suficientemente rápido, la instrucción MAC en un procesador de señal digital (DSP) típico debe utilizar una especie de arquitectura Harvard que pueda recuperar una instrucción y dos palabras de datos simultáneamente, y requiere un proceso de multiplicación-acumulación de un solo ciclo. multiplicador.


    Arquitectura: 

        En informática e ingeniería informática, la arquitectura informática es una descripción de la estructura de un sistema informático hecha de componentes. 

        A veces puede ser una descripción de alto nivel que ignora los detalles de la implementación. 

        En un nivel más detallado, la descripción puede incluir el diseño de la arquitectura del conjunto de instrucciones, el diseño de la microarquitectura, el diseño lógico y la implementación.


        Diagrama: 

            CPU: 

                Control Unit (CU)

                Arithmetic and Logical Unit (ALU)

                Register


            Memoria principal

                RAM 


            Memoría secundaria

                Almacenamiento 


            Dispositivos de entrada y salida.  


            La CPU contrala el flujo de flujo de CU, ALU, RAM, almacenamiento e I/O mientras estos controlan la data o instrucciónes. 


        Historia: 

            La primera arquitectura informática documentada se encuentra en la correspondencia entre Charles Babbage y Ada Lovelace, describiendo el motor analítico. 

            Mientras construía el ordenador Z1 en 1936, Konrad Zuse describió en dos solicitudes de patente para sus proyectos futuros que las instrucciones de la máquina podrían almacenarse en el mismo almacenamiento que se utiliza para los datos, es decir, el concepto de programa almacenado.

            Otros dos ejemplos tempranos e importantes son:

                 El artículo de John von Neumann de 1945, Primer borrador de un informe sobre el EDVAC, que describía una organización de elementos lógicos; y
                 Calculadora electrónica propuesta más detallada de Alan Turing para el motor de computación automática, también de 1945 y que citaba el artículo de John von Neumann.

            El término "arquitectura" en la literatura informática se remonta al trabajo de Lyle R. Johnson y Frederick P. Brooks, Jr., miembros del departamento de Organización de Máquinas del principal centro de investigación de IBM en 1959. 

            Johnson tuvo la oportunidad de escribir un diseño patentado, comunicación de investigación sobre Stretch, una supercomputadora desarrollada por IBM para el Laboratorio Nacional de Los Alamos (en ese momento conocido como Laboratorio Científico de Los Alamos). 

            Para describir el nivel de detalle para hablar de la computadora lujosamente adornada, señaló que su descripción de formatos, tipos de instrucciones, parámetros de hardware y mejoras de velocidad estaban al nivel de "arquitectura del sistema", un término que parecía más útil que "organización de la máquina". ".

            Posteriormente, Brooks, un diseñador de Stretch, abrió el capítulo 2 de un libro llamado Planificación de un sistema informático: Proyecto Stretch afirmando: "La arquitectura informática, como cualquier otra arquitectura, es el arte de determinar las necesidades del usuario de una estructura y luego diseñar para satisfacerlas", satisfacer esas necesidades tan eficazmente como sea posible dentro de las limitaciones económicas y tecnológicas."

            Brooks ayudó a desarrollar la línea de computadoras IBM System/360 (ahora llamada IBM zSeries), en la que "arquitectura" se convirtió en un sustantivo que definía "lo que el usuario necesita saber". 

            Más tarde, los usuarios de ordenadores empezaron a utilizar el término de formas mucho menos explícitas.

            Las primeras arquitecturas informáticas se diseñaron en papel y luego se integraron directamente en el formato de hardware final. 

            Más tarde, los prototipos de arquitectura informática se construyeron físicamente en forma de computadora con lógica transistor-transistor (TTL), como los prototipos del 6800 y el PA-RISC, probados y ajustados antes de comprometerse con la forma final del hardware. 

            A partir de la década de 1990, las nuevas arquitecturas informáticas suelen "construirse", probarse y modificarse, dentro de alguna otra arquitectura informática en un simulador de arquitectura informática; o dentro de una FPGA como un microprocesador suave; o ambos, antes de comprometerse con la forma final del hardware


        Subconceptos: 

            La disciplina de la arquitectura informática tiene tres subcategorías principales:

            Arquitectura de conjunto de instrucciones (ISA):

                Define el código de máquina que un procesador lee y sobre el que actúa, así como el tamaño de la palabra, los modos de dirección de la memoria, los registros del procesador y el tipo de datos.
             

            Microarquitectura:

                También conocida como "organización informática", describe cómo un procesador particular implementará la ISA.

                El tamaño de la memoria caché de la CPU de una computadora, por ejemplo, es un problema que generalmente no tiene nada que ver con ISA.
             

            Diseño de sistemas:

                Incluye todos los demás componentes de hardware dentro de un sistema informático, como el procesamiento de datos distintos de la CPU (por ejemplo, acceso directo a la memoria), la virtualización y el multiprocesamiento.


            Existen otras tecnologías en la arquitectura informática. 

            Las siguientes tecnologías se utilizan en empresas más grandes como Intel, y en 2002 se estimó que representaban el 1% de toda la arquitectura informática:


            Macroarquitectura: 

                Capas arquitectónicas más abstractas que la microarquitectura
                 

            Arquitectura del conjunto de instrucciones ensamblador: 

                Un ensamblador inteligente puede convertir un lenguaje ensamblador abstracto común a un grupo de máquinas en un lenguaje de máquina ligeramente diferente para diferentes implementaciones.
                

            Macroarquitectura visible para el programador: 

                Las herramientas de lenguaje de nivel superior, como los compiladores, pueden definir una interfaz consistente o contratar a los programadores que las usan, abstrayendo las diferencias entre ISA, UISA y microarquitecturas subyacentes. 

                Por ejemplo, los estándares C, C++ o Java definen diferentes macroarquitecturas visibles para el programador.
             

            Microcódigo: 

                El microcódigo es un software que traduce instrucciones para ejecutarlas en un chip. 

                Actúa como un envoltorio alrededor del hardware, presentando una versión preferida de la interfaz del conjunto de instrucciones del hardware. 

                Esta función de traducción de instrucciones ofrece a los diseñadores de chips opciones flexibles:

                p. 1. Una nueva versión mejorada del chip puede usar microcódigo para presentar exactamente el mismo conjunto de instrucciones que la versión anterior del chip, por lo que todo el software destinado a ese conjunto de instrucciones se ejecutará en el nuevo chip sin necesidad de cambios. 

                P.ej. 2. El microcódigo puede presentar una variedad de conjuntos de instrucciones para el mismo chip subyacente, lo que le permite ejecutar una variedad más amplia de software.
             

            UISA: 

                Arquitectura del conjunto de instrucciones del usuario, se refiere a uno de los tres subconjuntos de instrucciones de la CPU RISC proporcionadas por los procesadores RISC PowerPC. 

                El subconjunto UISA son aquellas instrucciones RISC de interés para los desarrolladores de aplicaciones. 

                Los otros dos subconjuntos son instrucciones VEA (Arquitectura de entorno virtual) utilizadas por los desarrolladores de sistemas de virtualización y OEA (Arquitectura de entorno operativo) utilizadas por los desarrolladores de sistemas operativos.
            

            Arquitectura de pines:

                Las funciones de hardware que un microprocesador debe proporcionar a una plataforma de hardware, por ejemplo, los pines x86 A20M, FERR/IGNNE o FLUSH. 

                Además, mensajes que el procesador debería emitir para que las cachés externas puedan ser invalidadas (vaciadas). 

                Las funciones de arquitectura de pines son más flexibles que las funciones ISA porque el hardware externo puede adaptarse a nuevas codificaciones o cambiar de un pin a un mensaje. 

                El término "arquitectura" encaja, porque las funciones deben estar previstas para sistemas compatibles, incluso si cambia el método detallado.


            Roles:

            La arquitectura informática se ocupa de equilibrar el rendimiento, la eficiencia, el costo y la confiabilidad de un sistema informático. 

            El caso de la arquitectura del conjunto de instrucciones se puede utilizar para ilustrar el equilibrio de estos factores en competencia.

            Conjuntos de instrucciones más complejos permiten a los programadores escribir programas más eficientes en cuanto a espacio, ya que una sola instrucción puede codificar alguna abstracción de nivel superior (como la instrucción Loop x86).

            Sin embargo, el procesador necesita más tiempo para decodificar instrucciones más largas y complejas y su implementación efectiva puede ser más costosa. 

            La mayor complejidad de un conjunto de instrucciones grande también crea más espacio para la falta de confiabilidad cuando las instrucciones interactúan de maneras inesperadas.

            La implementación implica diseño de circuitos integrados, empaquetado, alimentación y refrigeración. 

            La optimización del diseño requiere familiaridad con los compiladores, los sistemas operativos, el diseño lógico y el empaquetado.


            Set de instrucciones arquitectura:

            La arquitectura del conjunto de instrucciones (ISA) es la interfaz entre el software y el hardware de la computadora y también puede verse como la vista de la máquina por parte del programador. 

            Las computadoras no entienden los lenguajes de programación de alto nivel como Java, C++ o la mayoría de los lenguajes de programación utilizados. 

            Un procesador sólo entiende instrucciones codificadas de alguna forma numérica, normalmente como números binarios. 

            Las herramientas de software, como los compiladores, traducen esos lenguajes de alto nivel en instrucciones que el procesador puede entender.

            Además de las instrucciones, la ISA define elementos en la computadora que están disponibles para un programa, por ejemplo, tipos de datos, registros, modos de direccionamiento y memoria. 

            Las instrucciones localizan estos elementos disponibles con índices de registro (o nombres) y modos de direccionamiento de memoria.

            La ISA de una computadora generalmente se describe en un pequeño manual de instrucciones, que describe cómo se codifican las instrucciones. 

            Además, puede definir nombres mnemotécnicos cortos (vagos) para las instrucciones. 

            Los nombres pueden reconocerse mediante una herramienta de desarrollo de software llamada ensamblador. 

            Un ensamblador es un programa informático que traduce una forma legible por humanos de ISA a una forma legible por computadora. 

            Los desensambladores también están ampliamente disponibles, generalmente en depuradores y programas de software para aislar y corregir fallas en programas informáticos binarios.

            Las NIA varían en calidad e integridad. 

            Un buen ISA logra compromisos entre la conveniencia del programador (qué tan fácil es entender el código), el tamaño del código (cuánto código se requiere para realizar una acción específica), el costo de la computadora para interpretar las instrucciones (más complejidad significa más hardware necesario para decodificar y ejecutar las instrucciones) y la velocidad de la computadora (con un hardware de decodificación más complejo el tiempo de decodificación es mayor).

            La organización de la memoria define cómo las instrucciones interactúan con la memoria y cómo la memoria interactúa consigo misma.

            Durante la emulación del diseño, los emuladores pueden ejecutar programas escritos en un conjunto de instrucciones propuesto. 

            Los emuladores modernos pueden medir el tamaño, el costo y la velocidad para determinar si una ISA en particular está cumpliendo sus objetivos.


            Organización de computadoras:

            La organización informática ayuda a optimizar los productos basados en el rendimiento. 

            Por ejemplo, los ingenieros de software necesitan conocer la potencia de procesamiento de los procesadores. 

            Es posible que necesiten optimizar el software para obtener el máximo rendimiento al precio más bajo. 

            Esto puede requerir un análisis bastante detallado de la organización de la computadora. 

            Por ejemplo, en una tarjeta SD, es posible que los diseñadores necesiten organizar la tarjeta de manera que se pueda procesar la mayor cantidad de datos de la manera más rápida posible.

            La organización informática también ayuda a planificar la selección de un procesador para un proyecto en particular.

            Los proyectos multimedia pueden necesitar un acceso a datos muy rápido, mientras que las máquinas virtuales pueden necesitar interrupciones rápidas. 

            A veces, determinadas tareas también necesitan componentes adicionales.

            Por ejemplo, una computadora capaz de ejecutar una máquina virtual necesita hardware de memoria virtual para que la memoria de diferentes computadoras virtuales pueda mantenerse separada. 

            La organización y las características de la computadora también afectan el consumo de energía y el costo del procesador.


        Implementación:

            Una vez que se han diseñado un conjunto de instrucciones y una microarquitectura, se debe desarrollar una máquina práctica. 

            Este proceso de diseño se llama implementación. 

            La implementación generalmente no se considera diseño arquitectónico, sino ingeniería de diseño de hardware. 

            La implementación se puede dividir en varios pasos:

                La implementación lógica diseña los circuitos necesarios a nivel de puerta lógica.
                 

                La implementación de circuitos realiza diseños a nivel de transistor de elementos básicos (por ejemplo, compuertas, multiplexores, pestillos), así como de algunos bloques más grandes (ALU, cachés, etc.) que pueden implementarse en el nivel de puerta lógica o incluso en el nivel físico. si el diseño lo requiere.
                

                La implementación física dibuja circuitos físicos. Los diferentes componentes del circuito se colocan en un plano de chip o en un tablero y se crean los cables que los conectan.
                

                La validación del diseño prueba la computadora en su conjunto para ver si funciona en todas las situaciones y en todos los momentos. Una vez que comienza el proceso de validación del diseño, el diseño a nivel lógico se prueba utilizando emuladores lógicos. Sin embargo, esto suele ser demasiado lento para ejecutar una prueba realista. Entonces, después de hacer correcciones basadas en la primera prueba, los prototipos se construyen utilizando matrices de puertas programables en campo (FPGA). La mayoría de los proyectos de hobby terminan en esta etapa. El último paso es probar prototipos de circuitos integrados, lo que puede requerir varios rediseños.

            Para las CPU, todo el proceso de implementación se organiza de manera diferente y a menudo se lo denomina diseño de CPU.


        Objetivos de diseño: 

        La forma exacta de un sistema informático depende de las limitaciones y objetivos. 

        Las arquitecturas informáticas suelen equilibrar estándares, potencia frente a rendimiento, coste, capacidad de memoria, latencia (la latencia es la cantidad de tiempo que tarda la información de un nodo en viajar hasta la fuente) y rendimiento. 

        A veces, otras consideraciones, como las características, el tamaño, el peso, la confiabilidad y la capacidad de expansión, también son factores.

        El esquema más común realiza un análisis de energía en profundidad y descubre cómo mantener bajo el consumo de energía mientras se mantiene un rendimiento adecuado.


        Performance:

            El rendimiento de las computadoras modernas a menudo se describe en instrucciones por ciclo (IPC), que mide la eficiencia de la arquitectura en cualquier frecuencia de reloj; una tasa de IPC más rápida significa que la computadora es más rápida. 

            Las computadoras más antiguas tenían recuentos de IPC tan bajos como 0,1, mientras que los procesadores modernos alcanzan fácilmente casi 1. 

            Los procesadores superescalares pueden alcanzar de tres a cinco IPC ejecutando varias instrucciones por ciclo de reloj.

            Contar instrucciones en lenguaje de máquina sería engañoso porque pueden realizar diferentes cantidades de trabajo en diferentes ISA. 

            La "instrucción" en las medidas estándar no es un recuento de las instrucciones en lenguaje de máquina del ISA, sino una unidad de medida, generalmente basada en la velocidad de la arquitectura de la computadora VAX.

            Mucha gente solía medir la velocidad de una computadora mediante la frecuencia del reloj (generalmente en MHz o GHz). 

            Esto se refiere a los ciclos por segundo del reloj principal de la CPU. 

            Sin embargo, esta métrica es algo engañosa, ya que una máquina con una frecuencia de reloj más alta no necesariamente tiene un mayor rendimiento. 

            Como resultado, los fabricantes se han alejado de la velocidad del reloj como medida de rendimiento.

            Otros factores influyen en la velocidad, como la combinación de unidades funcionales, las velocidades del bus, la memoria disponible y el tipo y orden de las instrucciones en los programas.

            Hay dos tipos principales de velocidad: latencia y rendimiento. 

            La latencia es el tiempo entre el inicio de un proceso y su finalización. 

            El rendimiento es la cantidad de trabajo realizado por unidad de tiempo. 

            La latencia de interrupción es el tiempo de respuesta máximo garantizado del sistema ante un evento electrónico (como cuando la unidad de disco termina de mover algunos datos).

            El rendimiento se ve afectado por una amplia gama de opciones de diseño; por ejemplo, la canalización de un procesador generalmente empeora la latencia, pero mejora el rendimiento.

            Las computadoras que controlan maquinaria generalmente necesitan latencias de interrupción bajas. 

            Estas computadoras operan en un entorno de tiempo real y fallan si una operación no se completa en un período de tiempo específico. 

            Por ejemplo, los frenos antibloqueo controlados por computadora deben comenzar a frenar dentro de un período de tiempo predecible y limitado después de que se detecta el pedal del freno o, de lo contrario, se producirá una falla en el freno.

            La evaluación comparativa tiene en cuenta todos estos factores midiendo el tiempo que tarda una computadora en ejecutar una serie de programas de prueba. 

            Aunque la evaluación comparativa muestra puntos fuertes, no debería depender de la forma en que se elige una computadora. 

            A menudo las máquinas medidas se dividen en medidas diferentes. 

            Por ejemplo, un sistema podría manejar aplicaciones científicas rápidamente, mientras que otro podría reproducir videojuegos con mayor fluidez. 

            Además, los diseñadores pueden apuntar y agregar características especiales a sus productos, a través de hardware o software, que permitan ejecutar rápidamente un punto de referencia específico pero que no ofrezcan ventajas similares a las tareas generales.


        Eficiencia energetica:

            La eficiencia energética es otra medida importante en las computadoras modernas.

            A menudo se puede intercambiar una mayor eficiencia energética por una menor velocidad o un mayor costo. 

            La medida típica cuando se hace referencia al consumo de energía en la arquitectura de computadoras es MIPS/W (millones de instrucciones por segundo por vatio).

            Los circuitos modernos requieren menos energía por transistor a medida que crece el número de transistores por chip.

            Esto se debe a que cada transistor que se coloca en un nuevo chip requiere su propia fuente de alimentación y requiere la construcción de nuevas vías para alimentarlo.

            Sin embargo, el número de transistores por chip está empezando a aumentar a un ritmo más lento. 

            Por lo tanto, la eficiencia energética está empezando a ser tan importante, si no más, que colocar más y más transistores en un solo chip. 

            Los diseños de procesadores recientes han mostrado este énfasis, ya que se centran más en la eficiencia energética en lugar de meter tantos transistores en un solo chip como sea posible. 

            En el mundo de las computadoras integradas, la eficiencia energética ha sido durante mucho tiempo un objetivo importante junto al rendimiento y la latencia.


        Cambios en la demanda del mercado:

            Los aumentos en la frecuencia del reloj han crecido más lentamente en los últimos años, en comparación con las mejoras en la reducción de energía. 

            Esto ha sido impulsado por el fin de la Ley de Moore y la demanda de una mayor duración de la batería y reducciones de tamaño para la tecnología móvil. 

            Este cambio de enfoque de velocidades de reloj más altas al consumo de energía y miniaturización se puede mostrar en las reducciones significativas en el consumo de energía, hasta un 50%, que informó Intel en su lanzamiento de la microarquitectura Haswell; donde redujeron su punto de referencia de consumo de energía de 30 a 40 vatios a 10-20 vatios. 

            Comparando esto con el aumento de la velocidad de procesamiento de 3 GHz a 4 GHz (2002 a 2006), se puede ver que el enfoque en investigación y desarrollo se está alejando de la frecuencia del reloj y avanzando hacia un consumo menor de energía y ocupando menos espacio.


        32-bits:    

            Se refiere a sistemas informáticos con procesador, memoria y otros componentes importantes del sistema que operan con datos en unidades de 32 bits.

            En comparación con anchos de bits más pequeños, las computadoras de 32 bits pueden realizar cálculos grandes de manera más eficiente y procesar más datos por ciclo de reloj.

            Las computadoras personales típicas de 32 bits también tienen un bus de direcciones de 32 bits, lo que permite acceder a hasta 4 GB de RAM, mucho más de lo que permitían las generaciones anteriores de arquitectura de sistemas.

            Los diseños de 32 bits se han utilizado desde los primeros días de la informática electrónica, en sistemas experimentales y luego en grandes sistemas mainframe y minicomputadores. 

            El primer microprocesador híbrido de 16/32 bits, el Motorola 68000, se introdujo a finales de la década de 1970 y se utilizó en sistemas como el Apple Macintosh original. 

            Los microprocesadores totalmente de 32 bits, como HP FOCUS, Motorola 68020 e Intel 80386, se lanzaron entre principios y mediados de los años 1980 y se volvieron dominantes a principios de los años 1990. 

            Esta generación de computadoras personales coincidió con la primera adopción masiva de la World Wide Web y la permitió. 

            Si bien las arquitecturas de 32 bits todavía se utilizan ampliamente en aplicaciones específicas, el mercado de PC y servidores ha pasado a 64 bits con x86-64 desde mediados de la década de 2000, con una memoria instalada que a menudo excede los límites de direcciones RAM 4G de 32 bits en el nivel de entrada de ordenadores. 

            La última generación de móviles también pasa a los 64 bits.


            Rango para almacenar números enteros:

                Un registro de 32 bits puede almacenar 2^32 valores diferentes. 

                El rango de valores enteros que se pueden almacenar en 32 bits depende de la representación entera utilizada. 

                Con las dos representaciones más comunes, el rango es de 0 a 4.294.967.295 (2^32 - 1) para la representación como un número binario (sin signo), y de -2.147.483.648 (-2^31) a 2.147.483.647 (2^31 - 1) para la representación como complemento a dos.

                Una consecuencia importante es que un procesador con direcciones de memoria de 32 bits puede acceder directamente como máximo a 4 GiB de memoria direccionable por bytes (aunque en la práctica el límite puede ser menor).


            Historia tecnica

                La primera computadora electrónica con programa almacenado del mundo, la Manchester Baby, utilizó una arquitectura de 32 bits en 1948, aunque era sólo una prueba de concepto y tenía poca capacidad práctica. 

                Contenía sólo 32 palabras de 32 bits de RAM en un tubo Williams y no tenía operación de suma, solo resta.

                La memoria, así como otros circuitos y cableado digitales, eran caras durante las primeras décadas de las arquitecturas de 32 bits (de los años 1960 a los 1980). 

                Por lo tanto, las familias de procesadores de 32 bits más antiguas (o variantes más simples y económicas de las mismas) podrían tener muchos compromisos y limitaciones para reducir costos.

                Podría ser una ALU de 16 bits, por ejemplo, o buses externos (o internos) de menos de 32 bits, lo que limita el tamaño de la memoria o exige más ciclos para la búsqueda, ejecución o reescritura de instrucciones.

                A pesar de esto, dichos procesadores podrían etiquetarse como de 32 bits, ya que todavía tenían registros de 32 bits e instrucciones capaces de manipular cantidades de 32 bits. 

                Por ejemplo, el IBM System/360 Modelo 30 tenía una ALU de 8 bits, rutas de datos internas de 8 bits y una ruta de memoria de 8 bits, y el Motorola 68000 original tenía una ALU de datos de 16 bits y una ruta de 16 bits. 

                bus de datos externo, pero tenía registros de 32 bits y un conjunto de instrucciones orientadas a 32 bits.

                El diseño 68000 a veces se denominaba 16/32 bits.

                Sin embargo, suele ocurrir lo contrario con los diseños más nuevos de 32 bits.

                Por ejemplo, el procesador Pentium Pro es una máquina de 32 bits, con registros de 32 bits e instrucciones que manipulan cantidades de 32 bits, pero el bus de direcciones externo tiene 36 bits de ancho, lo que proporciona un espacio de direcciones mayor que 4 GB, y el procesador externo tiene 36 bits de ancho, lo que proporciona un espacio de direcciones mayor que 4 GB. 

                El bus de datos tiene 64 bits de ancho, principalmente para permitir una captación previa más eficiente de instrucciones y datos.


            Arquitecturas:
                
                Las arquitecturas de conjuntos de instrucciones de 32 bits más destacadas utilizadas en la informática de propósito general incluyen IBM System/360 e IBM System/370 (que tenían direccionamiento de 24 bits) y System/370-XA, ESA/370 y ESA/390 (que tenía direccionamiento de 31 bits), el DEC VAX, el NS320xx, la familia Motorola 68000 (cuyos dos primeros modelos tenían direccionamiento de 24 bits), la versión Intel IA-32 de 32 bits de la arquitectura x86 y el direccionamiento de 32 bits versiones de bits de las arquitecturas ARM,[8] SPARC, MIPS, PowerPC y PA-RISC. 

                Las arquitecturas de conjuntos de instrucciones de 32 bits utilizadas para la informática integrada incluyen la familia 68000 y las arquitecturas ColdFire, x86, ARM, MIPS, PowerPC e Infineon TriCore.


        64-bits:

            En la arquitectura informática, los números enteros de 64 bits, las direcciones de memoria u otras unidades de datos son aquellas que tienen 64 bits de ancho.

            Asimismo, las unidades centrales de procesamiento (CPU) y unidades lógicas aritméticas (ALU) de 64 bits son aquellas que se basan en registros de procesador, buses de direcciones o buses de datos de ese tamaño. 

            Una computadora que utiliza dicho procesador es una computadora de 64 bits.

            Desde la perspectiva del software, la informática de 64 bits significa el uso de código de máquina con direcciones de memoria virtual de 64 bits. 

            Sin embargo, no todos los conjuntos de instrucciones de 64 bits admiten direcciones de memoria virtual completas de 64 bits; x86-64 y AArch64, por ejemplo, admiten solo 48 bits de dirección virtual, y los 16 bits restantes de la dirección virtual deben ser todo ceros (000...) o todos unos (111...), y varios bits de 64 bits.

            Los conjuntos de instrucciones de bits admiten menos de 64 bits de dirección de memoria física.

            El término 64 bits también describe una generación de computadoras en las que los procesadores de 64 bits son la norma. 

            64 bits es un tamaño de palabra que define ciertas clases de arquitectura de computadora, buses, memoria y CPU y, por extensión, el software que se ejecuta en ellos.

            Las CPU de 64 bits se han utilizado en supercomputadoras desde la década de 1970 (Cray-1, 1975) y en estaciones de trabajo y servidores basados en computadoras con conjunto de instrucciones reducido (RISC) desde principios de la década de 1990. 

            En 2003, las CPU de 64 bits se introdujeron en el mercado general de PC en forma de procesadores x86-64 y el PowerPC G5.

            Un registro de 64 bits puede contener cualquiera de 2^64 (más de 18 quintillones o 1,8 × 10^19) valores diferentes. 

            El rango de valores enteros que se pueden almacenar en 64 bits depende de la representación entera utilizada. 

            Con las dos representaciones más comunes, el rango es de 0 a 18.446.744.073.709.551.615 (igual a 2^64 − 1) para la representación como un número binario (sin signo), y de −9.223.372.036.854.775.808 (−2^63) a 9.223.372.036.854.775.80 7 (2^63 − 1) para representación como complemento a dos. 

            Por lo tanto, un procesador con direcciones de memoria de 64 bits puede acceder directamente a 2^64 bytes (16 exbibytes o EiB) de memoria direccionable por bytes.

            Sin más calificaciones, una arquitectura de computadora de 64 bits generalmente tiene registros de números enteros y de direccionamiento de 64 bits de ancho, lo que permite soporte directo para tipos de datos y direcciones de 64 bits.

            Sin embargo, una CPU podía tener buses de datos externos o buses de direcciones con diferentes tamaños de registros, incluso mayores (el Pentium de 32 bits tenía un bus de datos de 64 bits, por ejemplo).


            Historia: 

                Muchos conjuntos de instrucciones de computadora están diseñados para que un único registro entero pueda almacenar la dirección de memoria en cualquier ubicación de la memoria física o virtual de la computadora. 

                Por lo tanto, el número total de direcciones en la memoria suele estar determinado por el ancho de estos registros. 

                El IBM System/360 de la década de 1960 fue uno de los primeros ordenadores de 32 bits; tenía registros enteros de 32 bits, aunque solo usaba los 24 bits de orden inferior de una palabra para las direcciones, lo que daba como resultado un espacio de direcciones de 16 MiB (16 × 1024^2 bytes).

                Las superminicomputadoras de 32 bits, como la DEC VAX, se hicieron comunes en la década de 1970, y los microprocesadores de 32 bits, como la familia Motorola 68000 y los miembros de 32 bits de la familia x86 comenzando con el Intel 80386, aparecieron a mediados de la década de 1970, década de 1980, lo que convirtió a 32 bits en una especie de consenso de facto como tamaño de registro conveniente.

                Un registro de direcciones de 32 bits significaba que se podía hacer referencia a 232 direcciones, o 4 GiB de memoria de acceso aleatorio (RAM).

                Cuando se idearon estas arquitecturas, 4 GiB de memoria superaban con creces las cantidades típicas (4 MiB) en las instalaciones, por lo que se consideró que era suficiente espacio para direccionar. 

                Se consideró que 4,29 mil millones de direcciones eran un tamaño apropiado para trabajar por otra razón importante: 4,29 mil millones de números enteros son suficientes para asignar referencias únicas a la mayoría de las entidades en aplicaciones como bases de datos.

                Algunas arquitecturas de supercomputadoras de las décadas de 1970 y 1980, como la Cray-1, usaban registros de hasta 64 bits de ancho y admitían aritmética de enteros de 64 bits, aunque no admitían direccionamiento de 64 bits. 

                A mediados de la década de 1980, el desarrollo del Intel i860 comenzó y culminó con un lanzamiento en 1989; el i860 tenía registros enteros de 32 bits y direccionamiento de 32 bits, por lo que no era un procesador completamente de 64 bits, aunque su unidad gráfica admitía aritmética entera de 64 bits.

                Sin embargo, 32 bits siguieron siendo la norma hasta principios de la década de 1990, cuando las continuas reducciones en el costo de la memoria llevaron a instalaciones con cantidades de RAM cercanas a los 4 GiB, y el uso de espacios de memoria virtual que superaban el límite de 4 GiB se volvió deseable para manejar ciertos tipos de problemas. 

                En respuesta, MIPS y DEC desarrollaron arquitecturas de microprocesadores de 64 bits, inicialmente para estaciones de trabajo y servidores de alta gama. 

                A mediados de la década de 1990, HAL Computer Systems, Sun Microsystems, IBM, Silicon Graphics y Hewlett-Packard habían desarrollado arquitecturas de 64 bits para sus estaciones de trabajo y sistemas de servidores. 

                Una excepción notable a esta tendencia fueron los mainframes de IBM, que entonces utilizaban datos de 32 bits y tamaños de direcciones de 31 bits; Los mainframes de IBM no incluyeron procesadores de 64 bits hasta el año 2000. 

                Durante la década de 1990, se utilizaron varios microprocesadores de 64 bits de bajo costo en electrónica de consumo y aplicaciones integradas. 

                En particular, la Nintendo 64 y la PlayStation 2 tenían microprocesadores de 64 bits antes de su introducción en las computadoras personales. 

                Las impresoras de alta gama, los equipos de red y las computadoras industriales también usaban microprocesadores de 64 bits, como los dispositivos de efecto cuántico R5000.

                La computación de 64 bits comenzó a llegar al escritorio de las computadoras personales a partir de 2003, cuando algunos Los modelos de las líneas Macintosh de Apple cambiaron a procesadores PowerPC 970 (denominados G5 por Apple) y Advanced Micro Devices (AMD) lanzó su primer procesador x86-64 de 64 bits. 

                La memoria física finalmente alcanzó los límites de 32 bits. 

                En 2023, las computadoras portátiles estaban comúnmente equipadas con 16 GB y los servidores con hasta 64 GB de memoria, superando con creces la capacidad de direcciones de 4 GB de 32 bits.


            Límites: 

                En principio, un microprocesador de 64 bits puede direccionar 16 EiB (16 × 1024^6 = 2^64 = 18.446.744.073.709.551.616 bytes, o aproximadamente 18,4 exabytes) de memoria.

                Sin embargo, no todos los conjuntos de instrucciones, ni todos los procesadores que implementan esos conjuntos de instrucciones, admiten un espacio de direcciones físico o virtual completo de 64 bits.

                La arquitectura x86-64 (a partir de 2016) permite 48 bits para memoria virtual y, para cualquier procesador, hasta 52 bits para memoria física. 

                Estos límites permiten tamaños de memoria de 256 TiB (256 × 1024^4 bytes) y 4 PiB (4 × 1024^5 bytes), respectivamente.

                Actualmente, una PC no puede contener 4 pebibytes de memoria (debido al tamaño físico de los chips de memoria), pero AMD imaginó servidores grandes, clústeres de memoria compartida y otros usos del espacio de direcciones físicas que podrían acercarse a esto en el futuro previsible. 

                Por lo tanto, la dirección física de 52 bits proporciona un amplio espacio para la expansión sin incurrir en el costo de implementar direcciones físicas completas de 64 bits.

                De manera similar, el espacio de direcciones virtuales de 48 bits fue diseñado para proporcionar 65,536 (2^16) veces el límite de 32 bits de 4 GiB (4 × 1024^3 bytes), lo que deja espacio para una expansión posterior y no incurre en gastos generales de traducción completa de 64 bits. direcciones.

            
            Apps de 64 y 32: 

                Un cambio de una arquitectura de 32 bits a una de 64 bits es una alteración fundamental, ya que la mayoría de los sistemas operativos deben modificarse ampliamente para aprovechar la nueva arquitectura, porque ese software tiene que administrar la memoria real que direcciona el hardware. 

                También se debe migrar otro software para utilizar las nuevas capacidades; El software antiguo de 32 bits puede ser compatible ya sea en virtud de que el conjunto de instrucciones de 64 bits es un superconjunto del conjunto de instrucciones de 32 bits, de modo que los procesadores que admiten el conjunto de instrucciones de 64 bits también pueden ejecutar código para la instrucción de 32 bits conjunto, o mediante emulación de software, o mediante la implementación real de un núcleo de procesador de 32 bits dentro del procesador de 64 bits, como ocurre con algunos procesadores Itanium de Intel, que incluían un núcleo de procesador IA-32 para ejecutar aplicaciones x86 de 32 bits. 

                Los sistemas operativos para esas arquitecturas de 64 bits generalmente admiten aplicaciones de 32 y 64 bits.

                Una excepción importante a esto es el IBM AS/400, cuyo software se compila en una arquitectura de conjunto de instrucciones virtuales (ISA) llamada Technology Independent Machine Interface (TIMI); Luego, el código TIMI se traduce a código de máquina nativo mediante software de bajo nivel antes de ejecutarse. 

                El software de traducción es todo lo que se debe reescribir para mover el sistema operativo completo y todo el software a una nueva plataforma, como cuando IBM hizo la transición del conjunto de instrucciones nativo para AS/400 del antiguo IMPI de 32/48 bits al nuevo PowerPC de 64 bits. -AS, cuyo nombre en código es Amazon. 

                El conjunto de instrucciones IMPI era bastante diferente incluso del PowerPC de 32 bits, por lo que esta transición fue incluso mayor que mover un conjunto de instrucciones determinado de 32 a 64 bits.

                En hardware de 64 bits con arquitectura x86-64 (AMD64), la mayoría de los sistemas operativos y aplicaciones de 32 bits pueden ejecutarse sin problemas de compatibilidad. 

                Si bien el mayor espacio de direcciones de las arquitecturas de 64 bits facilita el trabajo con grandes conjuntos de datos en aplicaciones como vídeo digital, informática científica y grandes bases de datos, ha habido un debate considerable sobre si ellos o sus modos de compatibilidad de 32 bits serán más rápidos que los de 64 bits, sistemas de 32 bits de precio similar para otras tareas.

                Un programa Java compilado puede ejecutarse en una máquina virtual Java de 32 o 64 bits sin modificaciones. 

                Las longitudes y la precisión de todos los tipos integrados, como char, short, int, long, float y double, y los tipos que se pueden usar como índices de matriz, están especificadas por el estándar y no dependen del subyacente arquitectura. 

                Los programas Java que se ejecutan en una máquina virtual Java de 64 bits tienen acceso a un espacio de direcciones mayor.

                La velocidad no es el único factor a considerar al comparar procesadores de 32 y 64 bits.

                Aplicaciones como multitarea, pruebas de estrés y agrupación en clústeres (para computación de alto rendimiento (HPC)) pueden ser más adecuadas para una arquitectura de 64 bits cuando se implementan adecuadamente. 

                Por esta razón, los clústeres de 64 bits se han implementado ampliamente en grandes organizaciones, como IBM, HP y Microsoft.                

        Resumen:

             Un procesador de 64 bits funciona mejor con software de 64 bits.

             Un procesador de 64 bits puede tener compatibilidad con versiones anteriores, lo que le permite ejecutar software de aplicación de 32 bits para la versión de 32 bits de su conjunto de instrucciones, y también puede admitir la ejecución de sistemas operativos de 32 bits para la versión de 32 bits de su conjunto de instrucciones. .

             Un procesador de 32 bits es incompatible con el software de 64 bits.


        Pros y contras

            Un error común es pensar que las arquitecturas de 64 bits no son mejores que las de 32 bits a menos que la computadora tenga más de 4 GiB de memoria de acceso aleatorio. 

            Esto no es enteramente verdad:

                 Algunos sistemas operativos y ciertas configuraciones de hardware limitan el espacio de memoria física a 3 GiB en sistemas IA-32, debido a que gran parte de la región de 3 a 4 GiB está reservada para direccionamiento de hardware; ver barrera de 3 GiB; Las arquitecturas de 64 bits pueden abordar mucho más de 4 GiB. 

                 Sin embargo, los procesadores IA-32 a partir del Pentium Pro permiten un espacio de direcciones de memoria física de 36 bits, utilizando la extensión de dirección física (PAE), que proporciona un rango de direcciones físicas de 64 GiB, de los cuales la memoria principal puede utilizar hasta 62 GiB. ; Es posible que los sistemas operativos que admiten PAE no estén limitados a 4 GiB de memoria física, incluso en procesadores IA-32. 

                 Sin embargo, los controladores y otro software en modo kernel, especialmente las versiones anteriores, pueden ser incompatibles con PAE; esto se ha citado como la razón por la que las versiones de 32 bits de Microsoft Windows están limitadas a 4 GiB de RAM física (aunque se ha cuestionado la validez de esta explicación).

                 Algunos sistemas operativos reservan partes del espacio de direcciones de proceso para uso del sistema operativo, lo que reduce efectivamente el espacio total de direcciones disponible para mapear la memoria de los programas de usuario. 

                 Por ejemplo, Windows de 32 bits reserva 1 o 2 GiB (según la configuración) del espacio total de direcciones para el kernel, lo que deja sólo 3 o 2 GiB (respectivamente) del espacio de direcciones disponible para el modo de usuario.

                 Este límite es mucho mayor en los sistemas operativos de 64 bits.

                 Los archivos mapeados en memoria son cada vez más difíciles de implementar en arquitecturas de 32 bits a medida que los archivos de más de 4 GiB se vuelven más comunes; Estos archivos grandes no pueden asignarse en memoria fácilmente a arquitecturas de 32 bits, ya que sólo una parte del archivo puede asignarse al espacio de direcciones a la vez, y para acceder a dicho archivo mediante el mapeo de memoria, las partes asignadas deben intercambiarse y fuera del espacio de direcciones según sea necesario. 

                 Esto es un problema, ya que el mapeo de memoria, si el sistema operativo lo implementa correctamente, es uno de los métodos más eficientes de conversión de disco a memoria.

                 Algunos programas de 64 bits, como codificadores, decodificadores y software de cifrado, pueden beneficiarse enormemente de los registros de 64 bits, mientras que el rendimiento de otros programas, como los orientados a gráficos 3D, no se ve afectado al cambiar de 32 bits a uno, Entorno de 64 bits.

                 Algunas arquitecturas de 64 bits, como x86-64 y AArch64, admiten más registros de uso general que sus contrapartes de 32 bits (aunque esto no se debe específicamente a la longitud de la palabra). 

                 Esto conduce a un aumento significativo de la velocidad para bucles cerrados, ya que el procesador no tiene que recuperar datos del caché o de la memoria principal si los datos caben en los registros disponibles.


            Modelos de datos de 64 bits

                En programas de 32 bits, los punteros y los tipos de datos, como los números enteros, generalmente tienen la misma longitud. 

                Esto no es necesariamente cierto en máquinas de 64 bits. 

                Por lo tanto, la combinación de tipos de datos en lenguajes de programación como C y sus descendientes, como C++ y Objective-C, puede funcionar en implementaciones de 32 bits, pero no en implementaciones de 64 bits.

                En muchos entornos de programación para C y lenguajes derivados de C en máquinas de 64 bits, las variables int todavía tienen 32 bits de ancho, pero los enteros largos y los punteros tienen 64 bits de ancho. 

                Se describe que tienen un modelo de datos LP64, que es una abreviatura de "Long, Pointer, 64". 

                Otros modelos son el modelo de datos ILP64 en el que los tres tipos de datos tienen 64 bits de ancho, e incluso el modelo SILP64 donde los enteros cortos también tienen 64 bits de ancho.

                Sin embargo, en la mayoría de los casos las modificaciones requeridas son relativamente menores y sencillas, y muchos programas bien escritos pueden simplemente recompilarse para el nuevo entorno sin cambios. 

                Otra alternativa es el modelo LLP64, que mantiene la compatibilidad con código de 32 bits al dejar tanto int como long en 32 bits. 

                LL se refiere al tipo entero largo, que es de al menos 64 bits en todas las plataformas, incluidos los entornos de 32 bits.

                También hay sistemas con procesadores de 64 bits que utilizan un modelo de datos ILP32, con la adición de enteros largos de 64 bits; esto también se utiliza en muchas plataformas con procesadores de 32 bits. 

                Este modelo reduce el tamaño del código y el tamaño de las estructuras de datos que contienen punteros, a costa de un espacio de direcciones mucho más pequeño, una buena opción para algunos sistemas integrados. 

                Para conjuntos de instrucciones como x86 y ARM en los que la versión de 64 bits del conjunto de instrucciones tiene más registros que la versión de 32 bits, proporciona acceso a registros adicionales sin penalización de espacio. 

                Es común en máquinas RISC de 64 bits, explorado en x86 como x32 ABI, y recientemente se ha utilizado en los Apple Watch Series 4 y 5.


    Registro de proceso: 

        El registro del procesador es una ubicación de rápido acceso disponible para el procesador de una computadora. 

        Los registros suelen consistir en una pequeña cantidad de almacenamiento rápido, aunque algunos registros tienen funciones de hardware específicas y pueden ser de sólo lectura o de sólo escritura. 

        En la arquitectura de computadoras, los registros generalmente se abordan mediante mecanismos distintos a la memoria principal, pero en algunos casos se les puede asignar una dirección de memoria, p. DIC PDP-10, TIC 1900.

        Casi todas las computadoras, ya sea con arquitectura de carga/almacenamiento o no, cargan elementos de datos desde una memoria más grande en registros donde se usan para operaciones aritméticas, operaciones bit a bit y otras operaciones, y son manipulados o probados mediante instrucciones de máquina. 

        Los elementos manipulados a menudo se almacenan en la memoria principal, ya sea mediante la misma instrucción o mediante una posterior. 

        Los procesadores modernos utilizan RAM estática o dinámica como memoria principal, a la que normalmente se accede a esta última a través de uno o más niveles de caché.

        Los registros del procesador normalmente se encuentran en la parte superior de la jerarquía de la memoria y proporcionan la forma más rápida de acceder a los datos. 

        El término normalmente se refiere sólo al grupo de registros que están codificados directamente como parte de una instrucción, según lo definido por el conjunto de instrucciones.

        Sin embargo, las CPU modernas de alto rendimiento a menudo tienen duplicados de estos "registros arquitectónicos" para mejorar el rendimiento mediante el cambio de nombre de los registros, lo que permite la ejecución paralela y especulativa. 

        El diseño x86 moderno adquirió estas técnicas alrededor de 1995 con los lanzamientos de Pentium Pro, Cyrix 6x86, Nx586 y AMD K5.

        Cuando un programa de computadora accede repetidamente a los mismos datos, esto se denomina localidad de referencia.

        Mantener valores utilizados con frecuencia en registros puede ser fundamental para el rendimiento de un programa.

        La asignación de registros la realiza un compilador en la fase de generación de código o manualmente un programador en lenguaje ensamblador.


            Tamaño:

                Los registros normalmente se miden por la cantidad de bits que pueden contener, por ejemplo, un "registro de 8 bits", un "registro de 32 bits", un "registro de 64 bits" o incluso más. 

                En algunos conjuntos de instrucciones, los registros pueden operar en varios modos, dividiendo su memoria de almacenamiento en partes más pequeñas (de 32 bits en cuatro de 8 bits, por ejemplo) a las que se agregan múltiples datos (vectoriales o una matriz unidimensional de datos). 

                Se puede cargar y operar al mismo tiempo. 

                Normalmente se implementa agregando registros adicionales que asignan su memoria a un registro más grande. 

                Los procesadores que tienen la capacidad de ejecutar instrucciones únicas sobre múltiples datos se denominan procesadores vectoriales.


            Tipos

                Un procesador suele contener varios tipos de registros, que se pueden clasificar según los tipos de valores que pueden almacenar o las instrucciones que operan sobre ellos:

                1. Los registros accesibles al usuario se pueden leer o escribir mediante instrucciones de la máquina. La división más común de los registros accesibles al usuario es una división en registros de datos y registros de direcciones.

                    Los registros de datos pueden contener valores de datos numéricos como números enteros y, en algunas arquitecturas, números de punto flotante, así como caracteres, matrices de bits pequeños y otros datos. En algunas arquitecturas más antiguas, como IBM 704, IBM 709 y sucesores, PDP-1, PDP-4/PDP-7/PDP-9/PDP-15, PDP-5/PDP-8 y HP 2100, un registro de datos especial conocido como acumulador se utiliza implícitamente para muchas operaciones.


                    Los registros de direcciones contienen direcciones y son utilizados por instrucciones que acceden indirectamente a la memoria primaria.

                        Algunos procesadores contienen registros que solo pueden usarse para contener una dirección o solo para contener valores numéricos (en algunos casos se usan como un registro de índice cuyo valor se agrega como un desplazamiento de alguna dirección); otros permiten que los registros contengan cualquier tipo de cantidad. Existe una amplia variedad de posibles modos de direccionamiento, utilizados para especificar la dirección efectiva de un operando.

                        El puntero de la pila se utiliza para administrar la pila en tiempo de ejecución. En raras ocasiones, otras pilas de datos se abordan mediante registros de direcciones dedicados (máquina de pila).


                    Los registros de propósito general (GPR) pueden almacenar tanto datos como direcciones, es decir, son registros combinados de datos/direcciones; En algunas arquitecturas, el archivo de registro está unificado.


                    Los GPR también pueden almacenar números de punto flotante.
                    Los registros de estado contienen valores de verdad que se utilizan a menudo para determinar si alguna instrucción debe o no ejecutarse.


                    Los registros de punto flotante (FPR) almacenan números de punto flotante en muchas arquitecturas.


                    Los registros constantes contienen valores de solo lectura como cero, uno o pi.


                    Los registros vectoriales contienen datos para el procesamiento vectorial realizado mediante instrucciones SIMD (Instrucción única, datos múltiples).


                    Los registros de propósito especial (SPR) contienen algunos elementos del estado del programa; suelen incluir el contador de programa, también llamado puntero de instrucción, y el registro de estado; el contador de programa y el registro de estado pueden combinarse en un registro de palabra de estado de programa (PSW). El puntero de pila antes mencionado a veces también se incluye en este grupo.

                    Los microprocesadores integrados también pueden tener registros correspondientes a elementos de hardware especializados.


                    En algunas arquitecturas, los registros específicos del modelo (también llamados registros específicos de la máquina) almacenan datos y configuraciones relacionados con el propio procesador. Debido a que sus significados están ligados al diseño de un procesador específico, no se puede esperar que sigan siendo estándar entre generaciones de procesadores.


                    Registros de rango de tipos de memoria (MTRR).


                2. Instrucciones y se utilizan internamente para las operaciones del procesador.

                El registro de instrucciones contiene la instrucción que se está ejecutando actualmente.

                Registros relacionados con la recuperación de información de la RAM, una colección de registros de almacenamiento ubicados en chips separados de la CPU:

                     Registro de búfer de memoria (MBR), también conocido como registro de datos de memoria (MDR)

                     Registro de dirección de memoria (MAR)


                3. Los registros arquitectónicos son los registros visibles para el software y están definidos por una arquitectura. Es posible que no se correspondan con el hardware físico si el cambio de nombre de los registros lo realiza el hardware subyacente.

                Los registros de hardware son similares, pero ocurren fuera de las CPU.



    Almacenamiento de datos: 

        El almacenamiento de datos informáticos es una tecnología que consta de componentes informáticos y medios de grabación que se utilizan para conservar datos digitales. 

        Es una función central y componente fundamental de las computadoras.

        La unidad central de procesamiento (CPU) de una computadora es la que manipula los datos mediante la realización de cálculos.

        En la práctica, casi todas las computadoras utilizan una jerarquía de almacenamiento, que coloca opciones de almacenamiento pequeñas, rápidas pero costosas cerca de la CPU y opciones más lentas pero menos costosas y más grandes, más alejadas.

        Generalmente, las tecnologías rápidas se denominan "memoria", mientras que las tecnologías persistentes más lentas se denominan "almacenamiento".

        Incluso los primeros diseños de computadora, la máquina analítica de Charles Babbage y la máquina analítica de Percy Ludgate, distinguían claramente entre procesamiento y memoria (Babbage almacenaba números como rotaciones de engranajes, mientras que Ludgate almacenaba números como desplazamientos de varillas en lanzaderas). 

        Esta distinción se amplió en la arquitectura Von Neumann, donde la CPU consta de dos partes principales: la unidad de control y la unidad aritmética lógica (ALU). 

        El primero controla el flujo de datos entre la CPU y la memoria, mientras que el segundo realiza operaciones aritméticas y lógicas con los datos.


        Funcionalidad:

            Sin una cantidad significativa de memoria, una computadora simplemente podría realizar operaciones fijas y generar el resultado inmediatamente.

            Habría que reconfigurarlo para cambiar su comportamiento. 

            Esto es aceptable para dispositivos como calculadoras de escritorio, procesadores de señales digitales y otros dispositivos especializados. 

            Las máquinas Von Neumann se diferencian por tener una memoria en la que almacenan sus instrucciones y datos de funcionamiento. 

            Estas computadoras son más versátiles porque no necesitan reconfigurar su hardware para cada nuevo programa, sino que simplemente pueden reprogramarse con nuevas instrucciones en memoria; también tienden a ser más simples de diseñar, en el sentido de que un procesador relativamente simple puede mantener el estado entre cálculos sucesivos para generar resultados de procedimientos complejos.

            La mayoría de las computadoras modernas son máquinas von Neumann.


        Organización y representación de datos:

            Una computadora digital moderna representa datos utilizando el sistema de numeración binario.

            Texto, números, imágenes, audio y casi cualquier otra forma de información se pueden convertir en una cadena de bits o dígitos binarios, cada uno de los cuales tiene un valor de 0 o 1. 

            La unidad de almacenamiento más común es el byte, igual a 8 bits. 

            Una información puede ser manejada por cualquier computadora o dispositivo cuyo espacio de almacenamiento sea lo suficientemente grande como para acomodar la representación binaria de la información, o simplemente los datos.

            Por ejemplo, las obras completas de Shakespeare, de unas 1.250 páginas impresas, pueden almacenarse en unos cinco megabytes (40 millones de bits) con un byte por carácter.

            Los datos se codifican asignando un patrón de bits a cada carácter, dígito u objeto multimedia. 

            Existen muchos estándares para la codificación (por ejemplo, codificaciones de caracteres como ASCII, codificaciones de imágenes como JPEG y codificaciones de vídeo como MPEG-4).

            Al agregar bits a cada unidad codificada, la redundancia permite que la computadora detecte errores en los datos codificados y los corrija basándose en algoritmos matemáticos. 

            Los errores generalmente ocurren en probabilidades bajas debido a cambios aleatorios de valores de bits, o "fatiga física del bit", pérdida del bit físico en el almacenamiento de su capacidad para mantener un valor distinguible (0 o 1), o debido a errores en inter o intra -comunicación informática. 

            Un cambio de bit aleatorio (por ejemplo, debido a una radiación aleatoria) normalmente se corrige tras la detección. 

            Un bit o un grupo de bits físicos que funcionan mal (no siempre se conoce el bit defectuoso específico; la definición del grupo depende del dispositivo de almacenamiento específico) generalmente se excluye automáticamente, se deja de utilizar por el dispositivo y se reemplaza con otro grupo equivalente que funcione en el dispositivo, donde se restablecen los valores de bits corregidos (si es posible). 

            El método de verificación de redundancia cíclica (CRC) se usa típicamente en comunicaciones y almacenamiento para la detección de errores.

            Luego se vuelve a intentar un error detectado.

            Los métodos de compresión de datos permiten en muchos casos (como en una base de datos) representar una cadena de bits mediante una cadena de bits más corta ("comprimir") y reconstruir la cadena original ("descomprimir") cuando sea necesario.

            Esto utiliza sustancialmente menos almacenamiento (decenas de por ciento) para muchos tipos de datos a costa de más cálculos (comprimir y descomprimir cuando sea necesario).

            Antes de decidir si mantener ciertos datos comprimidos o no, se realiza un análisis de la compensación entre el ahorro de costos de almacenamiento y los costos de los cálculos relacionados y los posibles retrasos en la disponibilidad de los datos.

            Por razones de seguridad, ciertos tipos de datos (por ejemplo, información de tarjetas de crédito) pueden mantenerse cifrados en el almacenamiento para evitar la posibilidad de reconstrucción no autorizada de información a partir de fragmentos de instantáneas de almacenamiento.


        Jerarquía de almacenamiento: 

            Generalmente, cuanto más bajo esté un almacenamiento en la jerarquía, menor será su ancho de banda y mayor será su latencia de acceso desde la CPU. 

            Esta división tradicional del almacenamiento en almacenamiento primario, secundario, terciario y fuera de línea también se rige por el costo por bit.

            En el uso contemporáneo, la memoria suele ser una memoria de lectura y escritura de semiconductores rápida pero temporal, generalmente DRAM (RAM dinámica) u otros dispositivos similares.

            El almacenamiento consta de dispositivos de almacenamiento y sus medios a los que la CPU no puede acceder directamente (almacenamiento secundario o terciario), generalmente unidades de disco duro, unidades de discos ópticos y otros dispositivos más lentos que la RAM pero no volátiles (que retienen el contenido cuando se apagan).


            Almacenamiento primario:

            El almacenamiento primario (también conocido como memoria principal, memoria interna o memoria principal), a menudo denominado simplemente memoria, es el único al que la CPU puede acceder directamente. 

            La CPU lee continuamente las instrucciones almacenadas allí y las ejecuta según sea necesario. 

            Los datos que se utilicen activamente también se almacenarán allí de forma uniforme.

            Históricamente, las primeras computadoras usaban líneas de retardo, tubos Williams o tambores magnéticos giratorios como almacenamiento primario. 

            En 1954, esos métodos poco fiables fueron reemplazados en su mayor parte por memorias de núcleo magnético.

            La memoria central siguió siendo dominante hasta la década de 1970, cuando los avances en la tecnología de circuitos integrados permitieron que la memoria semiconductora se volviera económicamente competitiva.

            Esto condujo a la moderna memoria de acceso aleatorio (RAM). 

            Es de tamaño pequeño, ligero, pero bastante caro al mismo tiempo. 

            Los tipos particulares de RAM utilizados para el almacenamiento primario son volátiles, lo que significa que pierden la información cuando no están encendidos. 

            Además de almacenar programas abiertos, sirve como caché de disco y búfer de escritura para mejorar el rendimiento de lectura y escritura. 

            Los sistemas operativos toman prestada capacidad de RAM para el almacenamiento en caché siempre que no sea necesaria para ejecutar el software.

            La memoria adicional se puede utilizar como unidad RAM para el almacenamiento temporal de datos de alta velocidad.

            Como se muestra en el diagrama, tradicionalmente hay dos subcapas más del almacenamiento primario, además de la RAM principal de gran capacidad:

                 Los registros del procesador están ubicados dentro del procesador. 

                 Cada registro suele contener una palabra de datos (a menudo de 32 o 64 bits).

                 Las instrucciones de la CPU indican a la unidad lógica aritmética que realice varios cálculos u otras operaciones con estos datos (o con la ayuda de ellos).

                 Los registros son la más rápida de todas las formas de almacenamiento de datos informáticos.

                 La caché del procesador es una etapa intermedia entre los registros ultrarrápidos y la memoria principal mucho más lenta.

                 Se introdujo únicamente para mejorar el rendimiento de las computadoras. 

                 La información más utilizada en la memoria principal simplemente se duplica en la memoria caché, que es más rápida, pero de mucha menor capacidad. 

                 Por otro lado, la memoria principal es mucho más lenta, pero tiene una capacidad de almacenamiento mucho mayor que los registros del procesador. 

                 La configuración de caché jerárquica multinivel también se utiliza comúnmente: la caché primaria es la más pequeña, la más rápida y está ubicada dentro del procesador; la caché secundaria es algo más grande y más lenta.

            La memoria principal está conectada directa o indirectamente a la unidad central de procesamiento a través de un bus de memoria. 

            En realidad, se trata de dos buses (no en el diagrama): un bus de direcciones y un bus de datos. 

            En primer lugar, la CPU envía un número a través de un bus de direcciones, un número llamado dirección de memoria, que indica la ubicación deseada de los datos. Luego lee o escribe los datos en las celdas de memoria utilizando el bus de datos. 

            Además, una unidad de gestión de memoria (MMU) es un pequeño dispositivo entre la CPU y la RAM que recalcula la dirección de memoria real, por ejemplo para proporcionar una abstracción de la memoria virtual u otras tareas.

            Como los tipos de RAM utilizados para el almacenamiento primario son volátiles (no inicializados al inicio), una computadora que contenga solo dicho almacenamiento no tendría una fuente desde la cual leer las instrucciones para iniciar la computadora. 

            Por lo tanto, el almacenamiento primario no volátil que contiene un pequeño programa de inicio (BIOS) se utiliza para arrancar la computadora, es decir, para leer un programa más grande desde el almacenamiento secundario no volátil a la RAM y comenzar a ejecutarlo.

            Una tecnología no volátil utilizada para este propósito se llama ROM, para memoria de sólo lectura (la terminología puede resultar algo confusa ya que la mayoría de los tipos de ROM también son capaces de acceso aleatorio).

            Muchos tipos de "ROM" no son literalmente de sólo lectura, ya que es posible actualizarlos; sin embargo, es lento y la memoria debe borrarse en grandes porciones antes de poder reescribirse. 

            Algunos sistemas integrados ejecutan programas directamente desde la ROM (o similar), porque dichos programas rara vez se modifican.

            Las computadoras estándar no almacenan programas no rudimentarios en ROM y, más bien, utilizan grandes capacidades de almacenamiento secundario, que tampoco es volátil y no es tan costoso.

            Recientemente, almacenamiento primario y almacenamiento secundario en algunos usos hacen referencia a lo que históricamente se denominó, respectivamente, almacenamiento secundario y almacenamiento terciario.


            Almacenamiento secundario:

            El almacenamiento secundario (también conocido como memoria externa o almacenamiento auxiliar) se diferencia del almacenamiento primario en que la CPU no puede acceder directamente a él. 

            La computadora generalmente usa sus canales de entrada/salida para acceder al almacenamiento secundario y transfiera los datos deseados al almacenamiento primario.

            El almacenamiento secundario no es volátil (retiene los datos cuando se corta la energía). 

            Los sistemas informáticos modernos suelen tener dos órdenes de magnitud más de almacenamiento secundario que el almacenamiento primario porque el almacenamiento secundario es menos costoso.

            En las computadoras modernas, las unidades de disco duro (HDD) o unidades de estado sólido (SSD) se suelen utilizar como almacenamiento secundario. 

            El tiempo de acceso por byte para HDD o SSD generalmente se mide en milisegundos (milmillonésimas de segundo), mientras que el tiempo de acceso por byte para el almacenamiento primario se mide en nanosegundos (milmillonésimas de segundo). 

            Por tanto, el almacenamiento secundario es significativamente más lento que el almacenamiento primario.

            Los dispositivos de almacenamiento óptico giratorio, como las unidades de CD y DVD, tienen tiempos de acceso aún más prolongados.

            Otros ejemplos de tecnologías de almacenamiento secundario incluyen unidades flash USB, disquetes, cintas magnéticas, cintas de papel, tarjetas perforadas y discos RAM.

            Una vez que el cabezal de lectura/escritura del disco en los HDD alcanza la ubicación adecuada y los datos, es muy rápido acceder a los datos posteriores en la pista.

            Para reducir el tiempo de búsqueda y la latencia rotacional, los datos se transfieren hacia y desde discos en grandes bloques contiguos.

            El acceso secuencial o en bloques a los discos es mucho más rápido que el acceso aleatorio, y se han desarrollado muchos paradigmas sofisticados para diseñar algoritmos eficientes basados en el acceso secuencial y en bloques.

            Otra forma de reducir el cuello de botella de E/S es utilizar varios discos en paralelo para aumentar el ancho de banda entre la memoria primaria y secundaria.

            El almacenamiento secundario suele formatearse según un formato de sistema de archivos, que proporciona la abstracción necesaria para organizar los datos en archivos y directorios, al tiempo que proporciona metadatos que describen el propietario de un determinado archivo, el tiempo de acceso, los permisos de acceso y otra información.

            La mayoría de los sistemas operativos de computadora utilizan el concepto de memoria virtual, lo que permite la utilización de más capacidad de almacenamiento primario de la que está físicamente disponible en el sistema. 

            A medida que la memoria primaria se llena, el sistema mueve los fragmentos (páginas) menos utilizados a un archivo de intercambio o de página en el almacenamiento secundario, recuperándolos más tarde cuando sea necesario. 

            Si se mueven muchas páginas a un almacenamiento secundario más lento, el rendimiento del sistema se degrada.            


        Block:

            En informática (específicamente transmisión y almacenamiento de datos), un bloque, a veces llamado registro físico, es una secuencia de bytes o bits, que generalmente contiene un número entero de registros y tiene una longitud máxima; un tamaño de bloque. 

            Los datos así estructurados se denominan bloqueados. 

            El proceso de poner datos en bloques se llama bloqueo, mientras que desbloqueo es el proceso de extraer datos de los blocking. 

            Los datos bloqueados normalmente se almacenan en un búfer de datos y se leen o escriben un bloque completo a la vez. 

            El bloque reduce la sobrecarga y acelera el manejo del flujo de datos. 

            Para algunos dispositivos, como los dispositivos de cinta magnética y disco CKD, el bloque reduce la cantidad de almacenamiento externo requerido para los datos.

            El bloque se emplea casi universalmente cuando se almacenan datos en cintas magnéticas de 9 pistas, memoria flash NAND y medios giratorios como disquetes, discos duros y discos ópticos.

            La mayoría de los sistemas de archivos se basan en un dispositivo de bloques, que es un nivel de abstracción del hardware responsable de almacenar y recuperar bloques de datos específicos, aunque el tamaño del bloque en los sistemas de archivos puede ser un múltiplo del tamaño del bloque físico.

            Esto conduce a una ineficiencia de espacio debido a la fragmentación interna, ya que las longitudes de los archivos a menudo no son múltiplos enteros del tamaño del bloque y, por lo tanto, el último bloque de un archivo puede permanecer parcialmente vacío. 

            Esto creará un espacio flojo. 

            Algunos sistemas de archivos más nuevos, como Btrfs y FreeBSD UFS2, intentan resolver este problema mediante técnicas llamadas subasignación de bloques y fusión de cola. 

            Otros sistemas de archivos, como ZFS, admiten tamaños de bloque variables.

            El almacenamiento en bloque normalmente se abstrae mediante un sistema de archivos o un sistema de gestión de bases de datos (DBMS) para que lo utilicen las aplicaciones y los usuarios finales. 

            Los volúmenes físicos o lógicos a los que se accede a través de bloques de E/S pueden ser dispositivos internos a un servidor, conectados directamente a través de SCSI o Fibre Channel, o dispositivos distantes a los que se accede a través de una red de área de almacenamiento (SAN) utilizando un protocolo como iSCSI o AoE. 

            Los DBMS a menudo utilizan su propio bloque de E/S para mejorar el rendimiento y la capacidad de recuperación en comparación con colocar el DBMS sobre un sistema de archivos.


    Read–write memory (RWM): 

        La memoria de lectura-escritura, es un tipo de memoria de computadora en la que se puede escribir y leer fácilmente mediante señales eléctricas normalmente asociadas con la ejecución de un software y sin ningún otro proceso físico. 

        El tipo de almacenamiento RAM relacionado significa algo diferente; se refiere a una memoria que puede acceder a cualquier ubicación de la memoria en un período de tiempo constante.

        El término también podría referirse a ubicaciones de memoria que tienen permisos de lectura y escritura. 

        En los sistemas informáticos modernos que utilizan la segmentación de memoria, cada segmento tiene una longitud y un conjunto de permisos asociados.


    Segmentación de memoria:

        Es una técnica de gestión de la memoria del sistema operativo que consiste en dividir la memoria principal de una computadora en segmentos o secciones. 

        En un sistema informático que utiliza segmentación, una referencia a una ubicación de memoria incluye un valor que identifica un segmento y un desplazamiento (ubicación de memoria) dentro de ese segmento. 

        Los segmentos o secciones también se utilizan en archivos objeto de programas compilados cuando se vinculan entre sí en una imagen de programa y cuando la imagen se carga en la memoria.

        Los segmentos suelen corresponder a divisiones naturales de un programa, como rutinas individuales o tablas de datos, por lo que la segmentación suele ser más visible para el programador que la paginación sola. 

        Se pueden crear segmentos para módulos de programa o para clases de uso de memoria, como segmentos de código y segmentos de datos.

        Ciertos segmentos pueden compartirse entre programas.

        La segmentación se inventó originalmente como un método mediante el cual el software del sistema podía aislar los procesos (tareas) de software y los datos que estaban utilizando. 

        Su objetivo era aumentar la confiabilidad de los sistemas que ejecutan múltiples procesos simultáneamente.


        Implementación de hardware

            En un sistema que utiliza segmentación, las direcciones de memoria de la computadora constan de una identificación de segmento y un desplazamiento dentro del segmento. 

            Una unidad de administración de memoria de hardware (MMU) es responsable de traducir el segmento y el desplazamiento a una dirección física, y de realizar comprobaciones para garantizar que se pueda realizar la traducción y que se permita la referencia a ese segmento y desplazamiento.

            Cada segmento tiene una longitud y un conjunto de permisos (por ejemplo, lectura, escritura, ejecución) asociados. 

            Un proceso solo puede hacer una referencia en un segmento si los permisos permiten el tipo de referencia y si el desplazamiento dentro del segmento está dentro del rango especificado por la longitud del segmento. 

            De lo contrario, se genera una excepción de hardware, como un error de segmentación.

            También se pueden utilizar segmentos para implementar memoria virtual. 

            En este caso cada segmento tiene un indicador asociado que indica si está presente en la memoria principal o no. 

            Si se accede a un segmento que no está presente en la memoria principal, se genera una excepción y el sistema operativo leerá el segmento en la memoria desde el almacenamiento secundario.

            La segmentación es un método para implementar la protección de la memoria. 

            La paginación es otra y se pueden combinar. 

            El tamaño de un segmento de memoria generalmente no es fijo y puede ser tan pequeño como un solo byte.

            La segmentación se ha implementado de varias maneras en distintos hardware, con o sin paginación. 

            La segmentación de la memoria Intel x86 no se ajusta a ninguno de los modelos y se analiza por separado a continuación, y también con mayor detalle en un artículo separado.


        x86:
            
            Los primeros procesadores x86, comenzando con el Intel 8086, proporcionaban una segmentación de memoria cruda y ninguna protección de la memoria.

            (Cada byte de cada segmento está siempre disponible para cualquier programa). 

            Los registros de segmento de 16 bits permiten 65.536 segmentos; cada segmento comienza en un desplazamiento fijo igual a 16 veces el número del segmento; la granularidad de la dirección inicial del segmento es de 16 bytes. 

            Cada segmento otorga acceso de lectura y escritura a 64 KiB (65,536 bytes) de espacio de direcciones (este límite lo establecen los registros SP y PC de 16 bits; el procesador no realiza comprobaciones de límites). 

            El desplazamiento+la dirección que excede 0xFFFFF se ajusta a 0x00000. 

            Cada segmento de 64 KiB se superpone a los siguientes 4.095 segmentos; cada dirección física se puede indicar mediante 4.096 pares de segmento-desplazamiento.

            Este esquema puede abordar solo 1 MiB (1024 KiB) de memoria física (y E/S asignadas en memoria). 

            (El hardware de memoria expandida opcional puede agregar memoria conmutada por banco bajo control de software). 

            Intel nombró retroactivamente al único modo operativo de estos modelos de CPU x86 "modo real".

            Los procesadores Intel 80286 y posteriores agregan el "modo protegido 286", que conserva el direccionamiento de 16 bits y agrega segmentación (sin paginación) y protección de memoria por segmento.

            Para compatibilidad con versiones anteriores, todas las CPU x86 se inician en "modo real", con los mismos segmentos superpuestos fijos de 64 KiB, sin protección de memoria, solo 1 MiB de espacio de dirección física y algunas diferencias sutiles (área de memoria alta, modo irreal). 

            Para utilizar todo su espacio de direcciones físicas de 24 bits (16 MiB) y sus funciones avanzadas de MMU, un procesador 80286 o posterior debe cambiarse al "modo protegido" mediante software, generalmente el sistema operativo o un extensor de DOS. 

            Si un programa no utiliza los registros de segmento, o solo coloca en ellos los valores que recibe del sistema operativo, entonces se puede ejecutar un código idéntico en modo real o en modo protegido, pero la mayoría del software en modo real calcula nuevos valores para los registros de segmento. rompiendo esta compatibilidad.

            Los procesadores Intel i386 y posteriores agregan el "modo protegido 386", que utiliza direccionamiento de 32 bits, conserva la segmentación y agrega paginación de memoria. 

            En estos procesadores, la tabla de segmentos, en lugar de apuntar a una tabla de páginas para el segmento, contiene la dirección del segmento en la memoria lineal. 

            Cuando la paginación está habilitada, las direcciones en la memoria lineal se asignan a direcciones físicas utilizando una tabla de páginas separada. 

            La mayoría de los sistemas operativos no utilizaron la capacidad de segmentación y optaron por mantener el direccionamiento base en todos los registros de segmento iguales a 0 en todo momento y proporcionar protección e intercambio de memoria por página utilizando solo paginación. 

            Algunos usan el registro CS para proporcionar protección del espacio ejecutable en procesadores que carecen del bit NX o usan los registros FS o GS para acceder al almacenamiento local de subprocesos.

            La arquitectura x86-64 no admite la segmentación en "modo largo" (modo de 64 bits).

            Cuatro de los registros de segmento: CS, SS, DS y ES se fuerzan a 0 y el límite a 264.

            Los registros de segmento FS y GS aún pueden tener una dirección base distinta de cero.

            Esto permite que los sistemas operativos utilicen estos segmentos para fines especiales, como el almacenamiento local de subprocesos.



    RAM: 


    

    Files: 

        La mayoría de los sistemas de archivos incluyen atributos de archivos y directorios que controlan la capacidad de los usuarios para leer, cambiar, navegar y ejecutar el contenido del sistema de archivos. 

        En algunos casos, las opciones o funciones del menú pueden hacerse visibles u ocultarse según el nivel de permiso del usuario; Este tipo de interfaz de usuario se conoce como basada en permisos.

        Hay dos tipos de permisos ampliamente disponibles: permisos del sistema de archivos POSIX y listas de control de acceso (ACL) que son capaces de realizar un control más específico.


        Los permisos en sistemas de archivos tipo Unix se definen en el estándar POSIX.1-2017,[9] que utiliza tres ámbitos o clases conocidos como propietario, grupo y otros. Cuando se crea un archivo, sus permisos están restringidos por la máscara del proceso que lo creó.


        Clases:

            Los archivos y directorios son propiedad de un usuario. 

            El propietario determina la clase de usuario del archivo. 

            Se aplican permisos distintos al propietario.

            A los archivos y directorios se les asigna un grupo, que define la clase de grupo del archivo. 

            Se aplican permisos distintos a los miembros del grupo del archivo. 

            El propietario puede ser miembro del grupo del archivo.

            Los usuarios que no son propietarios ni miembros del grupo constituyen la clase otros de un archivo. 

            Se aplican distintos permisos a otros.

            Los permisos efectivos se determinan en función de la primera clase a la que pertenece el usuario en el orden de usuario, grupo y luego otros. 

            Por ejemplo, el usuario propietario del archivo tendrá los permisos otorgados a la clase de usuario independientemente de los permisos asignados a la clase de grupo o a otras clases.


        Permisos:

            Los sistemas tipo Unix implementan tres permisos específicos que se aplican a cada clase:

             El permiso de lectura otorga la capacidad de leer un archivo. Cuando se establece para un directorio, este permiso otorga la capacidad de leer los nombres de los archivos en el directorio, pero no de encontrar más información sobre ellos, como contenido, tipo de archivo, tamaño, propiedad o permisos.


             El permiso de escritura otorga la posibilidad de modificar un archivo. Cuando se establece para un directorio, este permiso otorga la capacidad de modificar entradas en el directorio, lo que incluye crear archivos, eliminar archivos y cambiarles el nombre. Esto requiere que ejecutar también esté configurado; sin él, el permiso de escritura no tiene sentido para los directorios.


             El permiso de ejecución otorga la capacidad de ejecutar un archivo. Este permiso debe establecerse para los programas ejecutables para permitir que el sistema operativo los ejecute. Cuando se configura para un directorio, el permiso de ejecución se interpreta como el permiso de búsqueda: otorga la capacidad de acceder al contenido del archivo y a la metainformación si se conoce su nombre, pero no enumera los archivos dentro del directorio, a menos que también se configure la lectura.

            
            El efecto de establecer los permisos en un directorio, en lugar de en un archivo, es "uno de los problemas de permisos de archivos más frecuentemente mal entendidos".

            Cuando no se establece un permiso, se deniegan los derechos correspondientes. 

            A diferencia de los sistemas basados en ACL, los permisos en sistemas tipo Unix no se heredan. Los archivos creados dentro de un directorio no necesariamente tienen los mismos permisos que ese directorio.


        Cambiar el comportamiento de los permisos con setuid, setgid y bits adhesivos:

            Los sistemas tipo Unix suelen emplear tres modos adicionales. 

            En realidad, estos son atributos, pero se denominan permisos o modos. 

            Estos modos especiales son para un archivo o directorio en general, no por una clase, aunque en la notación simbólica (ver más abajo) el bit setuid se establece en la tríada para el usuario, el bit setgid se establece en la tríada para el grupo y el El bit pegajoso se establece en la tríada para los demás.

             El modo ID de usuario establecido, setuid o SUID. Cuando se ejecuta un archivo con setuid, el proceso resultante asumirá la ID de usuario efectiva proporcionada a la clase propietaria. Esto permite que los usuarios sean tratados temporalmente como root (u otro usuario).

             El permiso de ID de grupo establecido, setgid o SGID. Cuando se ejecuta un archivo con setgid, el proceso resultante asumirá el ID de grupo proporcionado a la clase de grupo. Cuando se aplica setgid a un directorio, los nuevos archivos y directorios creados en ese directorio heredarán su grupo de ese directorio. (El comportamiento predeterminado es utilizar el grupo principal del usuario efectivo al configurar el grupo de nuevos archivos y directorios, excepto en sistemas derivados de BSD que se comportan como si el bit setgid siempre estuviera configurado en todos los directorios (ver Setuid).)


             El modo fijo (también conocido como modo Texto). El comportamiento clásico del bit adhesivo en archivos ejecutables ha sido alentar al núcleo a retener la imagen del proceso resultante en la memoria más allá de su terminación; sin embargo, dicho uso del bit adhesivo ahora está restringido sólo a una minoría de sistemas operativos tipo Unix (HP-UX y UnixWare). En un directorio, el permiso fijo evita que los usuarios cambien el nombre, muevan o eliminen archivos contenidos que pertenecen a usuarios distintos a ellos, incluso si tienen permiso de escritura en el directorio. Sólo el propietario del directorio y el superusuario están exentos de esto.

            
            Estos modos adicionales también se conocen como bit setuid, bit setgid y bit adhesivo, debido a que cada uno de ellos ocupa solo un bit.


        Notación de los permisos de Unix:

            Notación simbólica.

            Los permisos de Unix se representan en notación simbólica o en notación octal.

            La forma más común, utilizada por el comando ls -l, es la notación simbólica.

            El primer carácter de la visualización ls indica el tipo de archivo y no está relacionado con los permisos. 

            Los nueve caracteres restantes están en tres conjuntos, cada uno de los cuales representa una clase de permisos como tres caracteres. 

            El primer conjunto representa la clase de usuario. 

            El segundo conjunto representa la clase grupal. 

            El tercer conjunto representa la clase de los demás.

            Cada uno de los tres caracteres representa los permisos de lectura, escritura y ejecución:

                 r si la lectura está permitida, - si no lo está.

                 w si se permite la escritura, - si no lo está.

                 x si la ejecución está permitida, - si no lo está.

            Los siguientes son algunos ejemplos de notación simbólica:

                 -rwxr-xr-x: un archivo normal cuya clase de usuario tiene permisos completos y cuyo grupo y otras clases tienen solo permisos de lectura y ejecución.

                 crw-rw-r--: un archivo de caracteres especiales cuyas clases de usuario y grupo tienen permisos de lectura y escritura y cuyas otras clases solo tienen permiso de lectura.

                 dr-x------: un directorio cuya clase de usuario tiene permisos de lectura y ejecución y cuyo grupo y otras clases no tienen permisos.

            En algunos sistemas de permisos, los símbolos adicionales en la pantalla ls -l representan características de permisos adicionales:

                 El sufijo + (más) indica una lista de control de acceso que puede controlar permisos adicionales.
                 
                 . El sufijo (punto) indica que hay un contexto SELinux presente. Los detalles se pueden enumerar con el comando ls -Z.

                 El sufijo @ indica que los atributos de archivo extendidos están presentes.

            Para representar los atributos setuid, setgid y sticky o text, se modifica el carácter ejecutable (x o -).

            Aunque estos atributos afectan al archivo en general, no solo a los usuarios de una clase, el atributo setuid modifica el carácter ejecutable en la tríada para el usuario, el atributo setgid modifica el carácter ejecutable en la tríada para el grupo y el atributo adhesivo o de texto modifica el Carácter ejecutable en la tríada para otros. 

            Para los atributos setuid o setgid, en la primera o segunda tríada, x se convierte en s y - se convierte en S. 

            Para el atributo adhesivo o de texto, en la tercera tríada, x se convierte en t y - se convierte en T. Aquí hay un ejemplo :

                 -rwsr-Sr-t: un archivo cuya clase de usuario tiene permisos de lectura, escritura y ejecución; cuya clase grupal tiene permiso de lectura; cuya clase otros tiene permisos de lectura y ejecución; y que tiene establecidos los atributos setuid, setgid y sticky


        Grupo privado de usuarios:

            Algunos sistemas se diferencian del modelo POSIX tradicional de usuarios y grupos al crear un nuevo grupo (un "grupo privado de usuarios") para cada usuario. 

            Suponiendo que cada usuario es el único miembro de su grupo privado de usuarios, este esquema permite utilizar una umask de 002 sin permitir que otros usuarios escriban en archivos recién creados en directorios normales porque dichos archivos están asignados al grupo privado del usuario creador. 

            Sin embargo, cuando es deseable compartir archivos, el administrador puede crear un grupo que contenga los usuarios deseados, crear un directorio de escritura grupal asignado al nuevo grupo y, lo más importante, configurar el directorio como gid.

            Hacerlo setgid hará que los archivos creados en él se asignen al mismo grupo que el directorio y la umask 002 (habilitada mediante el uso de grupos privados de usuarios) garantizará que otros miembros del grupo puedan escribir en esos archivos.



|| Kernel


    User-space: 



|| System Call
    





|| GPU








