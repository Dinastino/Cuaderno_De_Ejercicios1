# Cuaderno_De_Ejercicios1
## *Ejercicio 1*

- Para un sistema de comunicaciones con 17 niveles de señal, que funciona en banda base, calcular el máximo ancho de banda si el ruido es despreciable y la tasa de transmisión es de 10 Mbits/s. ¿Qué tipo de medio guiado se podría utilizar para el sistema?

La capacidad se calcula con la formula de Nyquist: $T = 2H * log_2(V)$  
T = Capacidad maxima  
H = Ancho de banda
V = niveles de señal  

$$H = \frac{T}{2 * log_2(v)} = \frac{1 * 10^{7}}{2 * log_2(17)} = 1.23MHz$$

Dado que el ancho de banda calculado es dde 1.23MHz se podrían utilizar como medio de transmisión guiado el par trenzado, de ancho de banda de *16MHz*(Categoría 2) a *600MHz*(Categoria 7), el coaxial, con ancho de banda de aproximadamente un GHz, o fibra optica. Aunque el par trenzado seria mas que suficiente y el mas económico.


## *Ejericio 2*

- ¿Cuál es la tasa de transmisión máxima en un canal óptico con fibra de ancho de banda de 1 THz y conversores optoeléctricos de 100 Gbaudios, si la relación SNR es de 15 dB y la modulación utilizada en los conversores es de 4 símbolos en cuadratura?

La capacidad del canal se calcula con la ecuación de Shannon:  
$$C = B * log_2(1 + SNR)$$

$$C = 1 * 10^{12} * log_2(1 + 31,6) = 5.03 * 10^{3}Gbps$$

Pero dado que la transmision maxima de la fibra optica depende de la capacidad de los receptores opticos y de la modulacion, en este caso QPSK, la tasa real de transmision es diferente a la calculada por la formula de shannon.

$$100Gbaudios * 2bit/simbolo = 200Gbps = 0,2Tbps$$


## *Ejercicio 3*

Si en el sistema anterior se introduce un conector de fibra con un 20% de pérdidas, 
responder a las siguientes cuestiones: 
a) ¿Se verá afectada la tasa de transmisión máxima? 
b) ¿Qué velocidad máxima se tendrá en la salida? 


## *Ejercicio 4*

Indicar el tipo de modulación que se está utilizando y los problemas que plantea en los 
casos b y c. 

Dado que se ven 16 puntos en cada grafica se puede inferir que la modulación es la 16-QAM o 4 bits por simbolo.
**En el caso A:** Se observan los 16 puntos bien definidos y cuadrados.  
**En el caso B:** Se observan que los puntos aunque cuadrados estan difusos y no en su posicion ideal lo que indicaría la presencia de ruido que puede provocar errores de decodificación.  
**En el caso C:** Los puntos estan no solo difusos sino tambien girados y fuera de su cuadricula lo que sugiere errores de desajuste de fase.  


![image](https://github.com/user-attachments/assets/72d4fbd9-5064-4aee-a365-8c7713d7b4f8)


## *Ejercicio 5*

Sabiendo que se transmiten dos señales de forma simultánea y que se aplican dos 
modulaciones diferentes: 
a) Indicar qué dos modulaciones se están aplicando. 
b) Recuperar la información de ambas señales. 

a) Se pude ver una modulación de frecuencia o frequency shift keying y una de fase o fase shift keying.

b) Para ver los datos que se han enviado seria cuando cambie la frecuencia es es 1 y el resto es cero.  
En resumen para freciencia sería: 0 1 1 0 0 1 0 1 1 0 1 0 1 0 0 1 1 0.

Para el cambio de fase es cuando se ve que la fase se cambie como si hubiese un espejo significa 1 y cuando vuelva a cambiar es cero.
En el caso de fase sería: 0 0 1 1 0 0 0 0 1 1 1 1 1 1 0 0 1 1.


![image](https://github.com/user-attachments/assets/dd4cac7d-0117-41c4-ad3a-f9f10cf2fbaa)


## *Ejercicio 6*

Indicar las longitudes de onda que se transmiten en cada uno de los puntos marcados 
en el esquema.  

![image](https://github.com/user-attachments/assets/bcce4f8f-6d4a-4095-95c2-033ff6200bed)


El esquema muestra un sistema de transmisión óptica con multiplexación por división de longitud de onda (WDM). El proceso se dividiria en tres fases: antes del combiner, entre el combiner y el splitter y despues del splitter. 

**Antes de combiner**:
- Cada fibra individual tranporta su propia longitud de onda. La fibra 1 = λ₁, fibra 2 = λ₂, etc.  
**Entre el combiner y el splitter**:
- La fibra de transmisión compartida transporta todas las longitudes de onda juntas: $λ_1 + λ_2 + λ_3 + λ_4$.  
**Despues del splitter**:
- Si es un splitter pasivo:  
  - El splitter divide las señales de regreso en diferentes fibras, por lo que cada salida del splitter debería recibir todas las longitudes de onda combinadas.
  - Si es demultiplexor cada salida debería llevar solo una λ en lugar de todas juntas.

