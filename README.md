# EvaluarExpresiones-java
Ejemplo de evaluar expresiones usando código de Java.

Evalúa expresiones simples de suma, resta, multiplicación, división y módulo, se pueden indicar paréntesis para cambiar la precedencia.
Para multiplicar se puede usar * o x, para dividir se puede usar / o :.

<br>

> **Nota:**
>
> Esta versión utiliza el tipo **double** para realizar las operaciones, por tanto, se pueden usar números con decimales (sin notación científica).
>
> Si quieres ver la versión que usa records para hacer las operaciones sigue este enlace: [EvaluarExpresiones-records-java](https://github.com/elGuille-info/EvaluarExpresiones-records-java)
>
<br>

Estoy usando el IDE [IntelliJ IDEA 2022.2.3 (Community Edition) de JetBrains](https://www.jetbrains.com/idea/whatsnew/) usando el SDK [openjdk-19 de Oracle](https://www.oracle.com/java/technologies/javase/jdk19-archive-downloads.html) instalado automáticamente por el IDE al usar características no incluidas en el que tenía instalado (versión 11.0.12).

<br>

## EvaluarExpresiones v1.1.2.* y v1.1.3.* del 21-nov-2022

> **Lo nuevo:** <br>
> Ahora evalúa bien los paréntesis con cualquier cantidad de niveles. <br>
> Si hay un paréntesis de apertura precedido por un dígito o de un paréntesis de cierre, se considera una multiplicación y se pone el signo *.<br>
> Si hay un paréntesis de cierre seguido de un dígito o de un paréntesis de apertura, se considera una multiplicación y se pone el signo *.<br>

<br>

## EvaluarExpresiones v1.1.1.* del 20-nov-2022
Detalles de lo que hace el evaluador de expresiones actualmente:

Salvo que surja algún error en otras expresiones diferentes a las comprobadas, la funcionalidad básica para trabajar con valores dobles (tipo double) no exponenciales está completada.

> **Lo que hace:**<br>
> Evalúa expresiones entre paréntesis (con varios niveles de anidación).<br>
> Evalúa primero los operadores multiplicativos (* y x para multiplicar, / y : para dividir y % para el módulo) y después los operadores aditivos (+ para sumar, - para restar).<br>
> La expresión pueden tener espacios, pero al evaluarla se quitan, por tanto: 1 5 * 2 se convierte en 15*2.<br>

<br>
Algunas de las expresiones comprobadas:

```
1.5*3+12-(-15+5)*2 + 10%3 = 37.5
1.5**3+12-(15+5)*2 + 10%3 = -22.5
2.5*5.5+1.5*2+22*5 = 126.75
1.5+2*5+3+4+22*5 = 128.5
15+2*5+3+4+22*5 = 142.0
1+2)*5+3+4 = 18.0
(1+2*5+3+4 = 18.0
((1+2)*(5+3+4) = 36.0
(1+2)*5+3+4 = 22.0
((1+2)*5+3+4) = 22.0
(1+2)*(5+3)+4 = 28.0
1+2*5+3+4 = 18.0
1 + 2 + 3 + 4*5 = 26.0
2*5 + 3*2 + 3 + 4*5 + 3*2 = 45.0

17 * ((12+5) * (7-2))  = 1445.0
1+2*3+6 = 13.0
99-15+2*7 = 98.0
36.0 / 2*(3) +4 = 58.0
6.0/2*(2+1) = 9.0
6.0/(2*(2+1)) = 1.0
2 - (10.0 * 2) / 6 = -1.3333333333333335

```

