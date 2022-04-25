# Explicación de redes neuronales convolucionales
  
Las redes neuronales convolucionales reciben los píxeles, extraen las características y las clasfican con capas regulares. De esta manera, este tipo de redes neuronales dejan de depender del tamaño y la posición de las cosas.  
Para evolucionar una red regular a una red convolucional necesitamos agregar dos tipos nuevos de capas:
- capas de convolución: lo que hace el dividir la imagen en su nº de capas (rgb, b/n) y sacar características de ellas con cada uno de los núcleos que se utilizan (formas, líneas...)
- capas de agrupación: lo que hace es reducir el tamaño de la imagen y resaltar las características más importantes. La más utilizada es la capa de agrupación máxima, que lo que hace es recorrer la imagen haciendo bloques de píxeles en los que conserva información del píxel de mayor valor, eliminando los restantes (imagen más pequeña y resaltada).  
Ambas capas son las que extraen las característica de la imagen para poder clasificarlas con las capas regulares (se ponen antes de las capas ocultas del modelo). Ver el siguiente vídeo para una explicación más detallada: https://www.youtube.com/watch?v=AwTH_0yW9_I  
  
Conv2D() es el parámetro que se usa para crear una red neuronal convolucional, y no hace falta indicarle cuantas neuronas tiene que tener, sino:
- núcleos a utilizar: 32
- tamaño de núcleos: (3,3)
- tamaño de imagen de entrada y nº de canales (1 para BN): input_shape=(28, 28, 1)
  
En estos 4 scripts, se parte de un modelo de red neuronal regular (sin ser convolucional) en el script 1, pasándola a convolucional en el script 2, y aplicando un proceso de mejora 'Droupout' en los scripts 3 y 4 (solo añade más 'epochs' en este último). Este proceso de mejora podría ser:
- Aumento de datos: esto hace que se generen imágenes más variadas a partir de las iniciales (giradas, volteadas, rotadas, != tamaño...), de modo que el set de datos inicial queda más variado.
- Dropout (el aplicado): este comando se incluye con un valor entre 0 y 1, de manera que establece que en cada 'epoch' las neuronas tengan un porcentaje de desactivación (el dado a la función dropout). Esto hace la red más resiliente (los pesos de todas las neuronas están más equilibrados).
