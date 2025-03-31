# Cuaderno_De_Ejercicios1
*Ejercicio 1*

- Para un sistema de comunicaciones con 17 niveles de señal, que funciona en banda base, calcular el máximo ancho de banda si el ruido es despreciable y la tasa de transmisión es de 10 Mbits/s. ¿Qué tipo de medio guiado se podría utilizar para el sistema?

La capacidad se calcula con la formula de Nyquist: $T = 2H * log_2(V)$  
T = Capacidad maxima  
H = Ancho de banda
V = niveles de señal  

$H = \frac{T}{2 * log_2(v)} = \frac{1 * 10^{7}}{2 * log_2(17)} = 1.23MHz$

Dado que el ancho de banda calculado es dde 1.23MHz se podrían utilizar como medio de transmisión guiado el par trenzado, de ancho de banda de *16MHz*(Categoría 2) a *600MHz*(Categoria 7), el coaxial, con ancho de banda de aproximadamente un GHz, o fibra optica. Aunque el par trenzado seria mas que suficiente y el mas económico.


*Ejericio 2*

- ¿Cuál es la tasa de transmisión máxima en un canal óptico con fibra de ancho de banda de 1 THz y conversores optoeléctricos de 100 Gbaudios, si la relación SNR es de 15 dB y la modulación utilizada en los conversores es de 4 símbolos en cuadratura?

La capacidad del canal se calcula con la ecuación de Shannon:  
$C = B * log_2(1 + SNR)$

$C = 1 * 10^{12} * log_2(1 + 31,6) = 5.03 * 10^{3}Gbps$

Pero dado que la transmision maxima de la fibra optica depende de la capacidad de los receptores opticos y de la modulacion, en este caso QPSK, la tasa real de transmision es diferente a la calculada por la formula de shannon.

$100Gbaudios * 2bit/simbolo = 200Gbps = 0,2Tbps$


*Ejercicio 3*

Si en el sistema anterior se introduce un conector de fibra con un 20% de pérdidas, 
responder a las siguientes cuestiones: 
a) ¿Se verá afectada la tasa de transmisión máxima? 
b) ¿Qué velocidad máxima se tendrá en la salida? 


*Ejercicio 4*

Indicar el tipo de modulación que se está utilizando y los problemas que plantea en los 
casos b y c. 

Dado que se ven 16 puntos en cada grafica se puede inferir que la modulación es la 16-QAM o 4 bits por simbolo. La grafica A es correcta sin ningun problema a diferencia de la B y la C.  
La grafica B se ve distorsionada debido posiblemente a interferencias o ruido.
La C se ve mas distorsionada y con mayor dispersión lo que indicaria una degradación de señal


*Ejercicio 5*

Sabiendo que se transmiten dos señales de forma simultánea y que se aplican dos 
modulaciones diferentes: 
a) Indicar qué dos modulaciones se están aplicando. 
b) Recuperar la información de ambas señales. 

a) Se pude ver una modulación de frecuencia o frequency shift keying y una de fase o fase shift keying.

b)


*Ejercicio 6*
