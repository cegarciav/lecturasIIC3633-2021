# Context-Aware Recommender Systems
Autores: G. Adomavicius, B. Mobasher, F. Ricci, A. Tuzhilin

## Breve Resumen
<p align="justify">
  Los autores comienzan por poner en evidencia que otros tipos de sistemas recomendadores como content-based y user-based ignoran el contexto en el que se va a recomendar. Adicionalmente, cuestionan la definición de contexto, que aunque puede no ser clara, su influencia se hace evidente en el proceso de recomendación. Luego, se definen dos aproximaciones para entender el "contexto": la representacional, que busca definir el contexto de forma estática e independiente de la actividad realizada, y la interactiva, cuya representación depende de la actividad realizada y existe una especie de feedback cíclico entre contexto y actividad. Dado que el sistema recomendador podría no tener toda la infomración del contexto disponible, esta información se diferencia según lo que sabe el sistema (totalmente observable, parcialmente observable y no observable) y según cómo esta cambia a través del tiempo (estática y dinámica). De esta forma, un contexto totalmente observavle y estático se describe como representacional, mientras que uno total o parcialmente observable, y dinámico, pasaría a ser interactivo.
</p>

<p align="justify">
  Si bien, en general, el artículo se centra en sistemas recomendadores de contexto estático y totalmente observables, también tiene algunas referencias a lo que sucede bajo contextos dinámicos o bajo información parcialmente observable o no observable. También se hace la distintión entre cómo se usa el contexto para recomendar. Este uso puede ser de prefiltrado y postfiltrado, que utilizan sistemas recomendadores clásicos y el contexto es una capa adicional, pero igualmente puede darse el uso del contexto directamente en el proceso de recomendación mismo, esto es, como parte del modelo de recomendación. El paper finaliza con la descripción de distintos escenarios de uso de los sistemas basados en contexto, así como con distintos desafíos y posibles direcciones de investigación para este tipo de sistemas recomendadores.
</p>
