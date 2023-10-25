# Apuntes servidor

- ### Variables
  - >`Define('name', value)`: Definir constantes
  - >**Variable variables**: permite utilizar el valor de una variable como el nombre de otra variable.<p align="center">
   <img alt="simbolos de patrones" src="imgs/variable_variables.png"></p>
   - 
- ### Bucles
  - >`for(varibale; condicion; incremento)`
  - >`while(condicion)`
  - >`do{codigo} while(condicion)`
  - >`foreach(array as value) | foreach(array as key => value)`: key se refiere a la posición _array[0]_ o al nombre en caso de ser asociativo _array['name']_ 
- ### Condicionales
  - >`if(condicion) | else(condicion) | else if(condicion)`
  - >`swith(condicion){case(value); codigo; break;}`
- ### Expresiones regulares
  - #### Funciones
    - >`preg_replace (pattern, replacement, string)`:examina la cadena en busca de coincidencias de patrón y sustituye el texto encontrado por el texto de sustitución.
    - >`preg_split(pattern, string, limite)`: Devuelve una matriz o lista de cadenas con el resultado de todas las apariciones del patrón en la cadena. Podemos especificar opcionalmente un límite de cadenas devueltas.
    - >`preg_match(pattern, string)`: comprueba si el patron y el string coincide **return bool**
  - #### Sintaxis
    - >preg_match("/^  $/", string) | ejemplo: (0[0-9] | 1[0-9] | 2[0-3], 23)
  * * *
  <p align="center">
    <img alt="simbolos de patrones" src="imgs/patterns.png">
    <img alt="sibolos 2" src="imgs/patterns2.png">
  </p>
- ### Modularizar codigo
  - Reusar codigo en diferentes sitios.
  - >`include`: inlcuye siempre (si no se puede da un aviso pero carga la pagina)
  - >`include_once`: solo incluye si no se ha incluido ya
  - >`require`: emite un error si no se ha podido incluir (no carga la pagina)
  - >`rquire_once`: igual que el anterior pero lo incluye si no ha sido incluido
- ### Text handling
  - >`trim()`: **quitar espacios** tanto delante como detras del string
  - >`number_format(number, decimals)`: muestra los decimales especificados
  - >`htmlspecialchars()`: formatea caracteres especiales a html
  - >`strtoupper()`: convierte el string a mayúsculas
  - >`strtolower()`: convierte el string a minúsculas
  - >`explode(separator, string)`: separa el string por el separador indicado **return array()**
  - >`implode(separador, array)`: junta el array en un string y los separa por el separador **return string**
  - >`strcmp(string1, string2)`: compara que string es mas largo
  - >`strlen(string)`: numero de caracteres
  - >`strpos(string, part)`: posición en la que empieza **part**(es un string)
  - >`str_replace(oldchain, newchain , string)`: reemplaza **newchain** por **oldchain** dentro del string dado
- ### Handling dates and times
  - >`time()`: da el número de segundos que han transcurrido desde el 1/1/1970
  - >`checkdate(month, day, year)`: compueba si la fecha esta bien **return bool**
  - >`date(format, date)`: obtiene una cadena de texto formateando la fecha con el formato indicado
  - > `strtotime(text)`: convierte un texto que intenta representar una fecha en una fecha determinada
- ### File handler
  - >`fopen(path)`; abre el archivo **devuelve booleano** 
  - >`fclose(path)`; cierra el archivo **devuelve booleano** 
  - >`file_exists($fichero)`; compueba si el archivo existe **devuelve booleano** 
  - >`readfile(file)`: lee un archivo entero y lo vuelca en el búfer de salida (es decir, en la página que se está generando, si estamos en una página PHP).
  - >`file('file', FILE_IGNORE_NEW_LINES)`: lee un fichero entero y devuelve un array o lista, donde en cada posición hay una línea del fichero
  - >`file_get_contents()`: lee un archivo entero y lo devuelve en un string (no en una matriz, como la anterior)
  - >`file_put_contents (file, text)`: sobreescribiendo su contenido anterior si lo tenía. para añadir se pone esto como tercer parámetro FILE_APPEND.
  - >`file_exists()`: aprende ingles si no sabes que hace esto
  - >`filesize()`: devuelve el tamaño en bytes del archivo, o FALSE si no existe
- ### Arrays
  - #### Tipos
    - >**Numerico**: la key es un numero _array[0]_
    - >**Asociativo**: la key es un string _array['name']_
    - >**Multidimensional**: tiene varias dimensiones que pueden ser tanto numericas como asociativas _array[0]['name']_  
  - #### Funciones
    - >`count(array`: cuenta el numero de elementos(values)
    - >`sort(array) | rsort(array)`: ordena arrays con elementos numericos (les cambia la key/index) _array(10, 3, 8, 1, 6)_
    - >`asort(array) | arsort(array`: ordena asociativos por el value <p align="center">
      <img alt="simbolos de patrones" src="imgs/asort.png">   </p>
    - >`ksort(array) | krsort(array)`: ordena asociativos por la key <p align="center">
      <img alt="simbolos de patrones" src="imgs/ksort.png">   </p>
    - >`usort(array, function)`: ordena un array según la función que el usuario defina como segundo parámetro.
    - >`array_filter(array, funcion_filtrado)`: devuelve un array con los elementos del array original que pasan la función de filtrado indicada.
    - >`print_r()`: para imprimir un array
- - -
>**Nota**: <=> Spaceship $x <=> $y Devuelve un entero menor, igual o mayor que cero, dependiendo de si $x es menor, igual o mayor que $y.
- - -
- ### Error management
  - >**Operador @**: se pone delante de una operación y no muestra nada en caso de error
  - >**Modificar php.ini**: _display_errors = (false, off o "0")_ (mala practica)
  - >**die() o exit;**: Ejemplo: `file_exists("file.txt") or die ("File not found");`
  - >**Uso de excepciones**: no se como explicar esto pregúntale al [Mister](https://chat.openai.com)
  