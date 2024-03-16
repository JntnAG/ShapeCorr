# Correspondencia de formas 3D

La CF podemos dividirla principalmente en tres areas de accion:
![Pipeline Shape Correspondence](/pics/pipe1.png)


## Pre procesamiento

El Pre-procesamiento va ligado a ajustar nuestros modelos 3d de la mejor forma cosa que filtremos, y organicemos los datos para que sean facilmente procesables por nuestros maquinas.

*Destacando para nuestro caso de estudio princiapl la reduccion de vertices y faces.
![Decimación de Vértices y Caras](/pics/prepro.png)
    

## Aprendizaje de Forma (Descriptor)

Los descriptores de formas pueden variar bastante, desde descriptores con histogramas y metricas de volumenes/areas hasta descriptores por curvaturas, firmas espectrales o por redes neuronales

✍️💼-> <a href="Codes/3D_Shape_descriptors.ipynb">3D descriptores generales</a>
Sin embargo, para nuestro caso solo nos interesan aquellos que sean robustoz frente a isometrías (transformaciones rigidas).
siendo relevante aquellos basados en medidas como curvaturas generales o geodesicas. ligando esto a su vez a sistemas espectrales con enfasis en autovalores y autovectores. Cabe resaltar que las redes neuronales tambien son planteadas como tecnicas robustaz frente a estas variaciones de rotacion y traslación.

Insertar archivo de kernels geometricos
Insertar archivo de descriptor NN


## Analisis de Correspondencia

Finalmente, para validar la correpsondencia de forma....

Insertar Fmaps
Insertar GraphAE
