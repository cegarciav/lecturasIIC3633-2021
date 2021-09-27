# Deep Learning based Recommender System: A Survey and New Perspectives
Autores: S. Zhang, L. Yao, A. Sun, Y. Tay

## Breve Resumen
<p align="justify">
  El paper inicia con la mención de múltiples ejemplos del uso de deep learning en los sistemas recomendadores y cómo estos demuestran gran mejoría por sobre los sistemas recomendadores clásicos. Luego, se describe los objetivos buscados por los autores: hacer una revisión del trabajo existente sobre sistemas recomendadores basados en deep learning y proponer un modelo de clasificación, hacer un resumen del "estado del arte" de este tema y discutir sobre los desafíos y posibles direcciones de investigación futura. No obstante, la parte a ser resumida y analizada en esta crítica solo considera la revisión sobre la investigación actual, el resumen del estado del arte y parte del sistema de clasificación propuesto por los autores.
</p>

<p align="justify">
  Para poder analizar el trabajo existente sobre sistemas recomendadores basados en deep learning, los autores describen rápidamente las técnicas clásicas de recomendación, así como algunos de los modelos más conocidos de deep learning (MLP, CNN, RNN, LSTM, etc). Luego, se analiza algunas de las ventajas que tiene el hecho de trabajar con modelos de deep learning, como la posibilidad de representación no lineal entre las interacciones usuario-item. Adicionalmente, se discute de forma superficial algunos de los argumentos contra el uso del deep learning, no solo para sistemas recomendadores, sino de forma general. Finalmente, en lo que concierne al estado del arte de la recomendación basada en deep learning, los autores describen métodos de recomendación basada en deep learning clasificándolos según el modelo de deep learning en el que se basan y según si usan uno o más modelos de deep learning (casos híbridos). De estos modelos, esta crítica solo revisará los sistemas basados en Multilayer Perceptron (MLP), Autoencoder (AE) y Convolutional Neural Network (CNN).
</p>

## Crítica personal
<p align="justify">
  En primer lugar, los autores mencionan que aunque existe un aumento exponencial del desarrollo de los sistemas recomendadores basados en deep learning, hasta el momento de escribir el paper existen solo dos fuentes que intentaron hacer esta especie de sondeo del estado y direcciones de la investigación sobre este tipo de sistemas recomendadores. En este sentido, me parece importante destacar esto como un indicio de lo joven que es el campo del uso de deep learning en sistemas recomendadores, pues el paper fue publicado hace solo tres años. Esto claramente implica que hay muchas cosas que aún no se comprenden del todo o que simplemente no se han estudiado, por lo que existe mucho terreno sobre el que se puede trabajar y aportar.
</p>

<p align="justify">
  En segundo lugar, creo que es muy importante que lo autores mencionen algunas de las falencias que tienen las técnicas de deep learning. Esto es positivo, pues los autores muestran que, si bien el deep learning representa grandes avances, no es una solución perfecta a todos los problemas. Un punto negativo mencionado sobre deep learning es la dificultad de interpretación de los resultados. Menciono este en particular debido a que es una de las razones por las que el estudio de modelos de deep learning no me atrae mucho, pues usualmente tengo la preferencia por aplicar conceptos que sí logro comprender. De todas formas, entiendo el interés por utilizar sistemas de deep learning aunque no se comprendan, pues la situación es similar a lo que pasa con el sistema nervioso humano (se usa y es estudia, pero no se comprende del todo), que finalmente es la base de la idea de desarrollar redes neuronales.
</p>

<p align="justify">
  En tercer lugar, en la sección de Feature Representation Learning con MLP, se indica que la combinación de un single layer perceptron + multilayer perceptron en *Wide & Deep Learning* permite capturar tanto memorización como generalización. Esto sería una ventaja respecto a modelos clásicos de recomendación como collaborative filtering, pues podría ayudar a reducir los efectos del cold start mediante el uso de la generalización. Eso sí, no se debe olvidar que para evitar este cold start también se propone la combinación de collaborative filtering con algúnb modelo content-based, por lo que sería importante evaluar si la introducción de deep learning es efectivamente conveniente. En la misma sección de uso de MLP, en *Deep Semantic Similarity based Personalized Recommendation* se hace mención del uso de un espacio commún de "tags" o etiquetas que son usadas para describir tanto a los usuarios como a los ítems. Sería interesante que se hubiese mencionado un poco más sobre cómo este tipo de sistemas puede escalar en caso de que se ingresen nuevos tipos de usuarios o ítems que puedan requerir el ingreso de nuevos tags.
</p>

<p align="justify">
  En cuarto lugar, en la sección de *Autoencoder based Collaborative Filtering*, se indica que aumentar la cantidad de capas en AutoRec para formular una red más profunda puede llevar a leves mejoras. Sería interesante poder ver qué tan *leves* son estas mejoras con respecto al tiempo de cómputo añadido por cada capa adicional, o si existen parámetros que cambien la proporción mejora/tiempo_de_cómputo. De esta manera, se podría evaluar el trade-off existente y definir bajo cuáles condiciones conviene añadir capas y bajo cuáles no en caso de encontrar patrones.
</p>

<p align="justify">
  Finalmente, en la sección *CNNs for Image Feature Extraction* no me queda muy claro si el uso de dos CNNs es tal que una recomienda imágenes que le gustan al usuario y otra recomienda imágenes que no, o si bien ambas trabajan con los dos tipos de imágenes. Aunque no tengo claro eso, de todas formas me parece muy interesante el uso tanto de ítems afines al usuario como de ítems no afines. En algunos casos, un usuario podría tender a no elegir un ítem porque se parece a uno que no le gustó, lo que no es exactamente lo opuesto a elegir un ítem porque se parece a uno que sí le gustó. Entonces, disponer de ambos inputs podría ser muy benéfico, pero obviamente hay que tener en cuenta el trade-off entre aumento de precisión y aumento en tiempo de ejecución.
</p>
