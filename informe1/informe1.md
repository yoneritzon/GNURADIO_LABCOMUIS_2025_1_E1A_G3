# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

- En caso de utilizar herramientas de Inteligencia Artificial para asistencia en la redacción, análisis o cualquier otra tarea, de debe especificar en la sección de **Declaración de Originalidad y Responsabilidad** aclarando el alcance y propósito de su uso.
- Cualquier omisión en la declaración del uso de IA o la presentación de contenido plagiado será penalizado con nota de 0.0 y reporte a la coordinación del programa.
- Si emplea referencias disponibles en línea, agregue los hipervínculos respectivos.  

Al final de la plantilla encontrará algunos ejemplos para enriquecer su informe, incluyendo cómo insertar imágenes, tablas y ecuaciones, así como generar hipervínculos a su repositorio o al propio informe. Ir a [ejemplos en Markdown](#ejemplos-usando-markdown)

---
# Práctica 1C: Mediciones de potencia y frecuencia

### Integrantes
- **ANDRES QUINTERO** - 2204655
- **JHON CHAVEZ** - 2212234

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
19 de febrero de 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia tales como chatGPT y han sido debidamente citadas. La herramienta anteriormente citada tambien ayudo con la redaccion de este informe.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

---
## Contenido

### Resumen
En este informe se expone de forma general el procedimiento experimental llevado a cabo, detallando los instrumentos empleados (USRP 2920, osciloscopio RTB2004 y analizador de espectros FPC1000), y detallando el método para cuantificar parámetros como potencia, frecuencia y ruido. Se tratará la configuración de los equipos, la comparación de diversas representaciones de señales y el contraste entre los resultados de simulación y las mediciones reales, ilustrando en síntesis el efecto de los ajustes en la calidad de la comunicación.

**Palabras clave:** 
- Potencia
- Frecuencia
- SNR

### Introducción
Este informe aborda de manera integral diversos aspectos clave en la evaluación de sistemas de comunicación. Se analiza cómo la potencia de la señal influye en la calidad de la transmisión, y se examina el impacto del piso de ruido en la detección de señales débiles. Además, se consideran las limitaciones de los equipos empleados, en términos de ancho de banda y precisión de las mediciones, y se discuten estrategias para mejorar la confiabilidad de las mediciones en entornos con altos niveles de ruido.

Asimismo, se exploran las aplicaciones prácticas de medir la potencia y el ancho de banda en sistemas de comunicaciones reales, junto con metodologías para determinar la respuesta en frecuencia de un canal alámbrico. Cada uno de estos temas se desarrolla en secciones específicas del informe, permitiendo un análisis detallado sin profundizar en esta introducción.

### Procedimiento
#### Actividad 1
#### USRP 2920
1. Rango de frecuencia (50 MHz a 2.2 GHz).
2. Rango de ganancia (0 dB a 31 dB en TX y 0 dB a 31.5 dB en RX).
3. Ancho de banda máximo en tiempo real (hasta 40 MHz).
4. Velocidad máxima de muestreo I/Q (25 MS/s en 16 bits y 50 MS/s en 8 bits).
5. Conectividad (Interfaz Gigabit Ethernet y requerimiento de alimentación de 6 V, 3 A).

#### Osciloscopio R&S RTB2004
1. Ancho de banda.
2. Resolución vertical (10‑bit ADC).
3. Tasa de muestreo.
4. Profundidad de memoria.
5. Pantalla táctil de alta resolución.

#### Analizador de espectro R&S®FPC1000
1. Rango de frecuencia (5 kHz a 1 GHz, ampliable hasta 2 o 3 GHz con opciones). 
2. Resolución de frecuencia (1 Hz). 
3. Resolución de banda (RBW) – Rango 1 Hz a 3 MHz en secuencia de 1/3, con precisión nominal (<5% para RBW ≤300 kHz y <10% para 300 kHz a 1 MHz). 
4. Nivel de entrada y piso de ruido – Rango de visualización desde el piso de ruido hasta +30 dBm.
5. Tiempo de barrido – Desde 10 ms hasta 1000 s, con incertidumbre nominal de 1% a 3%.

#### Medicion de piso de ruido normalizado
La medicion de ruido normalizado dio como resultado -98.682 [dB] esto teniendo en cuenta los datos arrojados por el analizador de espectros.
#### Actividad 2:
Las señales de tipo flotante y complejas se pueden diferenciar matematicamente de la siguiente manera:
<p align="center">
Vfloat(t) = Vm.sen(2πft+ϕ)   
</p>
donde:

A es la amplitud.

𝑓 es la frecuencia.

𝜙 es la fase.

La clave aquí es que esta ecuación solo involucra valores reales, sin ninguna componente imaginaria.
<p align="center">
Vcompl = Vm.(cos(2πft+ϕ)+jsin(2πft+ϕ))
</p>
se modela en el dominio de los números complejos, lo que implica relaciones fasoriales, cambios de fase y transformadas de Fourier.

Ademas se pueden diferenciar tanto en el tiempo como en el espectro de la señal, para este caso usamos una funcion senoidal.
<p align="center">
  <img src="https://github.com/user-attachments/assets/7c53be53-8075-48d1-94bd-b57b0d63b01c" width="500"/>
  <img src="https://github.com/user-attachments/assets/db6f20b5-56e1-4c66-bbdf-0440219724b3" width="500"/>
</p>
Imagen 1: Onda senoidal compleja (izquierda) y onda senoidal flotante (derecha)
</p>
Se puede comprobar que efectivamente la onda flotante al carecer de componente imaginaria, en el tiempo solo se ve una funcion seno, y en la frecuencia se ven los dos impulsos. Al contrario en la onda compleja se presentan dos funciones en el tiempo, un seno y coseno, donde su espectro solo muestra un unico impulso, esto debido a que se anulan algunos componentes.

</p>
Al analizar las distintas formas de ondas, se pudo observar un cambio en la distribucion de la potencia en el dominio de la frecuencia, tal y como podemos observar en las siguientes graficas:
<p align="center">
  <img src="https://github.com/user-attachments/assets/c76cab1d-cb5d-4e62-b174-0649d066c5a0" width="500"/>
  <img src="https://github.com/user-attachments/assets/28614b75-55c9-41c4-b65d-cd5cfe143c95" width="500"/>
</p>
Imagen 2: Onda cuadrada (izquierda), onda triangular (derecha)
</p>
Si observamos la onda cuadrada, esta contiene armónicos impares (múltiplos de 𝑓0), ademas la energía se distribuye en varias frecuencias, disminuyendo con 1/𝑛 como se puede ver en la grafica.
En cuanto a la onda triangular esta también tiene solo armónicos impares, pero con menor amplitud que la onda cuadrada. La potencia decrece más rápido, aproximadamente con 1/𝑛^2, lo que significa menor contenido de alta frecuencia.

Ahora bien, si cambiamos los parametros de la fuente podemos observar diferentes cambios tales como:
<p align="center">
  <img src="https://github.com/user-attachments/assets/0ae69fee-56c4-4c83-a9eb-3040ca6ef45f" width="500"/>
  <img src="https://github.com/user-attachments/assets/bcada02f-efe9-46d2-934d-8f249962aa7c" width="500"/>
  <img src="https://github.com/user-attachments/assets/1f7a986b-c8fc-4f06-bd32-b2ce42156cef" width="500"/>
  <img src="https://github.com/user-attachments/assets/1a12f8ea-6970-4b3b-8c67-c13a5a5ddc4f" width="500"/>
 </p>   
 
Imagen 3: Modificacion de parametros de la fuente.
</p>
Inicialmente la onda senoidal pura, al tener una componente real y una imaginaria, en el plano de la frecuencia se cancela unas componentes y por ende se observa un solo impulso. En la figura anterior se fue variando algunos parametros, cuando se cambio la fase de la onda, no hubo ningún cambio en la respuesta temporal ni en el espectro, es decir, no vario su potencia. Cuando se modifico el OFFSET hubo un cambio en la respuesta temporal, desplazandose verticalmente la componente real de la señal senoidal, pero el cambio mas importante se da en su espectro, donde aparecen dos impulsos, esto se debe a que al desplazarse la componente real de la señal, ya no se van a cancelar con las componentes imaginarias de la onda. Al modificar la frecuencia, se produjo cambios tanto en el tiempo como en su espectro, Los picos se desplazan a la nueva frecuencia ±f0′, la amplitud de los picos no cambia, porque la energía sigue concentrada en una sola frecuencia. Y para finalizar se cambio la amplitud provocando un aumento en la potencia de la señal tanto en el tiempo como en la frecuencia.

Las señales cuadradas y senoidales denotan su mayor diferencia en su espectro, esto debido a que por una parte la señal seno distribuye casi toda su energia en 2 picos, la señal cuadrada genera muchos armonicos que van disminuyendo su potencia conforme se alejan de la fundamental.

</p>

#### Actividad 3:
Inicialmente se configuró el software GNA RADIO para que el USRP 2920 pudiera transmitir las señales deseadas, para eso se modificaron ciertos bloques del flujograma:

<p align="center">
  <img src="https://github.com/user-attachments/assets/bdd76b5b-ad86-4580-ba3d-909d178d228c" width="520"/>
  <img src="https://github.com/user-attachments/assets/cc7aa257-9ebe-46ef-bfda-121938ac09ee" width="350"/>

</p>   
Imagen 4: Modificacion de parametros de la USRP 2090
</p>
En la figura anterior notese que el parametro de la ganancia del modulador es de 30 dB, por ende la señal que se simula no es la misma que llega al analizador de espectros por que este le va a inyectar una ganancia a la señal, como se obserba en la siguiente imagen:
<p align="center">
  <img src="https://github.com/user-attachments/assets/5121fcc8-c1b9-4c8d-b909-ea773700eb9f" width="550"/>
  <img src="https://github.com/user-attachments/assets/15ce160d-379b-41e9-bf1a-7dd068ec139b" width="400"/>
</p>   
Imagen 5: Modificacion de parametros de la USRP 2090
<p align="center">
  <img src="https://github.com/user-attachments/assets/5121fcc8-c1b9-4c8d-b909-ea773700eb9f" width="550"/>
  <img src="https://github.com/user-attachments/assets/15ce160d-379b-41e9-bf1a-7dd068ec139b" width="400"/>
</p>   
Imagen #: Comparación de la potencia simulada y la recibida por el analizador de espectros.
</p>
Si comparamos la potencia de la simulación respecto a la mostrada en el analizador de espectros, se nota una diferencia de casi 14dB. Para calcular la maxima potencia que se podría entregar se procedio a aumentar los parametros necesarios:

<p align="center">
  <img src="https://github.com/user-attachments/assets/cf6f6874-bfe6-48b8-9b00-69b2dadc4ee4" width="500"/>
  <img src="https://github.com/user-attachments/assets/afa16fc8-2495-4233-8b67-4c552406521e" width="500"/>
</p>   
Imagen #: Potencia maxima para una señal coseno flotante.
</p>

Se oberva que la señal final es parecida a la simulada, pero su potencia es mayor debido a la ganancia del modulador.
<p align="center">
  <img src="https://github.com/user-attachments/assets/78632ef2-d70f-4bf4-99fa-b04376058642" width="550"/>
  <img src="https://github.com/user-attachments/assets/a0ee2903-5251-4835-a829-d9a6b8247356" width="400"/>
</p>   
Imagen #: Potencia maxima para una señal coseno compleja.
</p>
Se oberva que la señal final es parecida a la simulada, pero su potencia es mayor debido a la ganancia del modulador. Para calcular el ancho de banda
con el analizador de espectros es necesario 
### Conclusiones
- La práctica evidenció la relevancia de ajustar adecuadamente los parámetros y montar correctamente los equipos para conseguir una señal de alta calidad y un análisis exacto en ambientes ruidosos. 
- Una potencia de señal adecuada mejora la SNR, lo que se ve como una mayor calidad, no obstante niveles exesivos podrian saturar o inducir interderencia.
- Aunque las fuentes complejas incorporan datos de magnitud y fase, las fuentes flotantes son modeladas como valores reales que se basan en un voltaje. Esto es crucial para el estudio fasorial y para la aplicación de las transformadas de Fourier.
### Referencias
Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)
- ChatGPT, modelo GPT-4 de OpenAI. (2025). Información generada mediante interacción en ChatGPT. Disponible en https://chat.openai.com
---
# Ejemplos usando Markdown

Volver al [INICIO](#laboratorio-de-comunicaciones)

## Inclusión de Imágenes
### Imagen de referencia dentro del repositorio:
![Networking](my%20file/test.png)

### Imagen de fuente externa
![GNU Radio logo](https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png)

### Uso de html para cambiar escala de la imagen
<img src="https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png" alt="GNU Radio Logo" width="300">

## Creación de hipevínculos 
- [Aprende Markdown](https://markdown.es/)
- [Más acerca de Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Abrir documento en el repositorio](my%20file/test_file.txt). Si hay espacios en la ruta de su archivo, reemplácelos por `%20`.
- Ir a una sección de este documento. Por ejemplo: [Ir a Contenido](#contenido) Tenga en cuenta escribir el título de la sección en minúsculas y los espacios reemplazarlos por guiones.
## Uso de Expresiones Matemáticas
Se pueden incluir ecuaciones en el archivo `README.md` utilizando sintaxis similar a [LaTeX](https://manualdelatex.com/tutoriales/ecuaciones):

### Ecuaciones en Línea
```
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.
```
**Salida renderizada:**
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.

### Ecuaciones en Bloque
```
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$
```
**Salida renderizada**
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$

## Creación de Tablas

**Tabla 1.** Ejemplo de tabla en Markdown.

| Parámetro | Valor |
|-----------|-------|
| Frecuencia (Hz) | 1000 |
| Amplitud (V) | 5 |
| Ciclo útil (%) | 50 |

## Inclusión de código

```python
def hello_world():
    print("Hello, World!")
```

También es posible resaltar texto tipo código como `print("Hello, World!")`.

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
