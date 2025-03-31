# Cuaderno_De_Ejercicios1
## *Ejercicio 1*

- Para un sistema de comunicaciones con 17 niveles de señal, que funciona en banda base, calcular el máximo ancho de banda si el ruido es despreciable y la tasa de transmisión es de 10 Mbits/s. ¿Qué tipo de medio guiado se podría utilizar para el sistema?

La capacidad se calcula con la formula de Nyquist: $T = 2H * log_2(V)$  
T = Capacidad maxima  
H = Ancho de banda
V = niveles de señal  

$$H = \frac{T}{2 * log_2(v)} = \frac{1 * 10^{7}}{2 * log_2(17)} = 1.23MHz$$

Dado que el ancho de banda calculado es dde 1.23MHz se podrían utilizar como medio de transmisión guiado el par trenzado, de ancho de banda de *16MHz*(Categoría 2) a *600MHz*(Categoria 7), el coaxial, con ancho de banda de aproximadamente un GHz, o fibra optica. Aunque el par trenzado seria mas que suficiente y el mas económico.

---
## *Ejericio 2*

- ¿Cuál es la tasa de transmisión máxima en un canal óptico con fibra de ancho de banda de 1 THz y conversores optoeléctricos de 100 Gbaudios, si la relación SNR es de 15 dB y la modulación utilizada en los conversores es de 4 símbolos en cuadratura?

La capacidad del canal se calcula con la ecuación de Shannon:  
$$C = B * log_2(1 + SNR)$$

$$C = 1 * 10^{12} * log_2(1 + 31,6) = 5.03 * 10^{3}Gbps$$

Pero dado que la transmision maxima de la fibra optica depende de la capacidad de los receptores opticos y de la modulacion, en este caso QPSK, la tasa real de transmision es diferente a la calculada por la formula de shannon.

$$100Gbaudios * 2bit/simbolo = 200Gbps = 0,2Tbps$$

---
## *Ejercicio 3*

Si en el sistema anterior se introduce un conector de fibra con un 20% de pérdidas, 
responder a las siguientes cuestiones: 
a) ¿Se verá afectada la tasa de transmisión máxima? 
b) ¿Qué velocidad máxima se tendrá en la salida? 

---
## *Ejercicio 4*

Indicar el tipo de modulación que se está utilizando y los problemas que plantea en los 
casos b y c. 

Dado que se ven 16 puntos en cada grafica se puede inferir que la modulación es la 16-QAM o 4 bits por simbolo.  
**En el caso A:** Se observan los 16 puntos bien definidos y cuadrados.  
**En el caso B:** Se observan que los puntos aunque cuadrados estan difusos y no en su posicion ideal lo que indicaría la presencia de ruido que puede provocar errores de decodificación.  
**En el caso C:** Los puntos estan no solo difusos sino tambien girados y fuera de su cuadricula lo que sugiere errores de desajuste de fase.  


![image](https://github.com/user-attachments/assets/72d4fbd9-5064-4aee-a365-8c7713d7b4f8)

---
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

---
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

---
## Ejercicio 7

Se considera una pila de protocolos de 4 capas. La capa 4 envía un bloque de 1 Kbyte. La capa 3 añade cabeceras de 256 bits y cada paquete es de 512 bytes. La capa 2 añade cabeceras de 512 bits y el campo de datos de las tramas son de 128 bytes. La capa 1 añade a cada 30 bytes de datos, 32 bits de comienzo, un byte de parada, y 16 bits de CRC. Dibujar todo el proceso de encapsulamiento del sistema transmisor y calcular la eficiencia del sistema.

### Capa 4:
- Un bloque de un 1 KByte = 1024 bytes.
### Capa 3:
- Se añaden cabeceras 256 bits = 32 bytes.
- Cada paquete = 512 bytes.
- $\frac{1024}{512} = 2$ Pero dado que la cabecera son 32 bytes se dividiría en tres paquetes para que se ajuste al tamaño del metodo de tranmision.
### Capa 2:
- Cabecera de 512 bits = 64 bytes.
- Tramas de 128 bytes.
- $\frac{512}{128} = 4*2 = 8$ tramas por paquete dado que la cabecera ocupa 64 bytes de cada trama.
### Capa 1: 
- 30 bytes de datos.
- 32 bits de comienzo = 4 bytes de comienzo.
- Un byte de parada.
- 16 bits de CRC = 2 bytes de CRC
- $128 + 30 + 4 + 1 + 2 = 165 bytes$

## **Cálculo de la eficiencia**
La eficiencia del sistema se define como:

$\text{Eficiencia} = \frac{\text{Datos Útiles}}{\text{Datos Totales}} \times 100%$

- **Datos útiles**: **1024 bytes**.
- **Datos totales transmitidos**: **3960 bytes**.


$\text{Eficiencia} = \frac{1024}{3960} \times 100= 25.85\%$  
La **eficiencia del sistema es del 25.85%**, lo que indica que el **74.15%** de los datos transmitidos corresponden a sobrecarga de cabeceras y control.

## Proceso de Encapsulamiento y Eficiencia del Sistema





### Detalles:
- **Capa 4:** Bloque de 1024 bytes.
- **Capa 3:** Añade cabeceras de 32 bytes. Divide en 3 paquetes de 512 bytes.
- **Capa 2:** Añade cabeceras de 64 bytes. Cada paquete se divide en 8 tramas de 128 bytes.
- **Capa 1:** Añade 4 bytes de inicio, 1 byte de parada y 2 bytes de CRC por cada 30 bytes de datos.

### Cálculo de Eficiencia


$$\text{Eficiencia} = \frac{1024}{3960} \times 100 = 25.85\%$$

Solo el 25.85% de los datos transmitidos son útiles; el resto corresponde a sobrecarga de cabeceras y control.

---

## Ejercicio 8

Un sistema satélite divide la información de la capa 3 en bloques de 1904 bits, a los que añade una cabecera de 64 bits. Si cada trama tarda en transmitirse 20 ms y la latencia del satélite es de 85 ms, ¿cuánto tiempo tardará en realizar la transmisión de 5 Mbytes de información? 

- Bloque de datos: 1904 bits
- Cabecera añadida: 64 bits
- Cada trama (paquete completo): 1904 + 64 = 1968 bits
- Tiempo de transmisión de una trama: 20 ms
- Latencia del satélite: 85 ms
- Información total a enviar: 5 MBytes

**Resolucion**:  

- Datos a enviar: $$5 MB = 5 * 10^{6}bytes * 8 = 4 * 10^{7}$$  
- Numero de tramas = $\frac{4 \times 10^{7}}{1904} = 3,66 \times 10^{4}$
- Tiempo de transmision = $3,66 \times 10^{4} \times 20 = 7,31 \times 10^{5}$
- Si se aplica latencia al principio = $7.31 \times 10^{5} + 0.085 = 7.31 \times 10^{5}$

---

## Ejercicio 9

Calcular el resultado de un paquete de datos “1111011101010101” en un sistema de enlace de datos con las siguientes especificaciones: 
- Secuencia de inicio de trama “010101010”. 
- Protección frente a errores H(7,4). 
- Tamaño máximo por trama de 4 bytes.


El código Hamming(7,4) toma 4 bits de datos y genera 7 bits codificados (añade 3 bits de paridad).  
1111 0111 0101 0101  

Vamos a codificar cada bloque por separado. El código Hamming(7,4) organiza los bits así:

Posiciones: [p1, p2, d1, p3, d2, d3, d4]
Donde:
- p1 = paridad de bits 1,3,5,7
- p2 = paridad de bits 2,3,6,7
- p3 = paridad de bits 4,5,6,7


*Bloque 1*: 1111
d1 = 1, d2 = 1, d3 = 1, d4 = 1

Posiciones: [p1, p2, 1, p3, 1, 1, 1]

Ahora calculamos:  
p1 = paridad de (3,5,7) = paridad de (1,1,1) = 1  
p2 = paridad de (3,6,7) = paridad de (1,1,1) = 1  
p3 = paridad de (5,6,7) = paridad de (1,1,1) = 1  
→ Resultado: 1111111


*Bloque 2*: 0111
d1 = 0, d2 = 1, d3 = 1, d4 = 1  
[p1, p2, 0, p3, 1, 1, 1]  
Cálculos:  
p1 = paridad(0,1,1) = 0  
p2 = paridad(0,1,1) = 0  
p3 = paridad(1,1,1) = 1  
→ Resultado: 0001111 


*Bloque 3*: 0101  
d1 = 0, d2 = 1, d3 = 0, d4 = 1  
[p1, p2, 0, p3, 1, 0, 1]  
Cálculos:  
-- p1 = paridad(0,1,1) = 0  
-- p2 = paridad(0,0,1) = 1  
-- p3 = paridad(1,0,1) = 0  
→ Resultado: 0101011  


*Bloque 4*: 0101 → Igual que anterior  
Resultado: 0101011  


Inicio de trama: 010101010
Datos codificados: 1111111000111101010110101011
Bloque 1: 1111111  
Bloque 2: 0001111  
Bloque 3: 0101011  
Bloque 4: 0101011  


Trama final:  
0101010101111111000111101010110101011  


---
## Ejercicio 10

Un fabricante indica que su sistema integra un CRC-8 con el siguiente polinomio generador: 𝐺𝐺(𝑥𝑥) = 𝑥𝑥8 + 𝑥𝑥7 + 𝑥𝑥2 + 1. Plantear los pasos que se deben realizar para calcular la trama resultante, considerando que el CRC se aplica al final de la trama 2 del ejercicio anterior. 

se toma como base una trama binaria de 37 bits (denominada **Trama 2**) y se le aplicará un **CRC-8** utilizando el siguiente polinomio generador:

- **Polinomio generador:** \(G(x) = x^8 + x^7 + x^2 + 1\)
- **Forma binaria del polinomio:** `110000101` (9 bits, desde \(x^8\) hasta \(x^0\))


**Trama inicial**

La trama sobre la que se aplicará el CRC es:  
0101010101111111011001101001010100101 ← 37 bits  

Para aplicar el algoritmo CRC-8, se agregan **8 ceros al final** (relleno), quedando:
010101010111111101100110100101010010100000000 ← 45 bits  

- Realizar una **división binaria (XOR)** entre el bloque de 45 bits y el polinomio generador.
- Esta operación se ejecuta bit a bit (sin acarreo), desplazando el divisor cada vez que se encuentra un `1` significativo.
- El **residuo** de la división es un número binario de **8 bits**, conocido como el **CRC**.

El residuo obtenido tras la operación de división con el generador `110000101` es:  
01100000  

Uniendo la trama original de 37 bits con el CRC calculado se obtiene la **trama final de 45 bits**:
010101010111111101100110100101010010101100000


## Ejercicio 11

 ¿Cuántos errores pueden llegar a corregir la codificación H(15,11) y el CRC-32? 

 - *Hamming*:  
El codigo de hamming es capaz de detectar errores a *d + 1* y corregir errores a *2d + 1* dado que el hamming proporcionado H(15,11) que nos da una distancia o *d* de 3 por lo que se pueden detectar dos errores y corregir uno.
- *CRC-32*:  
El CRC por si mismo no puede corregir errores dado que unicamente los detecta, con mucha exactitud y robustez pero solo detecta, por lo que la respuesta es que con CRC-32 se pueden corregir cero errores.

---
## Ejercicio 12

Se recibe la trama “1111111101011010101011” y se conoce que el protocolo está constituido por una cabecera “11111111” y que los datos están codificados con H(14,10), ¿cuáles son los datos útiles que se han transmitido?

De la trama recibida 1111111101011010101011 se saca la cabecera de los primeros 8 bits se queda la siguiente trama: 01011010101011 la que son 14 bits divididos en 10 bits de informacion y 4 de paridad segun indica el hamming H(14,10).  

La posición de los bits de datos en un código Hamming depende del diseño.  
En H(14,10), típicamente, los bits de datos están en posiciones no potencias de 2 (igual que en H(7,4), H(15,11), etc.).  
Posiciones (1-indexadas):  
- Bits de paridad → posiciones: 1, 2, 4, 8 (potencias de 2)
- Bits de datos → posiciones: 3, 5, 6, 7, 9, 10, 11, 12, 13, 14

Si se siguiese ese criterio los datos utilies transmitidos = 0101101011. 

## Ejercicio 13

¿A qué protocolo de la capa de enlace de datos corresponde el siguiente esquema temporal?

![image](https://github.com/user-attachments/assets/01c38b1f-c8dd-4d60-a812-66519b01ce48)

EL protocolo de la imagen correspondría al protocolo de **ventana corrediza** concretamente el protocolo Stop-and-wait ARQ. Se confirma que es este protocolo por dos razones:  
1. Las ventanas:
    - Ventana emisora (de A o B):
      - Contiene los números de secuencia de las tramas que pueden enviarse, pero aún no han sido confirmadas por el receptor.
      - En la imagen, A envía Frame 0 y espera la confirmación ACK 0, y luego envía Frame 1, esperando ACK 1. La ventana se mueve cuando recibe el ACK correspondiente.
    - Ventana receptora (de B o A):
      - Contiene los números de secuencia de tramas que está dispuesto a aceptar.
      - En este ejemplo, la ventana receptora tiene tamaño 1, por lo que solo acepta tramas ordenadas (por ejemplo, si espera Frame 1, descartará Frame 0 si llega de nuevo).
2. Piggybacking:
    - En vez de enviar el ACK por separada se sube a *caballito* o *piggybacking* en la sguiente trama a enviar.


## Ejercicio 14

¿Se puede aplicar el protocolo del ejercicio anterior en el siguiente escenario?

- No no se puede dado que en este diagrama el ACK se envia por separado y no por piggybacking por lo que no podria ser el protocolo de ventana corrediza

![image](https://github.com/user-attachments/assets/3bfefc08-20cd-405b-b652-ae5b476eefa0)


## Ejercicio 15

Dibujar un diagrama de ventana deslizante con un receptor con buffer para tres tramas y un transmisor que dispone de 5 tramas desordenadas que llegan en el orden 0, 3, 2, 4, 1.

| Tiempo | Estación A                   |                      | Estación B                   |
|--------|------------------------------|----------------------|------------------------------|
| T1     | `S = 0`                      | → Frame 0, ACK 0 →   | `R = 0`                      |
| T2     |                              | ← Frame 0, ACK 1 ←   | `S = 0`, envía ACK, espera 1 |
| T3     | `S = 1`                      | → Frame 1, ACK 1 →   | `R = 1`                      |
| T4     |                              | ← Frame 1, ACK 0 ←   | `S = 1`, envía ACK, espera 0 |
| ...    | Continúa el proceso...       |                      |                              |

---

## Ejericio 16

 Un canal coaxial con FDM con una tasa de transmisión de 500 Mbits/s con una longitud media de trama de 1/𝜇𝜇 = 12584 bits y una tasa de llegada de trama 𝜆𝜆 = 20000 trama/s:  
a) ¿Qué retardo tendrá?  
b) Si lo comparten entre 256 usuarios ¿cuántas portadoras serán necesarias?  
c) ¿Cuánto tiempo tardará un nodo en detectar una colisión?  

1. a) **¿Qué retardo tendrá?**

Paso 1: Calcular μ (tasa de servicio)

$$\mu = \frac{\text{Tasa de transmisión}}{\text{Tamaño medio de trama}} = \frac{500 \times 10^6}{12584} \approx 39727.13\ \text{tramas/s}$$
Paso 2: Calcular el retardo

$$\text{Retardo} = \frac{1}{\mu - \lambda} = \frac{1}{39727.13 - 20000} \approx \frac{1}{19727.13} \approx 5.07 \times 10^{-5}\ \text{segundos}$$

El retardo medio es de aproximadamente **50.7 microsegundos (μs)**.

2. b) **Si lo comparten entre 256 usuarios ¿cuántas portadoras serán necesarias?**
    En FDM (Multiplexación por División de Frecuencia), cada usuario necesita su propia portadora es decir se necesitan 256 portadoras.

3. c) **¿Cuánto tiempo tardará un nodo en detectar una colisión?**


$$t_{\text{prop}} = \frac{2500}{2 \times 10^8} = 12.5\ \mu s$$  

$$t_{\text{detección}} = 2 \times t_{\text{prop}} = 25\ \mu s$$  


---

## Ejercicio 17

Representar la trama “1111111101011010101011” con codificación Manchester y Manchester diferencial. Indicar las unidades y magnitudes en los ejes. 

**Codificación Manchester**  

Cada bit se representa con una transición en la mitad del bit.  
Reglas:  
- 1 → Transición baja a alta  
- 0 → Transición alta a baja
  
La frecuencia de la señal es el doble que la frecuencia de datos.  

**Codificación Manchester Diferencial**  

El bit se representa según la transición al inicio del bit:  
- 1 → Hay transición al inicio  
- 0 → No hay transición al inicio
  
Siempre hay una transición en el medio del bit.  
Se necesita un nivel inicial (se asumió nivel alto).  

- **Eje X**: Tiempo (en unidades de bit)
- **Eje Y**: Nivel de voltaje (por ejemplo, +V / 0V)
- El gráfico debe mostrar los cambios de nivel según las reglas de cada codificación.

![image](https://github.com/user-attachments/assets/1b30f39a-b27c-4478-bcf8-1b813130eaad)

    Es posible que la imagen sea erronea.

## Ejercicio 18

Diseñar una red Bluetooth que pueda mantener 15 nodos esclavos activos de manera simultánea. 
