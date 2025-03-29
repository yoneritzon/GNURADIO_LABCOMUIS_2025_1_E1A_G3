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
Este laboratorio evaluó el impacto del canal en la calidad de la señal mediante simulaciones en GNU Radio y mediciones reales con USRP, osciloscopio y analizador de espectros. Se estudiaron efectos del ruido, filtrado y atenuación para optimizar la relación señal-ruido en la transmisión de datos.

**Palabras clave:** 
- Canal de transmisión
- Ruido
- Filtrado
- Atenuación

### Introducción
Este informe analiza el comportamiento de las señales al atravesar distintos canales de transmisión. A través de simulaciones en GNU Radio y mediciones experimentales con equipos como el USRP, osciloscopio y analizador de espectros, se investigaron los efectos del ruido, filtrado y atenuación para optimizar la recuperación de la información.


Asimismo, se exploran las aplicaciones prácticas de medir la potencia y el ancho de banda en sistemas de comunicaciones reales, junto con metodologías para determinar la respuesta en frecuencia de un canal alámbrico. Cada uno de estos temas se desarrolla en secciones específicas del informe, permitiendo un análisis detallado sin profundizar en esta introducción.

### Procedimiento
#### Actividad 1: Simulación de canal en GNU Radio
Para la siguiente simulación usamos una onda triangular para verificar el comportamiento de su espectro al aplicarle diferentes frecuencias de filtrado.
<p align="center">
  <img src="https://github.com/user-attachments/assets/29150dc4-71b0-478f-b0db-1cdf37272160" width="500"/>
  <img src="https://github.com/user-attachments/assets/5af0e2c5-b333-486b-b528-e12607a16c98" width="500"/>
</p>
Imagen 1: Filtrado de altas frecuencias (izquierda) vs bajas frecuencias (derecha)
</p>
Se puede comprobar efectivamente que al filtrar en bajas frecuencias solo se deja pasar al armonico fundamental y al eliminar los demás armonicos de la señal se pierde parte de la potencia de esta y en consecuencia información o calidad. En cambio en altas frecuencias se dejan pasar más armonicos, y por ende la potencia de esa señal se distribuye a lo largo de su espectro, y la información se conserva casi en su totalidad. Este efecto es visible para cualquier tipo de señal, cuadratica, senoial, entre otras.


Si la señal recibe una desviación en la frecuencia antes de entrar al filtro, esto ocasiona que el filtro elimine parte de la señal que se sale del rango de filtrado. Además Cuando consideramos el ruido que afecta a la señal, podemos calcular la degradacion que sufre esta señal:
</p> 
<p align="center">
  SNR= PNref - 10log(P_Señal/P_ruido) = P_señal[dB] - P_ruido [dB] = -18 - (-65) = 42[dB]
</p> 
 Teniendo en cuenta lo anterior, se confirma que a mayor ruido, menor SNR y mayor degradación.


#### Actividad 2: Fenómenos de canal en el osciloscopio
<p align="center">
  <img src="https://github.com/user-attachments/assets/b3c6d46d-d45b-4c46-92c3-5fcb63527779" width="510"/>
  <img src="https://github.com/user-attachments/assets/287f10d4-e6cb-48a0-967c-6720d10590d7" width="490"/>
</p>   
Imagen 2: Señal senoidal sin ruido
</p>
Al no existir ruido, la envolvente de la señal no tiene ninguna perturbación.
</p> 

<p align="center">
  <img src="https://github.com/user-attachments/assets/355d923b-1aee-4143-81db-d39eb9d43b43" width="510"/>
  <img src="https://github.com/user-attachments/assets/c80ac8b3-7872-491f-b831-56ff55e2b99e" width="490"/>
</p>   
Imagen 3: Señal senoidal con ruido
</p>
En la figura anterior notese que al aparecer ruido en la señal su envolvelte presenta perturbaciones.
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/3325318a-e70d-468f-9f0d-389143b79fe1" width="330"/>
  <img src="https://github.com/user-attachments/assets/64566a0c-eda2-462b-bcad-624266cde068" width="330"/>
  <img src="https://github.com/user-attachments/assets/aaaf4140-04d9-4231-ab15-0053f1c6de7d" width="330"/>
</p>   
Imagen 4: Comportamiento de la envolvente de una señal senoidal (50Mhz, 400Mhz y 500Mhz)

Al variar la frecuencia de la portadora, la envolvente tiende a aumentar o disminuir la potencia de la señal.

#### Actividad 3: Fenómenos de canal en el analizador de espectro


</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/4dbdb796-3c50-4bac-91a5-39d3db55e2c2" width="500"/>
  <img src="https://github.com/user-attachments/assets/903d9109-1174-43f8-aa1c-d6e4cb762209" width="500"/>
  <img src="https://github.com/user-attachments/assets/fb8644df-4c13-4dc2-a66a-51120cdd3eef" width="1000"/>

</p>     
Imagen 5: Espectro de una señal cuadrada al aplicarle ruido
</p>  
Se evidencia el ruido de la señal que recibe el espectometro, y un leve desplazamiento del piso de este.

</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/c9dcb4a4-54fb-456f-9f14-d008e29318aa" width="500"/>
  <img src="https://github.com/user-attachments/assets/22163fff-878c-4836-8305-52a93bbc7720" width="500"/>
</p>   
Imagen 6: Afectación producida por un cable coaxial de 1 y 10 metros respectivamente
</p>  
Analizando su espectro se observa que este se desplaza verticalmente, es decir, disminuye su potencia, esto nos da a entender que entre mayor sea la longitud del cable,
mayor será la perdida de potencia de la señal. Algo similar ocurrió cuando se usaron las antenas, aunque su efecto no se evidenció tanto debido a que no se podía alejar tanto los instrumentos.

#### Actividad 4: Efectos de los fenómenos de canal en la conversión de frecuencia



### Conclusiones
- La práctica evidenció la relevancia de ajustar adecuadamente los parámetros y montar correctamente los equipos para conseguir una señal de alta calidad y un análisis exacto en ambientes ruidosos. 
- Una potencia de señal adecuada mejora la SNR, lo que se ve como una mayor calidad, no obstante niveles exesivos podrian saturar o inducir interderencia.
- Aunque las fuentes complejas incorporan datos de magnitud y fase, las fuentes flotantes son modeladas como valores reales que se basan en un voltaje. Esto es crucial para el estudio fasorial y para la aplicación de las transformadas de Fourier.
### Referencias
Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)
- ChatGPT, modelo GPT-4 de OpenAI. (2025). Información generada mediante interacción en ChatGPT. Disponible en https://chat.openai.com
---

