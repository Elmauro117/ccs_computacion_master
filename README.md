# VisionArtificial

## Acerca del Proyecto

El presente proyecto es del curso de Vision Artificial en grupo donde los integrantes somos:

* Ing. Alpaca Rendon, Jesus A.
* Ing. Ccallo Fernandez, Adolfo
* Ing. del Carpio Maraza, Heberth E.
* Ing. Vargas Franco, Mauricio S.

El proyecto consta de la resolucion de las tareas en el siguiente orden:

1. Cambiar el Brillo/Contraste de una imagen
2. Ecualizar una imagen
3. Sumar/Restar imagenes
4. Convolucion
5. Template Matching
6. Integrales Proyectivas

## Descripcion

El proyecto consta de 6 subcarpetas:
* Tarea1
* Tarea2
* Tarea3
* Tarea4
* Tarea5
* IntegralesProyectivas

Dentro de cada una se encontrara la resolucion en CUDA con C++ y OpenCV con Python/C++ donde colocamos el codigo desarrollado y las imagenes utilizadas para su resolucion.

## Intrucciones

### TAREA 1

**Descripcion**: Realizar utilizando CUDA con C++ el script para generar el histograma de cambio de brillo y otro de contraste

**Archivos**: 
* Carpeta "Tarea1": Imagen y script de Colab

**Solucion**: 
1. Ingresamos a Colab y abrimos el archivo(`Tarea1/brillo_contraste.ipynb`).
2. Una vez abierto, ejecutamos en orden los comandos.
3. Usamos OPENCV para cargar las imagenes y pasarlas a 2 matriz de dos dimensiones.

4. Reducimos el tamaño de las matrices para facilitar el proceso y que ambas sean de la misma dimensión

5. Declaramos la función CUDA para poder aumentar o reducir el brillo y el contraste: R(x, y):= (A(x,y) + factor para el brillo y R(x, y):= (A(x,y) * factor para el contraste, donde la matriz resultante es la asición o multiplicaciòn por una constantente.
6. Declaramos las filas y columnas y tamaño de las matrices
7. Copiamos la matriz a una varable declarada en cuda/c++
8. Declaramos la matriz de salida
9. Procedemos a localizar la memoria en el GPU
10. Copiamos las matrices A del host al device
11. Definimos red y los bloques
12. Lanzamos la funcion Kernel
13. Copiamos la matriz resultante del device(gpu) al host
14. Liberamos la memoria del gpu.
**Screenshots de Test**:

## TAREA 2 

**Descripcion**: Realizar utilizando CUDA con C++ el script para generar el histograma de ecualizacion de una imagen

**Archivos**: 
* Carpeta "Imagenes": imagenes de prueba del script
* Script EcualizarImagen: Script del Colab(principal)
* Proyecto Ecualizador en VS: Proyecto en Visual Studio 2022 con OpenCV para obtener el histograma y mostrar las imagenes de resultado.

**Solucion**: 

1. Ingresamos a Colab y abrimos el archivo(`Tarea2/EcualizarImagen.ipynb`)
2. Una vez abierto, ejecutamos en orden los comandos como aparece en la imagen:
![Funciones iniciales](images/tarea2_1.PNG)
3. Llegamos al cuarto cuadro y veremos el codigo el cual tiene definido un histograma de la imagen que se tomo como ejemplo, en este caso de la imagen en (`Tarea2/Imagenes/kodim08_grayscale.png`)
4. Ejecutamos el codigo.
5. Tendremos la salida por pantalla de los pasos que esta realizando

    * Primero mostrara un mensaje de inicio
    * Segundo un array de las acumulaciones
    * Tercero, un array indicando el inicio y fin del proceso
    * Y por ultimo el array del histograma ecualizado, indicando las frecuencias por cada posicion.
    * Podemos llevar este array a los proyectos de Visual Studio 2022 de la carpeta "Ecualizador" y verificar el resultado en imagen.

**Screenshots de Test**:

![Ejecucion del programa](./images/tarea2_2.png)

![Imagen Equalizada resultado](./Tarea2/Imagenes/kodim08_grayscale_equalized.PNG)

## TAREA 3 

**Descripcion**: Realizar utilizando CUDA con C++ el script para generar el histograma de suma y resta de imagenes

**Archivos**: 
* Imagenes: imagenes de prueba del script
* Script de Suma y Resta: Script del Colab(principal)

**Solucion**: 

1. Ingresamos a Colab y abrimos el archivo(`Tarea3/sumar_dos_imagenes.ipynb`)
2. Una vez abierto, ejecutamos en orden los comandos
3. Usamos OPENCV para cargar las imagenes y pasarlas a 2 matrices de dos dimensiones

4. Reducimos el tamaño de las matrices para facilitar el proceso y que ambas sean de la misma dimensión

5. Declaramos la función CUDA para poder sumar/restar las matrices usando: R(x, y):= (A(x,y)+B(x,y))/2 donde la matriz resultante es la división entre dos de la suma de las dos matrices.

6. Declaramos las filas y columnas y tamaño de las matrices

7. Copiamos la matriz a una varable declarada en cuda/c++

8. Declaramos la matriz de salida

9. Procedemos a localizar la memoria en el GPU

10. Copiamos las matrices A y B del host al device

11. Definimos red y los bloques

12. Lanzamos la funcion Kernel

13. Copiamos la matriz resultante del device(gpu) al host

14. Liberamos la memoria del gpu.

## TAREA 4

**Descripción**: Realizar utilizando CUDA con C++ el script para generar una convolución

**Archivos**: 
* Imagen: Imagen de prueba del script
* Script Convolución: Script del Colab(principal)

**Solución**: 

1. Ingresamos a Colab y abrimos el archivo(`Tarea4/Convolucion.ipynb`)
2. Una vez abierto, ejecutamos en orden los comandos
3. Usamos OPENCV para cargar la imagen y pasarla a una matriz.

4. Reducimos el tamaño de la matriz.

5. Declaramos la máscara

6. Dimensionamos la matriz, declaramos la máscara.

7. Declaramos la función iterativa para que la convolución se realice y la máscara se efectúe sobre la imagen sin salirse del rango.

8. Copiamos la matriz a una varable declarada en cuda/c++

9. Declaramos la matriz de salida/resultado

10. Procedemos a localizar la memoria en el GPU

11. Copiamos las matrices A del host al device

12. Definimos red y los bloques

13. Lanzamos la funcion Kernel

14. Copiamos la matriz resultante del device(gpu) al host

15. Liberamos la memoria del gpu.

## TAREA 5

**Descripcion**: Realizar utilizando CUDA con C++ el script para generar un caso de template matching con una matriz de imagen principal, otra de template y que vaya generando submatrices con las mismas dimensiones y utilizando una formula de medida(en este caso se utilizo distancia euclidiana), considere el minimo valor e indique las coordenadas iniciales donde se encontro este punto.

**Archivos**: 
* Carpeta "Imagenes": imagenes de prueba del script
* Proyecto templateMatching: Proyecto en Visual Studio 2022 con OpenCV para obtener la matriz de datos de la imagen y template
* Proyecto TMachingv1 en VS2022: Proyecto en Visual Studio 2022 con CUDA para obtener el valor de los puntos minimos cercanos con template matching.

**Solucion**: 

1. Ingresamos a VS 2022 y abrimos el proyecto(`Tarea5/templateMatching`)
2. Una vez abierto, verificamos las rutas de las imagenes(tanto la imagen principal como el template y ejecutamos):
<!-- ![Funciones iniciales](images/tarea2_1.PNG) -->
![Ejecucion del proyecto para obtener matrices](templateMatching.png)

3. Ahora abrimos el otro proyecto con CUDA TMatchingv1 y copiamos las matrices en el codigo (`Tarea55/TMatchingv1/`)

4. Ejecutamos el codigo.

5. Tendremos la salida por pantalla de la siguiente manera

    * Primero generara en 2 variables las 2 matrices, de la imagen y el template
    * Segundo, llamara a la funcion DistanciaEuclidiana la cual operara por submatrices
    * Tercero, por cada submatriz del mismo tama;o que el template ira sacando la distancia con esa matriz
    * Y por ultimo devolvera un array con las distancias calculadas.
    * Mostrara por pantalla la menor distancia y a que punto la obtuvo aproximadamente.

**Screenshots de Test**:

![Proyecto con CUDA ejecutandose y mostrando resultado](CUDATM.png)

![Medida utilizando Distancia Euclidiana](distanciaEuclidiana.png)


## INTEGRALES PROYECTIVAS

**Descripción**: Trabajo adicional realizado con Python para reconocimiento de rostros.

**Archivos**: 
* Imagenes: IMPORTANTE, las imágenes se colocan en una carpeta llamada "images/"
* Imagen Prueba: IMPORTANTE, la imagen de prueba se usa para ver si esta imagen que contiene una cara humana, según las integrales proyectivas es una cara humana o no.
* Script Integrales Proyectivas: Script del Colab(principal)

**Solución**: 

1. Ingresamos a Colab y abrimos el archivo(`Tarea_extra/integrales_proyectivas_master_ccs.ipynb`)
2. Una vez abierto, ejecutamos en orden los comandos
3. Declaramos una función que nos divida la imagen en cuadrilateros.

4. Declaramos una función que procesará la nueva imagen.

5. La siguiente celda contiene prácticamente el mismo código que la anterior, con las llamadas a las librerías que nos van a ser de ayuda.

6. En esa celda se carga y redimensiona la imagen, para que todas las imagenes tengan al misma dimension.

7. Dividimos la imagen en 8 rows/filas. Este caso es para el histograma vertical de la cara.

8. Guardamos las listas de las rows en un csv.

9. Dividimos la imagen en caudrilateros. 

10. Elegimos las placas cuadrilateras que caen en las regiones de ojos y boca.

11. Convertimos las placas en matrices y las convertimos en listas para simplificar el proceso de sacar la media de la región. 

12. Guardamos las medias de las regiones de ojos y boca en dos CSV's diferentes.

13. Visualizamos los gráficos.

14. Con un bucle for procedemos a verificar si la nueva imagen es una cara humana o no, caso las medias caigan dentro de los rangos.

15. Con un bucle for procedemos a verificar si la nueva imagen es una cara humana o no, caso las medias caigan dentro de un rango de media de los puntos del dataset original.
