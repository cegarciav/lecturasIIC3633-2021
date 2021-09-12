# Análisis del paper Content-Based Recommendation Systems
Autores: Michael J. Pazzani, Daniel Billsus

## Breve Resumen
<p align="justify">
  El paper inicia con una breve introducción sobre la utilidad de los sistemas basados en contenido y las características generales de estos y sus componentes (ítems, usuarios, recomendación). Luego, describe tres tipos de data para los ítems (estructurada, no estructurada y semi-estructurada), algunas ventajas y desventajas de cada una y una forma de convertir data no estructurada en semi-estructurada, de tal forma que sea más utilizable para los sistemas recomendadores. Posteriormente, describe la información relevante que debe ser parte del perfil de usuario y cómo relacionar los sistemas recomendadores con ese perfil (aprendizaje de un modelo).
</p>

<p align="justify">
  Dado que se menciona que los algoritmos de clasificación son clave para los sistemas recomendadores basados en contenido, se describen algunos algoritmos de clasificación como los árboles de decisión, RIPPER, k vecinos más cercanos, entre otros. Para cada uno de estos algoritmos, se presentan algunas ventajas, desventajas y consideraciones. Finalmente, los autores hacen mención de algunas tendencias, limitaciones y extensiones de los sistemas basados en contenido
</p>

## Crítica personal
<p align="justify">
  En primer lugar, me parece notable que la fórmula para calcular el peso w(t, d) en TF*IDF elimine de forma tan elegante la relevancia de palabras como artículos (la, el, los, las) o preposiciones (a, ante, bajo, ...). Dado que el cálculo de los pesos de un término t en un documento d se hace de forma relativa a la presencia del término en todos los documentos, las palabras de uso común y que no afectan al tema principal pasan a tener pesos mínimos debido a cómo está escrito el numerador de la fórmula. Es más: si una palabra como "la" aparece en todos los documentos, se tiene que log(N/dft) = log(N/N) = 0, con lo que w("la", d) es 0
</p>

<p align="justify">
  En segundo lugar, me parece que el uso de algún algoritmo de *stemming* (lexema) para obtener el término raíz para el método TF*IDF se hace bastante útil para la clasificación de texto libre. Se hace mención sobre el hecho de que existe un significado común bajo las palabras (1) "compute", "computation", "computer", "computes", and "computers", por ejemplo, lo que es interesante: si todas esas palabras se consideraran como independientes en un texto, su probabilidad podría ser baja, lo que daría paso a que no se consideren como palabras centrales del texto. No obtante, si se obtiene su raíz o *stem*, ambas pasan a formar parte de un solo término, lo que les asegura mayor relevancia. Se hace evidente de todas formas la necesidad de cautela al momento de utilizar un algoritmo de *stemming*, pues obtener la raíz de las palabras podría no ser trivial. Por ejemplo, la palabra "compulsory" tiene las mismas 5 letras que todas las palabras mencionadas al principio de este párrafo, pero su significado es totalmente independiente a la familia de palabras asociadas a la computación.
</p>

<p align="justify">
  En tercer lugar, creo que es importante la mención de la debilidad que tiene la distancia euclidiana al momento de calcular los K vecinos más cercanos. Como se vio en las primeras clases del curso, la distancia euclidiana puede tener errores según la distribución de los clusters de datos disponibles. Claramente, se debe tener cierto nivel de criterio al momento de elegir una u otra, lo que en más de tres dimensiones probablemente se deba hacer en base a experimentación más que a visualización. En el siguiente enlace, se muestra de forma más gráfica y en dos dimensiones un ejemplo de cómo la elección entre utilizar distancia euclidiana y similaridad coseno puede entregar información diferente sobre el dataset Iris: https://www.baeldung.com/cs/euclidean-distance-vs-cosine-similarity
</p>

<p align="justify">
  En cuarto lugar, es interesante el supuesto que se hace en el método Naïve Bayes: la probabilidad de que una palabra aparezca en un texto es independiente de la probabilidad de que otras palabras aparezcan. Si bien esto simplifica los cálculos a una multiplicación de términos, el estudio del lenguaje natural hace evidente el hecho de que la probabilidad de aparición de una palabra en un texto tiene una alta dependencia de su contexto. De hecho, la aparición de una palabra puede no depender de las palabras que la rodean estrictamente, sino de palabras incluidas inclusive en párrafos diferentes del mismo texto
</p>

<p align="justify">
  En quinto lugar, destaco un elemento reiterativo en los papers leídos para el curso hasta ahora: el desarrollo de la web y la explosión en cantidad de información disponible. Probablemente, de no ser por el desarrollo de la web, la investigación y el desarrollo de los sistemas recomendadores no tendría el nivel que conocemos en la actualidad. Otro elemento que se menciona en este paper, al igual que en Collaborative Filtering Recommender Systems de J. Ben Schafer, Dan Frankowski, Jon Herlocker, Shilad Sen, es el complemento que puede ser hecho entre sistemas recomendadores colaborativos y sistemas recomendadores basados en contenido. Efectivamente, se puede concluir que ambas aproximaciones combinadas pueden llevar a resultados mucho más precisos, pues mientras los sistemas basados en contenido utilizan features más "exactas", los sistemas colaborativos permiten atacar información más subjetiva. Si bien es un hecho que usar dos sistemas recomendadores podría resultar en problemas de performance y se necesitaría definir protocolos sobre cuándo usar uno vs otro o cómo ponderar la información provista por ambos, el desarrollo tecnológico y la capacidad de cómputo existente en la actualidad podría hacer que estos problemas no sean necesariamente graves.
