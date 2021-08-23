# Análisis del paper Collaborative Filtering Recommender Systems
Autores: J. Ben Schafer, Dan Frankowski, Jon Herlocker, Shilad Sen

## Breve Resumen
<p align="justify">
  El paper inicia con el principio base de los sistemas recomendadores: cómo los humanos escuchamos opiniones de otros y aprendemos a valorarlas y a juzgar cuáles nos parecen pertinentes y cuáles no. Luego, se introducen conceptos mínimos requeridos para entender la idea de los sistemas CF, como usuario, ítems, ratings, tipos de ratings (escalares, binarios, unitarios) y la forma cómo se colecta la información para estos ratings (implícita o explícitamente). También, se hace mención al problema inicial que se busca resolver: existe mucha información, por lo que debe ser clasificada de forma útil para los usuarios o grupos de usuarios.
</p>

<p align="justify">
  Posteriormente, se mencionan algunas tareas para las que son útiles los sistemas CF: ayudar a los usuarios a encontrar ítems que no conocen, aconsejar a los usuarios sobre un ítem dado, ayudar a un grupo a encontrar algo que les guste como conjunto y no como individuos, entre otras. Igualmente, se mencionan las familias de funcionalidades. Por ejemplo, se aclara que no es lo mismo que un sistema recomiende ítems a que un sistema prediga de antemano la evaluación esperada para un ítem específico. Esta idea de diferentes tareas realizables por los sistemas CF se complementa con propiedades de la información a recomendar que los autores consideran que calzan bien con los sistemas, siempre con un espíritu de mantener la mente abierta y dar paso a la discusión más que a la aceptación sin más.
</p>

<p align="justify">
  Luego, se desarrolla de forma más detallada la información introducida. Por ejemplo, se clasifican los algoritmos entre probabilísticos y no probabilísticos y se da ejemplos de implementación de algunos. Además, se mencionan desafíos a evaluar en algunos de ellos y se profundiza en aspectos como ratings o conceptos como el cold starting y sus implicancias. El paper continúa desarrollando conceptos como la evaluación, en que deja en evidencia que la precisión no es el único factor clave a tener presente, o como la importancia de la integración de sistemas de recomendación colaborativa y las interfaces gráficas visibles por el usuario. Finalmente, los autores mencionan desafíos aún no resueltos como los aspectos de confianza (los sistemas confían en que el usuario entrega información correcta) e incluso añade una sección de preguntas abiertas.
</p>

## Crítica personal
<p align="justify">
  En primer lugar, destaco el carácter introductorio del paper: me gustó que iniciara con el origen intuitivo de los sistemas recomendadores, que es el hecho de que como personas estamos constantemente, y de forma intuitiva, compartiendo nuestros intereses con otros. Creo que esta modalidad de introducción hizo más simple e incluso entretenido de leer el paper, pues aterriza la base a algo que no solo los entendidos en el asunto pueden procesar.
</p>

<p align="justify">
  En segundo lugar, destaco la idea de Adomavicius et al. de crear una suerte de lenguaje SQL para recomendaciones. Sin embargo, creo que sería más apropiado pensar en un sistema de queries más de tipo no relacional, como lo que se hace con el sistema de aggregations en MongoDB, principalmente considerando que las recomendaciones necesitan de una flexibilidad que quizá un sistema relacional no les puede dar (data no estructurada o esquemas fácilmente actualizables).
</p>

<p align="justify">
  En tercer lugar, me pareció muy correcto mencionar casos en los que los sistemas CF no son necesariamente la mejor solución, como ocurre cuando se tiene filtros por características objetivas. En la actualidad, con el desarrollo de la inteligencia artificial, machine learning, big data, data science, entre otras disciplinas o conceptos *de moda*, pasa que todos quieren ser parte de esa moda y casi forzar el uso de estas tecnologías en todo lo posible. Si bien no niego los resultados increíbles y el mundo de posibilidades que existen gracias a estos conceptos, me parece muy necesario aclarar que no son la solución a todo y que no siempre son aplicables ni necesarios. Por esto, considero correcto hacer énfasis en los comentarios de los autores de que los sistemas CF no son siempre la mejor solución, principalmente dado que el paper tiene esa característica introductoria hacia los sistemas recomendadores.
</p>

<p align="justify">
  En cuarto lugar, me llamó la atención ese concepto de complementariedad entre los sistemas CF y los sistemas content-based filtering. Al leer eso, lo primero que pensé fue en Netflix, ya que todas las recomendaciones son basadas en el usuario, pero a la vez son clasificadas según contenido (recomendados de terror, por haber sido visto anteriormente, porque se clasifican como series o como películas, etc).
</p>

<p align="justify">
  En quinto lugar, me pareció remarcable el hecho de que los user-based CF a la base no distingan entre similaridad de dos usuarios para un ítem popular vs un ítem controvertido. Efectivamente, me parece que encontrar similaridades entre dos usuarios frente a un ítem poco popular debería ser considerado más relevante, pues la probabilidad de encontrar esa similitud es menor. Por otro lado, que dos usuarios coincidan en un ítem universalmente considerado con buen rating o mal rating es más probable, entonces podría no ser tan significativo. De todas formas, es un tema complejo, porque la coincidencia frente a un ítem no popular podría ser una equivocación y si se le da mucha relevancia podría sesgar fácilmente al sistema. Entonces, de alguna forma sería necesario estudiar patrones de comportamiento para validar esa coincidencia frente a un ítem no popular.
</p>

<p align="justify">
  En sexto lugar, me gustaría hacer una acotación a la Ecuación (6) de la página 304. Tengo la impresión de que el factor r<sub>ui</sub> debería ser r<sub>uj</sub>, pues el índice j es el que indica los ítems ya evaluados por el usuario u, mientras que el índice i es el ítem a predecir. Entonces, se entiende que el rating r<sub>ui</sub> aún no está disponible, además de que sería una constante para la sumatoria.
</p>

<p align="justify">
  Finalmente, me gustaría tomar el punto del paper que hace referencia a la privacidad. Como se ha visto en clases y en el mismo paper, los sistemas estudiados requieren de información, o sea, de conocer a los usuarios. Sin embargo, un usuario preocupado por sus datos podría no querer entregar su información salvo que el sistema recomendador demuestre explícitamente que la información guardada no se está guardando con fines maliciosos. La gran pregunta es, ¿qué tan fácil es demostrar que esa información está siendo usada de una forma y no de otra? Si se toma el caso de Netflix, por ejemplo, se puede ver que la plataforma no funciona en un navegador en modo incógnito. ¿Cómo puedo asegurarme de que Netflix no está accediendo a cookies guardadas o a otras pestañas abiertas en paralelo y obteniendo más información sobre mí? Por otro lado, dado que Netflix permite crear distintos perfiles de usuario, la plataforma podría llegar a generar conclusiones sobre la conformación de los integrantes de la vivienda si se asume que una cuenta de Netflix está pensada para ser compartida por gente de una misma residencia. ¿Quién me asegura que esa información no está siendo vendida a otros servicios o cruzada con otras fuentes de información? Efectivamente, las cuestiones relacionadas a la privacidad son de alta importancia y debiesen ser reguladas por entidades competentes a nivel global, pues las implicancias del tráfico de datos pueden ser graves si la información cae en manos equivocadas.
</p>
