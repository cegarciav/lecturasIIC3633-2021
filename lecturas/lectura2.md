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

## Crítica personal
<p align="justify">
  En primer lugar y como comentario general, considero que este paper requiere cierto nivel de entendimiento de álgebra lineal, no es de ninguna forma un paper introductorio. Si bien no es muy extenso, hay secciones del paper que pueden hacerse un poco densas de leer. No obstante, se aprecia de todas formas el hecho de que existen ciertos ejemplos explicativos o incluso imágenes que aterrizan un poco el concepto descrito. Un ejemplo de esto es la consideración de los biases integrados tanto por ítems como por usuarios y el ejemplo de Titanic (sobre calificada) y Joe (usuario exigente).
</p>

<p align="justify">
  En segundo lugar, me gustaría destacar el método incremental que se utilizó para describir el modelo. Se comienza con un modelo muy simple y de a poco se da opciones de cómo añadir complejidad en él. Al menos hasta donde yo entendí, la aplicación de cada factor de complejidad en el sistema es independiente de los otros factores, lo que hace que el modelo sea más versátil según el contexto en que se quiera aplicar o según los datos que posea una persona que quiera implemtar lo propuesto por el paper
</p>

<p align="justify">
  En tercer lugar, me parece muy relevante la inclusión de los biases que tanto usuarios como ítems integran al sistema. Esto está muy en línea con el paper **Collaborative Filtering Recommender Systems** de J. Ben Schafer, Dan Frankowski, Jon Herlocker, Shilad Sen. Efectivamente, es importante tener en consideración que hay ítems que reciben, a nivel general, ratings más o menos severos, así como usuarios que son más o menos críticos. A pesar de esto, no estoy 100% convencido de la elección del factor $\mu$ como el promedio de todos los ítems. Me imagino que para que el promedio sea representativo, habría que considerar una distribución simétrica de ratings. Quizá una opción alternativa podría ser considerar la mediana de los ratings en vez de la media.
</p>

<p align="justify">
  Finalmente, creo que considerar la evolución temporal tanto de valoración de ítems como de gustos de usuario es algo realmente esencial para los sistemas recomendadores. Quizá en personas de más de 40 años o con un criterio formado en base a una mayor trayectoria los gustos podrían llegar a volverse menos variables. No obstante, en adolescentes o en personas nuevas en cierto rubro el tiempo en un factor crítico. Personalmente, por ejemplo, mis gustos musicales han evolucionado drásticamente respecto a lo que eran hace 10 años, pero en un período más corto (~2-3 años) han mantenido ciertas características más estables o constantes. Asimismo, el nivel de confianza se hace clave en mi opinión, y me parece muy interesante que se haya incluido en este paper. Continuando con mi gusto musical, me ha pasado que a veces escucho una canción por curiosidad y no me gusta el estilo del artista, por lo que no vuelvo a escuchar más música suya. Por otro lado, si una canción me cautiva, comienzo a escuchar más música de ese artista con el fin de validar si fue la canción fue un caso particular o si realmente me gusta el estilo del artista. Entonces, la intuición indica que hay ítems con ciertas características a los que un usuario accede una vez y otros a los que el usuario accede muchas veces, y que la recomendación debería contemplar este hecho. Como consecuencia, esta intuición dejaría claro que ciertos inputs ingresados por el usuario, incluso voluntariamente, son más confiables que otros.
</p>
