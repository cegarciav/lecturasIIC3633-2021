# Análisis del paper Matrix factorization for recommender systems
Autores: Yehuda Koren, Robert Bell, Chris Volinsky

## Breve Resumen
<p align="justify">
  El paper inicia poniendo en contexto la situación: describe el surgimiento de la necesidad de los sistemas recomendadores, menciona algunas diferencias entre content filtering y collaborative filtering. En particular, se destaca la ventaja de collaborative filtering de no necesitar de una definición explícita de un perfil de usuario e ítem mediante atributos, así como la desventaja del *cold start*. Luego, se plantean dos aproximaciones en collaborative filtering: nearest-neighbours y modelos de factores latentes. Particularmente, se menciona la popularidad de los modelos de factores latentes basados en factorización matricial debido a su flexibilidad, escalabilidad y precisión. En línea con esto, el modelo central del paper es un modelo de factores latentes basado en factorización matricial.
</p>

<p align="justify">
  El modelo propuesto se basa en los vectores p<sub>u</sub> para los usuarios y q<sub>i</sub> para los ítems, ambos de dimensión *f* que corresponde a la cantidad de factores a considerar y tales que el producto escalar entre q<sub>i</sub><sup>T</sup> y p<sub>u</sub> corresponde al rating estimado para el ítem i y el usuario u. Luego, se describe la función que describe el modelo y se presentan dos alternativas de optimización para obtener los vectores p y q: stochastic gradient descent y ALS (alternating least squares). Posteriormente, se describen algunas consideraciones para el modelo, como el concepto de bias ingresado tanto por usuarios como por ítems, maneras de incluir información adicional para sobrellevar el problema del *cold start*, el efecto del tiempo en la popularidad de ítems y en los gustos de los usuarios, e incluso el nivel de confianza de la información ingresada al sistema.
</p>

<p align="justify">
  Finalmente, los autores describen su experiencia con el Netflix Prize: cómo el set de datos y el premio ofrecidos por Netflix aceleró la investigación en el campo de los sistemas recomendadores y cómo lograron evidenciar el potencial de los métodos basados en factorización matricial
</p>
