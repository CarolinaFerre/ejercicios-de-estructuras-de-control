# ejercicios-de-estructuras-de-control


INSTRUCCIONES Y SENTENCIAS DE CONTROL EN JAVA
Instrucción secuencial Simple / Compuesta
 Simple : Instrucción; ( Siempre termina con punto y coma )
 Compuesta o Bloque de instrucciones ( Entre llaves )
 {
               Instrucción;
               Instrucción;
      }
Sentencia alternativa simple SI
if ( Condición)
 Instrucción S/C
[else
 Instrucción S/C ]
if (expresion_1)
sentencia_1;
else if (expresion_2)
sentencia_2;
else if (expresion_3)
sentencia_3;
else if (...)
...
[else
sentencia_n;]
Cuando hay varios if anidados se supone que el else es del if más próximo.
Ejemplos: 
/* Simula una clave numérica de acceso, con 
un único intento */
...
int Usuario, Clave=18276;
...
if ( Usuario == Clave )
   {
    System.out.println("Acceso permitido");
    System.out.println(“Enhorabuena”);
    }   
  else
   {
    System.out.println("Acceso denegado");
    }
...
/* Escribe bebé‚,niño, joven o adulto */
...
   int edad;
...
   if (edad<0)
      System.out.println("No es una edad 
correcta.");
   else if (edad<3) 
System.out.println("Eres un bebé‚");
   else if (edad<13) 
System.out.println("Eres un niño");
   else if (edad<18) 
System.out.println("Eres un joven");
   else
System.out.println("Eres un adulto");
...
En todas las sentencias alternativas o 
repetitivas es siempre preferible utilizar 
un bloque de instrucciones aunque sólo 
se incluya una instrucción.
El formato:
if ( Contador > 0 )
 {
 Suma = Suma + Contador;
 }
Es Preferible a:
if ( Contador > 0 )
 Suma = Suma + Contador;
Operador Condicional ( SI – simplificado en una instrucción )
valor = ( expresión lógica)? valor si cierto: valor si falso;
Ejemplos:
mayor = ( Num1 > Num2)? Num1:Num2;
String Mensaje = (Saldo < 0)? "CORRECTO": "SALDO NEGATIVO";
SENTENCIA ALTERNATIVA MÚLTIPLE (SEGÚN)
switch (expresión) {
case expresión_cte_1: sentencia_1;
                      sentencia_12;
[break] 
case expresión_cte_2: sentencia_2;
       ...
case expresión_cte_n: sentencia_n;
[default: sentencia;]
}
Ejemplo
...
   int dia;
...
   switch (dia )
     {
      case 1: System.out.println("Lunes"); break;
      case 2: System.out.println("Martes"); break;
      case 3: System.out.println("Miércoles"); break;
      case 4: System.out.println("Jueves"); break;
      case 5: System.out.println("Viernes"); break;
      case 6: System.out.println("Sábado"); break;
      case 7: System.out.println("Domingo"); break;
      default: System.out.println(" ­ Valor erróneo ­");
     }
...
Ejercicio: Dada las siguientes instrucciones, indicar cual seria las funciones ejecutadas según los 
valores de la variable letra = A,a,B,b,C,c,t,M,R
switch ( letra )
{
   case ‘A’:
   case ‘a’: Hacer.menuA ();
             break;
   case ‘B’: Hacer.menuB()
             break;
   case ‘b’: Hacer.menub()
             break;
   case ‘C’: Hacer.menuC();
   case ‘c’: Hacer.menuc();
             break;
   case ‘t’: Hacer.menut();
             break;
default    : Hacer.menuX();
}
El funcionamiento de la instrucción 
switch es un poco peculiar:
Si la expresión coincide con algún caso,
se ejecutan las instrucciones de la parte
derecha y se continua con las
instrucciones de los siguientes casos a no
ser que exista una instrucción break que
provoque la salida del switch.
Solución:
‘A’ menuA()
‘a’­> menuA()
‘B’­> menuB()
‘b’­>menub()
‘C’­> menuC() y menuc()
‘c’­> menuc()
‘t’­> menut()
‘M’­> menuX()
‘R’­> menuX()
SENTENCIAS REPETITIVAS
MIENTRAS
while ( Condición  )
    {
     Instrucciones;
    }
REPETIR (OJO: mientras no hasta )
do
   {
   Instrucciones;
   }
while ( Condición );
Ejemplos:
Se hace mientras num sea 
mayor que 0
Cuando num vale cero termina,
pero decrementa antes. 
Siempre se hace una vez aunque 
inicialmente num fuera 0
num= 5;
while ( num > 0 )
  {
  Hacer.algo(num)
  num­­;
  }
Se hace:5,4,3,2,1
num = 5; 
while ( ­­num != 0 )
   {
   Hacer.algo(num);
  }
Se hace: 4,3,2,1
num = 5;
do
  {
  Hacer.algo(num);
  num­­;
  }
while ( num > 0)
Se hace 5,4,3,2,1
Ciclo infinito
while ( true )  
       {           
       Hacer.algo();
       }    
Hace siempre 
CICLO PARA
 
Ejemplos:
Ciclo en incremento Ciclo en decremento Ciclo combinado
for (int i=1;i<= 10; i++)  
    {
     System.out.println(i);
     }
Resultado:
1,2,3,4,5,6,7,8,9,10
for (int i=10; i>0; i­­ )
      {
      System.out.println(i);
      }
Resultado:
10,9,8,7,6,5,4,3,2,1
for (int i=0,j=5; i<j;i++,j­­)
    {
   System.out.println(i+":"+j);
    }
Resultado
0:5 ,  1:4 ,  2:3
for ( Valores iniciales; Condición ; Incrementos )
 {
 Instrucciones;
 }
Formatos menos habituales 
No hay inicialización, ni el incremento Ciclo infinito
for ( ; i > 0 ;  )
    {
    i­­;
    }
for ( ; ; )
    {
     Hacer.algo();
    }
Incrementos distintos de 1 Decrementos distintos de 1
for ( int i= 1; i <= 10; i+=2 )  
    {
     System.out.println(i);  
     }
Resultado:
1,3,5,7,9
for ( int i = 10;  i >  0; i­=3 )
      {
      System.out.println(i);  
      }
Resultado:
10,7,4,1
Lo normal es definir los índices dentro del propio ciclo for para evitar su uso fuera del ciclo, lo que
se considera una práctica incorrecta.
BIEN, La variable i no se puede 
usar fuera del ciclo for
MAL, la variable i se tiene que 
definir antes y se puede usar 
después. 
for (int i=0; i< 10; i++)
    {
    Hacer.Algo(i);
    }
i = valor; // Da fallo la 
variable i ya no existe.
int i;
for (i=0;i<10; i++)
    {
     Hacer.algo(i);
    }
i = valor; // No da fallo
INTERRUPCIONES DE CICLOS:
 Sentencia continue:
Esta instrucción, cuando aparece dentro de cualquier ciclo (while, do while, for), salta las sentencias
que se repiten y vuelve a evaluar la condición del ciclo.
/* Escribe del 1 al 100 menos los múltiplos de 11 */
 int Num =1;
 while (Num <=100)
 {
 if ( (Num % 11)==0)
 {
 Num ++;
continue;
 }
 System.out.println( Num);
 Num ++;
 }
 Sentencia break
Esta instrucción provoca la salida y la terminación inmediata del ciclo.
/* Calcula la suma 100 números, pero si encuentra el número cero termina inmediatamente */
 int Num, Suma, i ;
 Suma = 0;
 for (i=1; i <= 100; i++ )
 {
 Num = sc.nextInt();
 if ( Num == 0 )
 {
 break;
 }
 Suma = Suma + Num;
 }
 System.out.println(“ El resultado es ” + Suma);
}
Algunos autores no recomiendan en uso de las sentencias break y 
continue, pues si somos fieles a la programación estructura, no 
deberíamos usarlas al existir alternativas. 
Ej.-
i =1;
while ( i <= 100 && Num != 0)
{
Num = sc.nextInt();
Suma = Suma + Num;
i++;
}
RECOMENDACIÓN:
 En principio cualquier ciclo de programación se puede realizar con las estructuras for, while o dowhile, sin embargo cada tipo de ciclo es adecuado para un tipo de algoritmos característicos.
Estructura Uso
while Cuando el ciclo se va a realizar 0 o más veces.
Es utilizado para leer ficheros o estructuras de datos que pueden estar vacías
do-while Cuando el ciclo se va realizar 1 o más veces 
Por ejemplo para mostrar un menú de opciones
for Si se sabe el número de veces que se ha de repetir el bucle.
Si utilizar la inicialización y la actualización del bucle permite escribir el
código de forma más clara.
Se realiza un recorrido en una estructura de almacenamiento como las tablas
con un tamaño conocido
