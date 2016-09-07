Algorithm Naive Bayes - Machine Learning
----------------------------------------

Éste algoritmo utiliza principios de probabilidad para clasificar.
Utiliza probabilidades de eventos anteriores para estimar la
probabilidad de futuros eventos.

Un ejemplo en el que se aplica Bayes:

-   Correo Spam: Utiliza la frequencia de las palabras en correos no
    deseados para detectar futuros correos Spam.

La probabilidad de un evento está entre 0 y 100 por ciento. Si es 0 el
evento nunca ocurrirá, si es 100 el evento ocurrirá con toda certeza.

### Funcionamiento

Utiliza un training data para calcular las probabilidades para cada
clase basado en las diferentes variables. Cuando se utiliza con nuevas
observaciones utiliza las probabilidades observadas para predecir la
clase más probable para las nuevas características.

se ha usado:

-   Clasificación de texto, spam, identificación de autor o
    categorizar temas.
-   Detección de intrusos o anomalías en las redes de ordenadores.
-   Diagnóstico de condiciones médicas, cuando tenemos un conjunto
    de síntomas.

Éste método es bueno con problemas en los que la información de
numerosos atributos se debe considerar de forma simultánea con el fin de
estimar la probabilidad de un resultado. Utiliza todas las variables
necesarias para predecir el resultado.

### Probabilidad

Número de veces que sucede un evento dividido por el total de eventos.
Ejemplo: Si 10 de cada 50 emails son Spam, la probabilidad de que un
correo sea spam será un 20%.

*P(A) - Probabilidad del evento A (ej:P(Spam)= 20%)*

La probabilidad de todos los posibles resultados tiene que ser 100%.

*P(non-Spam)= 1- 20% = 80%*

Ésto sucede porque spam y non-spam son mutuamente exclusivos.

### Probabilidad Conjunta

Algunas veces queremos saber la probabilidad de eventos no mutuamente
exclusivos. Por ejemplo consideramos que tenemos un segundo evento que
es que el email contenga una palabra en concreto. Para mucha gente esta
palabra solo aparece en un mensaje Spam, es una evidencia fuerte de que
el mensaje es Spam. Pero puede ser que no todo mensaje con esa palabra
sea Spam y que no todos los Spam contengan esa palabra.

-   Spam con la palabra
-   Spam sin la palabra
-   non-Spam con la palabra
-   non-Spam sin la palabra

El 20% era Spam, el 5% de todos los email contiene la palabra. Queremos
saber la probabilidad de que sea Spam y tenga la palabra.

P(Spam ⋂ Word)= P(A) \* P(B)

P(Spam ⋂ Word)=0.2 \* 0.05= 0.01

Pero esa sería la probabilidad si los eventos fueran independientes.
Pero en éste caso son dependientes con lo que ese cálculo es erroneo.

### Probabilidad Condicional con el Teorema de Bayes

La relación entre eventos dependientes se puede explicar con el teorema
de Bayes:

*P (A|B) = La probabilidad del evento A cuando ocurre el evento B.*

La probabilidad del evento A depende del evento B.

$$P(A|B)=\\frac{P(B|A)\*P(A)}{P(B)}= \\frac{0.2 \* 0.05}{0.05}$$

$$P(A|B)=\\frac{P(A \\bigcap B)}{P(B)}$$

$$P(Spam|Word)=\\frac{P(Word|Spam)\*P(Spam)}{P(Word)}= \\frac{0.2 \* 0.05}{0.05}$$

Para calcular los componentes del Teorema de bayes tenemos que construir
una tabla de frecuencias que nos dice el número de veces que esa palabra
aparece en Spam y en non-Spam. Será como una tabla cruzada en un eje
indicaremos si el correo es o no Spam y en el otro eje si está la
palabra o no.

Esta tabla de frecuencias puede servirnos para calcular la tabla de
Probabilidades:
