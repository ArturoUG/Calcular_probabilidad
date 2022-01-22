# Calcular_probabilidad
Certificación

Español

Supongamos que hay un sombrero que contiene 5 bolas azules, 4 bolas rojas y 2 bolas verdes. ¿Cuál es la probabilidad de que un sorteo aleatorio de 4 bolas contenga al menos 1 bola roja y 2 bolas verdes? Si bien sería posible calcular la probabilidad usando matemáticas avanzadas, una forma más fácil es escribir un programa para realizar una gran cantidad de experimentos para estimar una probabilidad aproximada.

Para este proyecto, escribirás un programa para determinar la probabilidad aproximada de sacar ciertas bolas al azar de un sombrero.

Primero, cree una clase Hat en prob_calculator.py. La clase debe tomar un número variable de argumentos que especifiquen el número de bolas de cada color que hay en el sombrero. Por ejemplo, un objeto de clase podría crearse de cualquiera de estas formas:

hat1 = Hat(yellow=3, blue=2, green=6)
hat2 = Hat(red=5, orange=4)
hat3 = Hat(red=5, orange=4, black=1, blue=0, pink=2, striped=9)

Un sombrero siempre se creará con al menos una bola. Los argumentos pasados ​​al objeto hat al momento de la creación deben convertirse en una variable de instancia de contenido. el contenido debe ser una lista de cadenas que contengan un artículo para cada bola en el sombrero. Cada elemento de la lista debe ser un nombre de color que represente una sola bola de ese color. Por ejemplo, si su sombrero es {"rojo": 2, "azul": 1}, el contenido debe ser ["rojo", "rojo", "azul"].

La clase Sombrero debe tener un método de sorteo que acepte un argumento que indique el número de bolas que se sacarán del sombrero. Este método debería eliminar las bolas al azar del contenido y devolver esas bolas como una lista de cadenas. Las bolas no deben volver al sombrero durante el sorteo, similar a un experimento de urna sin reemplazo. Si el número de bolas a sacar excede la cantidad disponible, devolver todas las bolas.

A continuación, cree una función de experimento en prob_calculator.py (no dentro de la clase Hat). Esta función debe aceptar los siguientes argumentos:

sombrero: un objeto sombrero que contiene bolas que debe copiarse dentro de la función.
bolas_esperadas: un objeto que indica el grupo exacto de bolas que se intentará sacar del sombrero para el experimento. Por ejemplo, para determinar la probabilidad de sacar 2 bolas azules y 1 bola roja del sombrero, establezca bolas_esperadas en {"azul":2, "roja":1}.
num_balls_drawn: El número de bolas a sacar del sombrero en cada experimento.
num_experiments: El número de experimentos a realizar. (Cuantos más experimentos se realicen, más precisa será la probabilidad aproximada).
La función de experimento debe devolver una probabilidad.

Por ejemplo, supongamos que desea determinar la probabilidad de obtener al menos 2 bolas rojas y 1 bola verde cuando saca 5 bolas de un sombrero que contiene 6 negras, 4 rojas y 3 verdes. Para hacer esto, realizamos N experimentos, contamos cuántas veces M obtenemos al menos 2 bolas rojas y 1 bola verde, y estimamos la probabilidad como M/N. Cada experimento consiste en comenzar con un sombrero que contiene las bolas especificadas, sacar una cantidad de bolas y verificar si obtuvimos las bolas que estábamos tratando de sacar.

Así es como llamaría a la función de experimento según el ejemplo anterior con 2000 experimentos:

hat = Hat(black=6, red=4, green=3)
probability = experiment(hat=hat, 
                  expected_balls={"red":2,"green":1},
                  num_balls_drawn=5,
                  num_experiments=2000)
                  
Dado que esto se basa en sorteos aleatorios, la probabilidad será ligeramente diferente cada vez que se ejecute el código.

Sugerencia: considere usar los módulos que ya están importados en la parte superior de prob_calculator.py.

Desarrollo

Escribe tu código en prob_calculator.py. Para el desarrollo, puede usar main.py para probar su código. Haga clic en el botón "ejecutar" y main.py se ejecutará.

Pruebas

Las pruebas unitarias para este proyecto están en test_module.py. Importamos las pruebas de test_module.py a main.py para su comodidad. Las pruebas se ejecutarán automáticamente cada vez que presione el botón "ejecutar".




Ingles

Assignment

Suppose there is a hat containing 5 blue balls, 4 red balls, and 2 green balls. What is the probability that a random draw of 4 balls will contain at least 1 red ball and 2 green balls? While it would be possible to calculate the probability using advanced mathematics, an easier way is to write a program to perform a large number of experiments to estimate an approximate probability.

For this project, you will write a program to determine the approximate probability of drawing certain balls randomly from a hat.

First, create a Hat class in prob_calculator.py. The class should take a variable number of arguments that specify the number of balls of each color that are in the hat. For example, a class object could be created in any of these ways:

hat1 = Hat(yellow=3, blue=2, green=6)
hat2 = Hat(red=5, orange=4)
hat3 = Hat(red=5, orange=4, black=1, blue=0, pink=2, striped=9)
A hat will always be created with at least one ball. The arguments passed into the hat object upon creation should be converted to a contents instance variable. contents should be a list of strings containing one item for each ball in the hat. Each item in the list should be a color name representing a single ball of that color. For example, if your hat is {"red": 2, "blue": 1}, contents should be ["red", "red", "blue"].

The Hat class should have a draw method that accepts an argument indicating the number of balls to draw from the hat. This method should remove balls at random from contents and return those balls as a list of strings. The balls should not go back into the hat during the draw, similar to an urn experiment without replacement. If the number of balls to draw exceeds the available quantity, return all the balls.

Next, create an experiment function in prob_calculator.py (not inside the Hat class). This function should accept the following arguments:

hat: A hat object containing balls that should be copied inside the function.
expected_balls: An object indicating the exact group of balls to attempt to draw from the hat for the experiment. For example, to determine the probability of drawing 2 blue balls and 1 red ball from the hat, set expected_balls to {"blue":2, "red":1}.
num_balls_drawn: The number of balls to draw out of the hat in each experiment.
num_experiments: The number of experiments to perform. (The more experiments performed, the more accurate the approximate probability will be.)
The experiment function should return a probability.

For example, let's say that you want to determine the probability of getting at least 2 red balls and 1 green ball when you draw 5 balls from from a hat containing 6 black, 4 red, and 3 green. To do this, we perform N experiments, count how many times M we get at least 2 red balls and 1 green ball, and estimate the probability as M/N. Each experiment consists of starting with a hat containing the specified balls, drawing a number of balls, and checking if we got the balls we were attempting to draw.

Here is how you would call the experiment function based on the example above with 2000 experiments:

hat = Hat(black=6, red=4, green=3)
probability = experiment(hat=hat, 
                  expected_balls={"red":2,"green":1},
                  num_balls_drawn=5,
                  num_experiments=2000)
Since this is based on random draws, the probability will be slightly different each time the code is run.

Hint: Consider using the modules that are already imported at the top of prob_calculator.py.

Development

Write your code in prob_calculator.py. For development, you can use main.py to test your code. Click the "run" button and main.py will run.

Testing

The unit tests for this project are in test_module.py. We imported the tests from test_module.py to main.py for your convenience. The tests will run automatically whenever you hit the "run" button.

