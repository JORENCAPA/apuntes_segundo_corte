Introducción
Los métodos algebráicos son herramientas que permiten modificar la función de transferencia en lazo cerrado de un sistema, con el fin de obtener una respuesta deseada. Existen dos enfoques principales:

Igualación de modelos
Igualación de coeficientes
Igualación de Modelo
Este método permite diseñar un controlador C(z) tal que se obtenga una función de transferencia de lazo cerrado Go(z) deseada, a partir de una función de lazo abierto conocida G(z) .

El proceso de igualación de modelo puede expresarse matemáticamente como:

GRAMO
𝑜
(
el
)
=
do
(
el
)
GRAMO
(
el
)
1
+
do
(
el
)
GRAMO
(
el
)
GRAMO 
o
​
 ( y )= 
1+C ( z ) G ( z )
C ( z ) G ( z )
​
 
De esta ecuación, podemos despejar el controlador:

do
(
el
)
=
GRAMO
𝑜
(
el
)
GRAMO
(
el
)
⋅
[
1
−
GRAMO
𝑜
(
el
)
]
C ( z )= 
G ( z )⋅[ 1−GRAMO 
o
​
 ( z )]
GRAMO 
o
​
 ( y )
​
 
Condiciones :

Si G(z) tiene polos fuera del círculo unitario o varios polos en z=-1 , no se puede implementar una retroalimentación unitaria.
Ejemplo 1: Diseño de Controlador
Dado un sistema con:

Función de lazo cerrado deseada:

GRAMO
𝑜
(
el
)
=
0,009
el
+
0,008
el
2
−
1.801
el
+
0,818
GRAMO 
o
​
 ( y )= 
el 
2
 −1.801 z+0,818
0,009 z+0,008
​
 
Función de lazo abierto:

GRAMO
(
el
)
=
0,004
(
el
+
1
)
el
2
−
1.819
el
+
0,8187
G ( z )= 
el 
2
 −1.819 z+0,8187
0,004 ( z+1 )
​
 
Se busca un controlador C(z) que cumpla con las siguientes especificaciones:

Estabilidad
Comportamiento subamortiguado
Sobreimpulso menor al 5%
Aplicando la ecuación de igualación de modelo, se obtiene el controlador:

do
(
el
)
=
(
0,009
el
+
0,008
)
(
el
2
−
1.819
el
+
0,8187
)
(
0,004
(
el
+
1
)
)
[
el
2
−
1.801
el
+
0,818
−
(
0,009
el
+
0,008
)
]
C ( z )= 
( 0,004 ( z+1 )) [ en 
2
 −1.801 z+0,818−( 0,009 z+0,008 )]
( 0,009 z+0,008 ) ( z 
2
 −1.819 z+0,8187 )
​
 
Simplificando:

do
(
el
)
=
1.997
el
2
+
0,233
el
−
1.529
el
2
+
0,125
el
−
0,757
C ( z )= 
el 
2
 +0,125 z−0,757
1.997 z 
2
 +0,233 z−1.529
​
 
Este controlador garantiza una respuesta estable y subamortiguada.

Igualación de coeficientes
La igualación de coeficientes es otro método que permite diseñar un controlador mediante la ubicación deseada de los polos del sistema en lazo cerrado.

Se parte de una función de lazo abierto G(z) conocida.
A partir de la ubicación de los polos deseados, se determina un polinomio característico para el sistema en lazo cerrado.
El controlador C(z) se diseña de tal manera que el sistema en lazo cerrado cumpla con dicho polinomio.
Ejemplo 2: Controlador Proporcional

Dado un sistema:

GRAMO
(
el
)
=
0,0043
el
2
−
1.819
el
+
0,8187
G ( z )= 
el 
2
 −1.819 z+0,8187
0,0043
​
 
Y los polos deseados:

PAG
1
=
0,91
+
yo
0,23
,
PAG
2
=
0,91
−
yo
0,23
PAG 
1
​
 =0,91+j 0,23 ,PAG 
2
​
 =0,91−0,23​
El polinomio característico deseado es:

el
2
−
1.82
el
+
0,881
el 
2
 −1,82 z+0,881
Aplicando la igualación de coeficientes , se obtiene que K = 14.48 para un controlador proporcional que logre esta ubicación de polos.


Análisis de frecuencia
Introducción
El análisis en frecuencia es un enfoque para estudiar sistemas dinámicos, observando su comportamiento a la salida en respuesta a cambios de frecuencia en la entrada. Se basa en la suposición de que el sistema tiene un comportamiento lineal y se utilizan señales sinusoidales de la forma:

𝑅
=
𝐴
⋅
pecado
⁡
(
𝜔
𝑎
yo
+
𝜃
)
R=A⋅pecado ( ωk T+θ )
Al variar la frecuencia de la señal de entrada, se producen variaciones tanto en la amplitud como en la fase de la señal de salida.

Representación en Fasores
Las señales sinusoidales son convenientes porque se pueden representar en fasores , los cuales asumen una frecuencia constante y describen las señales únicamente en términos de amplitud y fase.

𝑅
(
𝑎
)
=
𝐴
⋅
pecado
⁡
(
𝜔
𝑎
yo
+
𝜙
)
R ( t )=A⋅pecado ( ωk T+ϕ )
𝑅
=
𝐴
∠
𝜙
R=A ∠ ϕ
Cuando tanto la entrada como la salida se representan mediante fasores, es posible describir el sistema en esta misma forma.

Ejemplo de sistema en factores
Supongamos que tenemos un sistema representado por la función de transferencia
GRAMO
(
𝑠
)
G ( s ). Si la entrada y la salida se representan como factores:

𝐴
2
⋅
pecado
⁡
(
𝜔
1
𝑎
yo
+
𝜙
2
)
𝐴
1
⋅
pecado
⁡
(
𝜔
1
𝑎
yo
+
𝜙
1
)
=
METRO
⋅
∠
𝜙
A 
1
​
 ⋅pecado ( ω 
1
​
 yo​+ϕ 
1
​
 )
A 
2
​
 ⋅pecado ( ω 
1
​
 yo​+ϕ 
2
​
 )
​
 =METRO⋅∠ ϕ
Dónde:

METRO
=
𝐴
2
𝐴
1
METRO= 
A 
1
​
 
A 
2
​
 
​
 
𝜙
=
𝜙
2
−
𝜙
1
ϕ=ϕ 
2
​
 −ϕ 
1
​
 
Este resultado no depende de la frecuencia.

Expresión de la Función de Transferencia en Términos de la Frecuencia
La función de transferencia
yo
(
el
)
H ( z )puede expresarse en el dominio de la frecuencia reemplazando
el
=
mi
yo
𝜔
yo
el=mi 
jω T
 :

yo
(
mi
yo
𝜔
yo
)
=
1
(
mi
yo
𝜔
yo
−
0,1
)
(
mi
yo
𝜔
yo
−
5
)
Él​​ 
jω T
 )= 
( mi 
jω T
 −0,1 ) ( mi 
jω T
 −5 )
1
​
 
Esta expresión se puede descomponer en su parte real e imaginaria para obtener la magnitud y fase en el dominio de la frecuencia.

Diagramas de Bode
El diagrama de Bode es una representación gráfica de cómo varía la magnitud y fase de un sistema en función de la frecuencia. La magnitud se representa en decibelios.
𝑑
𝐵
el B, donde:

𝐴
𝑑
𝐵
=
20
registro
⁡
10
𝐴
A 
el B
​
 =20registro​ 
10
​
 A
Ejemplo de diagrama de Bode
Dada la función de transferencia:

GRAMO
(
𝑠
)
=
1
𝑠
+
10
G ( s )= 
s+10
1
​
 
Al discretizarla con un tiempo de muestreo
yo
=
0,1
yo=0,1seg, se obtiene:

GRAMO
el
=
0,06321
el
−
0,3679
GRAMO 
el
​
 = 
el−0,3679
0,06321
​
 
Utilizando la transformada
el
el, obtendremos:

GRAMO
el
=
0,924
−
0,05
el
el
+
9.242
GRAMO 
el
​
 = 
el+9.242
0,924−0,05 W
​
 
Relación entre Respuesta Temporal y Frecuencia
Es posible obtener una relación entre la respuesta en frecuencia en lazo abierto y la respuesta temporal en lazo cerrado . Por ejemplo, el overshoot está relacionado con el factor de amortiguamiento
𝑜
omediante la siguiente expresión:

𝑜
=
En
⁡
(
METRO
pag
)
𝜋
2
+
(
En
⁡
(
METRO
pag
)
)
2
o= 
π 
2
 +( en ( M 
pag
​
 ) ) 
2
 
en ( M 
pag
​
 )
​
 
Dónde
METRO
pag
METRO 
pag
​
 es el pico de resonancia .

Ejemplo de texto completo
Vamos a calcular el diagrama de Bode para el sistema descrito por la siguiente función de transferencia en lazo abierta:

GRAMO
=
8
el
2
+
0,5
el
+
1
GRAMO= 
el 
2
 +0,5 W+1
8
​
 
El pico de repercusión
METRO
𝑎
METRO 
a
​
 es 5,82 dB.
El sobreimpulso
METRO
pag
METRO 
pag
​
 es 0,7621.
El factor de amortiguamiento
𝑜
oes 0,083.
Este es el diagrama de Bode correspondiente a este sistema.


Diseño de Redes de Atraso
Introducción
El diseño de controladores a través del análisis en frecuencia permite visualizar las características de un sistema de control, como los márgenes de estabilidad y el error en estado estacionario. A través de los diagramas de Bode, se puede diseñar compensadores de adelanto y atraso de fase para mejo.
![image](https://github.com/user-attachments/assets/77526408-070c-4fae-a396-2c6f27128e4f)


Con
Ade
Aum
Mejor
Aum
Atrás
Re
Des
Minimizar
Atraso-Adel
Con
Control
El control PID es un caso especial de una red de adelanto-atraso. Ley de PD su parteLey PI

Mar
Estos mares

Margen de ganancia (MG) :
Margen de fase (MP):Indica cuanto
Ejemplo de
Supongamos un sistema con la siguiente

GRAMO
(
el
)
=
1
el
(
el
+
2
)
G ( w )= 
y ( y + 2 )
1
​
 

Queremos diseñar

Error de estado estacionario
mi
en
≤
10
mi 
en
​
 ≤10.
Margen de fase
METRO
PAG
≥
60
°
Diputado≥60°.
Margen de ganancia
METRO
GRAMO
≥
12
𝑑
𝐵
M.S.≥12 días B.
Paso
Remilgado

mi
en
=
límite
⁡
el
→
0
1
el
⋅
1
GRAMO
(
el
)
=
2
𝐾
pag
mi 
en
​
 =límite 
y → 0
​
  
el
1
​
 ⋅ 
G ( w )
1
​
 = 
K 
pag
​
 
2
​
 

Para cumplir con
mi
en
≤
0,1
mi 
en
​
 ≤0,1,
𝐾
pag
≥
20
K 
pag
​
 ≥20.

Paso 2: Diseño de la compensación
La red de atraso tiene la siguiente forma:

do
(
el
)
=
1
+
𝑎
yo
1
el
1
+
yo
1
el
,
0
<
𝑎
<
1
C ( en )= 
1 + T 
1
​
 el
1 + una T 
1
​
 el
​
 ,0<a<1

Para calcular los parámetros de

Medimos el margen de fase actual y calculamos la frecuencia a la que se debe mejorar el m
Definimos
yo
1
yo 
1
​
 Pensilvania
Paso 3: Cálculo de
yo
1
yo 
1
​
 
Utilizando las fórmulas de di

𝛼
=
−
20
log
⁡
(
𝑎
)
,
𝑇
1
=
10
𝑎
⋅
𝜔
𝐺
α=−20log(a),T 
1
​
 = 
a⋅ω 
G
​
 
10
​
 
donde
𝜔
GRAMO
ω 
GRAMO
​
 es la

Conclusión
El diseño de redes de atraso mejora la respuesta del sistema en frecuencias altas y bajas. Este proceso es fundamental en sistemas de control digital, y el análisis en frecuencia propo.
![image](https://github.com/user-attachments/assets/3737bce7-e6ca-48ee-b467-30647801fdfc)

