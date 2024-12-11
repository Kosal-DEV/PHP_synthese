## Variable PHP
Pour déclarer une variable en PHP, il faut commencer par un symbole dollar `$`, suivi du nom de la variable. Le nom de la variable doit respecter certaines règles :
-	Il doit commencer par une lettre (a-z, A-Z) ou un underscore (`_`), mais pas par un chiffre. Par exemple, `$variable`, `$nom` et `$_nom` sont valides, mais `$1variable` ne l'est pas.
-	Il peut ensuite contenir des lettres, des chiffres (0-9) et des underscores. Par exemple, `$variable1`, `$var_1` et `$ma_variable` sont valides.
-	PHP est sensible à la casse (c'est-à-dire que $variable, $Variable, et $VARIABLE sont trois variables différentes).
PHP est un langage faiblement typé, ce qui signifie que vous n'avez pas besoin de spécifier le type de données d'une variable lors de sa déclaration. Le type est déterminé dynamiquement en fonction de la valeur que vous assignez à la variable.
## Le typage :
PHP est un langage faiblement typé. Cela signifie qu'il ne faut pas indiquer au programme le type de la variable, il est par contre capable de changé dynamiquement le typage de la variable en fonction du résultat.
```PHP
$nom = "Timothy"; //String
$age = 22; //int
$prix = 19.99; //float
$estVrai = true or false; //Boolean
$tableau = [22, 35, 59]; //array
```
- String : Une variable en `string` est un type chaine de caractère. La valeur d'une variable en `string` est obligatoirement entre guillemet `""`.
- int : Une variable en `int` est un type entier. La valeur d'une variable en `int` est obligatoirement un entier et ne dois pas être entre guillemet `""`
