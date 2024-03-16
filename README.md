# Correspondencia de formas 3D

La correspondencia se forma se puede dividir en tres bloques principales:
![Pipeline Shape Correspondence](/pics/pipe1.png)


## Pre procesamiento

El preprocesamiento está destinado a ajustar nuestros modelos 3D de la mejor manera posible, de modo que filtremos y organicemos los datos para que sean fácilmente procesables por nuestras máquinas.

*Destacando en nuestro caso de estudio principal la reducción de vértices y caras.
![Decimación de Vértices y Caras](/pics/prepro.png)
    

## Aprendizaje de Forma (Descriptor)

Los descriptores de formas pueden variar bastante, desde histogramas y métricas de volúmenes/áreas hasta curvaturas, firmas espectrales o redes neuronales.

✍️💼-> <a href="Codes/3D_Shape_descriptors.ipynb">3D descriptores generales</a>

Sin embargo, para nuestro caso solo nos interesan aquellos que sean robustos frente a isometrías (transformaciones rígidas), siendo relevantes aquellos basados en medidas como curvaturas generales o geodésicas, relacionándolos a su vez con sistemas espectrales con énfasis en autovalores y autovectores. Cabe resaltar que las redes neuronales también son consideradas como técnicas robustas frente a estas variaciones de rotación y traslación.

Insertar archivo de kernels geometricos
Insertar archivo de descriptor NN


## Análisis de Correspondencia

Finalmente, para validar la correspondencia de forma, debemos llevar las formas 3D a un entorno de comparación mutuo, donde las rotaciones, traslaciones y cantidad de descriptores a comparar sean iguales.

Por ende, tenemos inicialmente planteadas dos áreas:

Utilizar una transformación lograda entre los descriptores (Fmaps)
Buscar un espacio latente al cual llevemos nuestros descriptores y podamos compararlos.
Insertar Fmaps Insertar GraphAE

Por ende tenemos inicialmente plateadas dos areas:
    1. Utilizar una transformacion lograda entre los descriptores (Fmaps)
    2. Buscar un espacio latente al cual llevemos nuestros descriptores y podamos compararlos.
    
Insertar Fmaps
Insertar GraphAE


### Fmaps Notes:
* Fmaps tendrá un costo computacional dependiendo de los descriptores a comparar, este se incrementa especialmente para formas complejas o conjuntos de datos grandes {la matriz generada sería de tamaño NxN (N = # de descriptores)}.
* Solo realiza comparaciones y transformaciones 1 vs 1, brindando un nivel mínimo de generalización.
* Las FMAPs pueden no ser robustas ante deformaciones extremas o no lineales en las formas, funcionando especialmente con errores entre formas muy diferentes.
* Debido a que la matriz de transformación C se logra 1 vs 1, incluso si las figuras son totalmente diferentes y debido a cómo se crea el mapa funcional, tendrán un buen grado de correspondencia.
* Es necesario que el descriptor a comparar sea robusto frente a rotaciones e isometrías, ya que no se pueden percibir únicamente con el fmaps, lo que afecta la precisión de la correspondencia.
