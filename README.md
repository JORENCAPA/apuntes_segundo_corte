# Introducción a los Métodos Algebraicos

Los métodos algebraicos en control digital permiten ajustar el comportamiento de un sistema en lazo cerrado mediante la modificación de su función de transferencia. Estos métodos son claves cuando se busca cumplir requisitos específicos de estabilidad y respuesta en sistemas controlados digitalmente.

## Objetivo

El objetivo es diseñar controladores que, al integrarse en el sistema, modifiquen su comportamiento hasta obtener la respuesta deseada. Para esto, existen dos enfoques principales:

- **Igualación de Modelo**
- **Igualación de Coeficientes**

### 1. Igualación de Modelo

**Conceptos clave:**
- \( G(z) \): Función de transferencia en lazo abierto.
- \( G_0(z) \): Función de transferencia deseada en lazo cerrado.
- \( C(z) \): Función de transferencia del controlador.

**Procedimiento:**
Se parte de una función conocida \( G(z) \) (lazo abierto) y una respuesta deseada \( G_0(z) \) (lazo cerrado). El objetivo es encontrar el controlador \( C(z) \) que asegure que el sistema se comporta como \( G_0(z) \).

**Fórmula principal:**
Para encontrar el controlador, se utiliza la siguiente relación:

\[
C(z) = \frac{G_0(z)}{G(z) \cdot (1 - G_0(z))}
\]

Esta fórmula nos permite ajustar el controlador de tal forma que la función de transferencia del sistema en lazo cerrado cumpla con la especificación de \( G_0(z) \).

**Ejemplo de diseño de controlador:**

Dada la función en lazo abierto \( G(z) \):

\[
G(z) = \frac{0.004(z + 1)}{z^2 - 1.819z + 0.8187}
\]

Y la función deseada en lazo cerrado \( G_0(z) \):

\[
G_0(z) = \frac{0.009z + 0.008}{z^2 - 1.801z + 0.818}
\]

Aplicamos la fórmula para obtener \( C(z) \):

\[
C(z) = \frac{(0.009z + 0.008)(z^2 - 1.819z + 0.8187)}{0.004(z + 1)(z^2 - 1.801z + 0.818 - 0.009z - 0.008)}
\]

Simplificamos:

\[
C(z) = \frac{1.997z^2 + 0.233z - 1.529}{z^2 + 0.125z - 0.757}
\]

Este es el controlador que debe implementarse para lograr la respuesta deseada.

**Consideraciones:**
Si \( G(z) \) tiene polos fuera del círculo unitario o más de dos en \( z = -1 \), la retroalimentación unitaria no puede implementarse.

### 2. Igualación de Coeficientes

**Conceptos clave:**
Este método se basa en ajustar el sistema en función de los polos que se desean en lazo cerrado. Estos polos se representan en un polinomio característico que debe satisfacer la respuesta deseada.

**Procedimiento:**
Se parte de \( G(z) \) conocida y se define la ubicación deseada de los polos del sistema en lazo cerrado. A partir de esta información, se obtiene el polinomio característico, el cual se iguala con el polinomio en lazo cerrado generado por el controlador.

**Ejemplo de diseño de controlador proporcional:**

Dada la función:

\[
G(z) = \frac{0.0043}{z^2 - 1.819z + 0.8187}
\]

Se desea que los polos estén en:

\[
P_1 = 0.91 + i0.23, \quad P_2 = 0.91 - i0.23
\]

Esto genera un polinomio característico deseado:

\[
z^2 - 1.82z + 0.881
\]

Para ubicar los polos en las posiciones deseadas, se calcula el controlador \( K \) que satisface la ecuación:

\[
K \cdot 0.0043 = 0.881 - (z^2 - 1.819z + 0.8187)
\]

Al resolver, \( K \) será aproximadamente 14.48. Sin embargo, este valor indica que no se puede solucionar solo con acción proporcional.

**Consideraciones:**
En este método, se ubican los polos, pero no se tiene control sobre los ceros del sistema.

### 3. Ecuaciones Diofánticas

Para resolver sistemas de control más complejos, es común utilizar las ecuaciones diofánticas, las cuales permiten simplificar el problema de encontrar los coeficientes del controlador.

**Ejemplo:**

Para una función de transferencia en lazo abierto \( G(z) \):

\[
G(z) = \frac{0.005 + 0.005z}{z^2 - 2z + 1}
\]

Se desea un polinomio característico:

\[
z^3 + 0.6z^2 + 0.12z + 0.008
\]

Se plantean ecuaciones diofánticas para resolver los coeficientes \( A_0, B_0, A_1, B_1 \), lo que facilita el diseño del controlador.

## Conclusiones

- **Igualación de Modelo:** Permite controlar completamente la función de transferencia deseada.
- **Igualación de Coeficientes:** Ofrece un enfoque más sencillo, pero no permite controlar la ubicación de los ceros.
- **Ecuaciones Diofánticas:** Son útiles para simplificar el proceso de igualación de coeficientes en sistemas de orden superior.

# Gráfica del Controlador Diseñado con Igualación de Modelo

Dada la función de transferencia en lazo abierto:

\[
G(z) = \frac{0.004(z + 1)}{z^2 - 1.819z + 0.8187}
\]

Y la función deseada en lazo cerrado:

\[
G_0(z) = \frac{0.009z + 0.008}{z^2 - 1.801z + 0.818}
\]

El controlador diseñado es:

\[
C(z) = \frac{z^2 + 0.125z - 0.757}{1.997z^2 + 0.233z - 1.529}
\]

## Gráfica del Ejemplo con Igualación de Coeficientes

Dada la función de transferencia en lazo abierto:

\[
G(z) = \frac{0.0043}{z^2 - 1.819z + 0.8187}
\]

Los polos deseados son:

\[
P_1 = 0.91 + i0.23, \quad P_2 = 0.91 - i0.23
\]

Voy a generar las gráficas basadas en estos ejemplos. Dame un momento para preparar las simulaciones.

---

![image](https://github.com/user-attachments/assets/88d4ec54-d5b8-4801-9044-a5ef1f05d14b)
![image](https://github.com/user-attachments/assets/a11d5b85-da07-4cc5-979a-084ace37d925)



#### Igualación de Modelo:

Se muestra la respuesta al impulso para \( G(z) \) (lazo abierto) y \( G_0(z) \) (lazo cerrado deseado). La gráfica compara cómo el sistema en lazo cerrado se ajusta a la respuesta deseada utilizando el controlador diseñado.

#### Igualación de Coeficientes:

La segunda gráfica muestra la respuesta al impulso de \( G(z) \) y el sistema con los polos deseados. Se puede observar cómo el sistema en lazo abierto responde en comparación con la respuesta deseada cuando se colocan los polos específicos.

# Introducción al Análisis en Frecuencia

## Objetivo:
El análisis en frecuencia estudia cómo un sistema dinámico responde a señales sinusoidales de entrada a diferentes frecuencias. Este enfoque es útil para determinar la estabilidad y el comportamiento del sistema a través de variaciones en la amplitud y fase de la salida.

## Fundamentos:
Se analiza un sistema aplicando una señal de entrada sinusoidal de la forma:
\[
R(t) = A\sin(\omega t + \theta)
\]
Si el sistema es lineal, la salida también será sinusoidal, pero con una amplitud y fase distintas:
\[
Y(t) = A'\sin(\omega t + \phi)
\]
- **Amplitud:** \( A' \)
- **Fase:** \( \phi \)

### 1. Representación Matemática con Factores
Las señales sinusoidales se representan en forma de fasores, lo que simplifica el análisis en términos de amplitud y fase:
\[
R = A \angle \phi
\]
En este enfoque, la frecuencia está implícita, y solo se manejan los cambios en amplitud y fase.

### 2. Ejemplo - Función de Transferencia en el Dominio de la Frecuencia
Dada la siguiente función de transferencia con un tiempo de muestreo \( T = 0.1 \) segundos:
\[
H(z) = \frac{1}{(z - 0.1)(z - 5)}
\]
La función de transferencia se puede expresar en el dominio de la frecuencia usando la relación \( z = e^{j\omega T} \):
\[
H(e^{j\omega T}) = \frac{1}{(e^{j\omega T} - 0.1)(e^{j\omega T} - 5)}
\]
Expresando esto en términos de \( \cos(\omega T) \) y \( \sin(\omega T) \):
\[
H(e^{j\omega T}) = \frac{1}{\cos^2(\omega T) - \sin^2(\omega T) - 5.1\sin(\omega T) - 5.1\cos(\omega T) + 0.5}
\]
La función de transferencia ahora está separada en parte real e imaginaria, lo que nos permite graficar la magnitud y la fase en función de la frecuencia.

### 3. Diagramas de Frecuencia y Diagramas de Bode
Los diagramas de Bode muestran cómo varía la magnitud y la fase del sistema conforme la frecuencia de la entrada cambia. Estos diagramas suelen graficarse en escalas logarítmicas:
- **Magnitud en decibelios (dB):**
\[
A_{dB} = 20 \log_{10}(A)
\]
- **Fase en grados.**

### 4. Ejemplo - Análisis en Frecuencia en Tiempo Discreto
Dado un sistema continuo:
\[
G(s) = \frac{1}{s + 10}
\]
Su equivalente en tiempo discreto (con \( T = 0.1 \)) es:
\[
G(z) = \frac{0.06321}{z - 0.3679}
\]
Aplicando la transformación bilineal para obtener su versión en el dominio \( z \):
\[
G(w) = \frac{0.924 - 0.05}{z + 9.242}
\]
Este sistema presenta una ganancia y un polo similar al sistema continuo, pero también aparece un cero que no estaba presente originalmente en el sistema continuo.

#### Análisis a diferentes tiempos de muestreo:
Para \( T = 0.1 \), \( T = 0.01 \) seg y \( T = 0.001 \) seg, se obtienen diferentes comportamientos de magnitud y fase.

### 5. Ejemplo - Relación entre Respuesta en Frecuencia y Respuesta Temporal
Un sistema en lazo cerrado con la siguiente función de transferencia:
\[
G(s) = \frac{8}{s^2 + 0.5s + 1}
\]
Su función de transferencia en lazo cerrado es:
\[
G_0 = \frac{8}{s^2 + 0.5s + 9}
\]
Al analizar la respuesta al escalón, se obtiene el overshoot \( M_p = 0.7621 \), y el coeficiente de amortiguamiento es:
\[
\zeta = \frac{\ln(0.7621)}{\pi + \ln^2(0.7621)} = 0.083
\]
El pico resonante \( M_r \) en el diagrama de Bode para este sistema es:
\[
M_r = 5.82 \, dB
\]

## Gráficas

---
![image](https://github.com/user-attachments/assets/74c32e75-847e-402a-849c-5aba1de1147b)
![image](https://github.com/user-attachments/assets/e7eb0bcb-db3d-482a-bd23-9662c2cbf0d9)



#### Diagrama de Bode - Ejemplo 1:
Representa la función de transferencia en frecuencia para \( H(z) = \frac{1}{(z - 0.1)(z - 5)} \), con magnitud y fase en función de la frecuencia.

#### Diagrama de Bode - Ejemplo 2 (Tiempo Discreto):
Representa el sistema discreto \( G(z) = \frac{0.06321}{z - 0.3679} \), mostrando cómo se comporta en términos de magnitud y fase.

# Ventajas del Diseño Basado en el Diagrama de Bode

## 1. Ventajas del Diagrama de Bode
El diagrama de Bode permite visualizar el error en estado estacionario y analizar los márgenes de estabilidad de un sistema. Además:
- Se pueden medir directamente los márgenes de estabilidad en frecuencia.
- El diseño es similar al utilizado en tiempo continuo, aplicando la transformada \( w \).

## 2. Tipos de Controladores por Análisis en Frecuencia

### Adelanto de Fase
- **Ventajas:** Aumenta el ancho de banda y los márgenes de estabilidad, mejorando la velocidad del sistema.
- **Desventajas:** Puede amplificar el ruido en frecuencias altas.

### Atraso de Fase
- **Ventajas:** Reduce la ganancia en frecuencias altas, mejorando la atenuación del ruido.
- **Desventajas:** Disminuye el ancho de banda y la velocidad del sistema.

### Atraso-Adelanto de Fase
- **Ventajas:** Combina los beneficios de ambos compensadores, mejorando los márgenes de estabilidad, aumentando el ancho de banda y reduciendo el error en estado estacionario sin afectar tanto el ruido.

### Control PID
Un controlador PID es un caso especial de una red de atraso-adelanto:
- **PD:** Afecta las altas frecuencias y mejora la estabilidad.
- **PI:** Actúa como una red de atraso, corrigiendo el error en estado estacionario.

## 3. Márgenes de Fase y Ganancia
- **Margen de Ganancia (MG):** Es el cambio en la ganancia que haría que el sistema en lazo cerrado sea inestable. Se mide en dB.
- **Margen de Fase (MF):** Es el cambio en la fase que haría inestable el sistema. Se mide en grados, tomando como referencia la ganancia unitaria (0 dB).

Para que el sistema sea estable, ambos márgenes deben ser positivos.

## 4. Procedimiento de Diseño de una Red de Atraso

### Pasos:
1. Discretizar la planta para obtener \( G(z) \).
2. Transformar \( G(z) \) a \( G(w) \).
3. Graficar los diagramas de Bode para \( G(w) \).
4. Aplicar el método de diseño para obtener \( C(z) \).
5. Recuperar \( C(z) \) desde \( G(w) \).

### Ejemplo:
Dada una función de transferencia:
\[
G(w) = \frac{1}{w(w + 2)}
\]
Se requiere cumplir los siguientes criterios:
- \( e_{ss} \leq 0.1 \)
- \( M_f \geq 60^\circ \)
- \( M_g \geq 12 \, \text{dB} \)

Para corregir el error en estado estacionario, se calcula:
\[
e_{ss} = \lim_{w \to 0} \frac{1}{w G(w)} = \frac{2}{K_p}, \text{donde } K_p \geq 20
\]

## 5. Diseño de una Red de Atraso
La función de la red de atraso es:
\[
C(w) = \frac{1 + \tau_1 w}{1 + \tau_2 w}, \text{donde } 0 < \alpha < 1
\]

### Procedimiento:
1. Calcular \( K_p \) para garantizar el requerimiento de error.
2. Medir los márgenes teniendo en cuenta \( K_p \).
3. Calcular la frecuencia que cumple \( M_f + 6^\circ \), que será el nuevo \( \omega_c \).
4. Medir la atenuación necesaria para cumplir con el margen de fase.
5. Calcular \( \tau_1 \) usando la fórmula:
\[
\tau_1 = \frac{10^a}{\omega_c}, \text{donde } a \text{ se calcula a partir de la atenuación en dB}.
\]

\[
\alpha = 20 \log a \Rightarrow a = 10^{-\alpha / 20}
\]

## 6. Ejemplo de Aplicación

Para una red de atraso con \( \alpha = 20 \, \text{dB} \):
\[
a = 0.1
\]
Si la frecuencia de cruce de la ganancia es \( \omega_c = 0.908 \), el valor de \( \tau_1 \) es:
\[
\tau_1 = \frac{10 \times 0.1}{0.908} = 110.13
\]

### Resultados:
- El diagrama de Bode en lazo abierto muestra que se cumple el margen de fase y magnitud requeridos.
- El diagrama de Bode en lazo cerrado y la respuesta temporal verifican la estabilidad y comportamiento deseado del sistema.
![image](https://github.com/user-attachments/assets/12d8cf84-70cd-47fc-af47-05e293fa824c)

# Gráfica de la Red de Atraso

Este diagrama muestra cómo varían la magnitud y la fase en función de la frecuencia, siguiendo el diseño de la red con los siguientes parámetros:
- \( a = 0.1 \)
- \( \tau_1 = 110.13 \)

La gráfica permite observar cómo la red de atraso afecta al sistema en diferentes frecuencias, mostrando los cambios en la respuesta del sistema al aplicar esta compensación. Estos cambios incluyen:
- Atenuación de la ganancia en frecuencias bajas y medias.
- Un ajuste de fase que mejora el margen de estabilidad del sistema.

Esta visualización es útil para analizar el comportamiento del sistema y asegurar que los requisitos de margen de fase y ganancia se cumplen dentro del rango de frecuencias deseado.


