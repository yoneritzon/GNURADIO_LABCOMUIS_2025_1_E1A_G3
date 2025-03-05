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
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

---
## Contenido

### Resumen
Se corroboro de manera 

**Palabras clave:** de 2 a 5 palabras clave. 

### Introducción


### Procedimiento

#### Actividad 2:
Las señales de tipo flotante y complejas se pueden diferenciar matematicamente de la siguiente manera:
<p align="center">
Vfloat = V+ - V-  
</p>
donde V- no necesariamente va conectado a tierra, esto nos puede ocacionar que quede flotando con respecto a los demas nodos del sistema, se modela con una ecuación diferencial simple de potenciales sin referencia absoluta, es decir, solo depende de la diferencia de voltaje entre sus terminales.
<p align="center">
Vcompl = Vm(cosθ+jsinθ)
</p>
se modela en el dominio de los números complejos, lo que implica relaciones fasoriales, cambios de fase y transformadas de Fourier.

Ademas se pueden diferenciar tanto en el tiempo como en el espectro de la señal, para este caso usamos una funcion senoidal.
<p align="center">
  <img src="https://github.com/user-attachments/assets/7c53be53-8075-48d1-94bd-b57b0d63b01c" width="500"/>
  <img src="https://github.com/user-attachments/assets/db6f20b5-56e1-4c66-bbdf-0440219724b3" width="500"/>
</p>
Imagen #: Onda senoidal compleja (izquierda) y onda senoidal flotante (derecha)
</p>

Al analizar las distintas formas de ondas, se pudo observar un cambio en la distribucion de la potencia en el dominio de la frecuencia, tal y como podemos observar en las siguientes graficas:
<p align="center">
  <img src="https://github.com/user-attachments/assets/c76cab1d-cb5d-4e62-b174-0649d066c5a0" width="500"/>
  <img src="https://github.com/user-attachments/assets/28614b75-55c9-41c4-b65d-cd5cfe143c95" width="500"/>
</p>
Imagen #: Onda cuadrada (izquierda), onda triangular (derecha)
    ![1_complex2](https://github.com/user-attachments/assets/1a12f8ea-6970-4b3b-8c67-c13a5a5ddc4f)

Si observamos la onda cuadrada, esta contiene armónicos impares (múltiplos de 𝑓0), ademas la energía se distribuye en varias frecuencias, disminuyendo con $1/𝑛$ como se puede ver en la grafica.
En cuanto a la onda triangular esta también tiene solo armónicos impares, pero con menor amplitud que la onda cuadrada.
La potencia decrece más rápido, aproximadamente con $1/𝑛^2$, lo que significa menor contenido de alta frecuencia.

Ahora bien, si cambiamos los parametros de la fuente podemos observar diferentes cambios tales como:
<p align="center">
  <img src="https://github.com/user-attachments/assets/bcada02f-efe9-46d2-934d-8f249962aa7c" width="500"/>
  <img src="https://github.com/user-attachments/assets/0ae69fee-56c4-4c83-a9eb-3040ca6ef45f" width="500"/>
  <img src="https://github.com/user-attachments/assets/1f7a986b-c8fc-4f06-bd32-b2ce42156cef" width="500"/>
  <img src="https://github.com/user-attachments/assets/1a12f8ea-6970-4b3b-8c67-c13a5a5ddc4f" width="500"/>
 </p>   
Imagen #: Modificacion de parametros de la fuente.
</p>
En la figura anterior 

</p>






### Conclusiones
Se sintetizan los principales aportes y puntos relevantes de la práctica, evitando repetir lo ya consignado en las otras secciones del informe. 

### Referencias
Ejemplo de referencia:

- [Proakis, 2014] J. Proakis, M. Salehi. Fundamentals of communication systems. 2 ed. England: Pearson Education Limited, 2014. p. 164-165, 346. Chapter 5 In: [Biblioteca UIS](https://uis.primo.exlibrisgroup.com/permalink/57UIDS_INST/63p0of/cdi_askewsholts_vlebooks_9781292015699)

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
