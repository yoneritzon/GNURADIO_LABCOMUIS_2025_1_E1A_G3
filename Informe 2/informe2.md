# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

- En caso de utilizar herramientas de Inteligencia Artificial para asistencia en la redacción, análisis o cualquier otra tarea, de debe especificar en la sección de **Declaración de Originalidad y Responsabilidad** aclarando el alcance y propósito de su uso.
- Cualquier omisión en la declaración del uso de IA o la presentación de contenido plagiado será penalizado con nota de 0.0 y reporte a la coordinación del programa.
- Si emplea referencias disponibles en línea, agregue los hipervínculos respectivos.  

Al final de la plantilla encontrará algunos ejemplos para enriquecer su informe, incluyendo cómo insertar imágenes, tablas y ecuaciones, así como generar hipervínculos a su repositorio o al propio informe. Ir a [ejemplos en Markdown](#ejemplos-usando-markdown)

---
# Práctica 2: Modelo de canal

### Integrantes
- **ANDRES QUINTERO** - 2204655
- **JHON CHAVEZ** - 2212234

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
28 de marzo de 2025

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
#### Actividad 1: Simulación de canal en GNU Radio
Para la siguiente simulación usamos una onda triangular con la idea de verificar el comportamiento de su espectro al aplicarle diferentes frecuencias de filtrado.
<p align="center">
  <img src="https://github.com/user-attachments/assets/29150dc4-71b0-478f-b0db-1cdf37272160" width="500"/>
  <img src="https://github.com/user-attachments/assets/5af0e2c5-b333-486b-b528-e12607a16c98" width="500"/>
</p>
Imagen 1: Filtrado de altas frecuencias (izquierda) vs bajas frecuencias (derecha)
</p>
Se puede comprobar efectivamente que al filtrar en bajas frecuencias solo se deja pasar al armonico fundamental y al eliminar los demás armonicos de la señal se pierde parte de la potencia de esta y en consecuencia información o calidad. En cambio en altas frecuencias se dejan pasar más armonicos, y por ende la potencia de esa señal se distribuye a lo largo de su espectro, y la información se conserva casi en su totalidad.
Si la señal recibe una desviación en la frecuencia antes de entrar al filtro, esto ocasiona que el filtro elimine parte de la señal que se sale del rango de filtrado. Además Cuando consideramos el ruido que afecta a la señal, podemos calcular la degradacion que sufre esta señal:
</p> 
<p align="center">
  SNR= PNref - 10log(P_Señal/P_ruido) = P_señal[dB] - P_ruido [dB] = -18 - (-65) = 42[dB]
</p> 
 Teniendo en cuenta lo anterior, se confirma que a mayor ruido, menor SNR y mayor degradación.


#### Actividad 2: Fenómenos de canal en el osciloscopio

<p align="center">
  <img src="https://github.com/user-attachments/assets/355d923b-1aee-4143-81db-d39eb9d43b43" width="510"/>
  <img src="https://github.com/user-attachments/assets/c80ac8b3-7872-491f-b831-56ff55e2b99e" width="490"/>
</p>   
Imagen 2: Señal senoidal con ruido
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
Imagen 6: Comparación de la potencia simulada y la recibida por el analizador de espectros.
</p>
Si comparamos la potencia de la simulación respecto a la mostrada en el analizador de espectros, se nota una diferencia de casi 14dB. Para calcular la maxima potencia que se podría entregar se procedio a aumentar los parametros necesarios:

<p align="center">
  <img src="https://github.com/user-attachments/assets/cf6f6874-bfe6-48b8-9b00-69b2dadc4ee4" width="500"/>
  <img src="https://github.com/user-attachments/assets/afa16fc8-2495-4233-8b67-4c552406521e" width="500"/>
</p>   
Imagen 7: Potencia maxima para una señal coseno flotante.
</p>

Se oberva que la señal final es parecida a la simulada, pero su potencia es mayor debido a la ganancia del modulador.
<p align="center">
  <img src="https://github.com/user-attachments/assets/78632ef2-d70f-4bf4-99fa-b04376058642" width="550"/>
  <img src="https://github.com/user-attachments/assets/a0ee2903-5251-4835-a829-d9a6b8247356" width="400"/>
</p>   
Imagen 8: Potencia maxima para una señal coseno compleja.
</p>

Se oberva que la señal final es parecida a la simulada, pero su potencia es mayor debido a la ganancia del modulador. Para calcular la ganancia entregada por el radio, calculamos la ganancia de la señal y luego hacemos una diferencia en potencias con la que nos muestra el analizador de espectros:

Potencia teorica de la señal antes de modularse:
<p align="center">
  P= 10Log(A^2/4) = -12.04 [dB]
</p> 
La potencia experimental obtenida de la grafica (Imagen 8) es aproximadamente de -16.00 [dBm].
</p>
<p align="center">
  P = -16 - (-12,04)  = 13.96 [dB] Mayor a la simulada </p>
  
<p align="center">
  P = 10^(13,96/10)   = 24,88 [W] Mayor a la simulada </p>
  
<p align="center">
  V = (5,49)^(0.5)    = 4,98 [v] Mayor a la simulada
</p> 
Se aclara que esta potencia se calculo tomando en cuenta 1 sola componente del espectro.
</p> 
Para calcular el ancho de banda
con el analizador fue necesario identificar que tipo de filtro era, en este caso un banda base, luego se procedio a calcularlo:
<p align="center">
  BWM= f2-f1 = 3,7 [kHz]
</p> 
Para normalizar el piso de ruido fue necesario sacar unos valores aproximados en los que oscilaba el ruido.
<p align="center">
  NF= PNref - 10log(RBW/1) = (-58-68)/2 - 10log(3,7k/1) = -98.68 [dBm]
</p> 

### Conclusiones
- La práctica evidenció la relevancia de ajustar adecuadamente los parámetros y montar correctamente los equipos para conseguir una señal de alta calidad y un análisis exacto en ambientes ruidosos. 
- Una potencia de señal adecuada mejora la SNR, lo que se ve como una mayor calidad, no obstante niveles exesivos podrian saturar o inducir interderencia.
- Aunque las fuentes complejas incorporan datos de magnitud y fase, las fuentes flotantes son modeladas como valores reales que se basan en un voltaje. Esto es crucial para el estudio fasorial y para la aplicación de las transformadas de Fourier.
### Referencias
Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)
- ChatGPT, modelo GPT-4 de OpenAI. (2025). Información generada mediante interacción en ChatGPT. Disponible en https://chat.openai.com
---

