[<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--xNN3N2qj--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lfeb29tti4oe0efwgu65.jpeg" width="600" height="200" />](dedde)

# Guía de expresiones regulares

### Expresiones regulares
<p style="text-align: justify;">
Las expresiones regulares son patrones utilizados para encontrar una determinada combinación de caracteres dentro de una cadena de texto, estos proporcionan una manera muy flexible de buscar o reconocer cadenas de texto. Las expresiones regulares son cadenas de caracteres basadas en reglas sintácticas que permiten describir secuencias de caracteres. Así, forman parte de los lenguajes regulares, los cuales son un subgrupo de los lenguajes formales, de gran importancia para la tecnología de la información y, especialmente, para el desarrollo de software.</p>

<br/>

### *Que podemos hacer con las expresiones regulares?*

+ **Encontrar (Find):** Realiza una búsqueda de un patrón dentro de una cadena de caracteres.
+ **Remplazar (Replace):** Realiza un remplazo de un patrón dentro de una cadena de caracteres.
+ **Separar (Split):** Realiza una separación de una cadena de caracteres de acuerdo con un patrón.  
+ **Contar (Count):** Realiza el conteo de las coincidencias del patrón encontradas en la cadena de caracteress.
+ **Posición (Position):** Muestra la posición de la coincidencia del patrón en una cadena caracteres.

<br/>



## Estructura de expresiones regulares
[<img src="https://i.ibb.co/DQs2r0K/Partes-de-Regex.png" width="600" height="250" />](dedde)
<br/>
<br/>
La expresión regular es una cadena de texto que puede estar formada por hasta tres partes (delimitadores, patrones y modificadores), independientemente del lenguaje en el que se va a utilizar.
 **Ejemplo:** `/patrón/modificadores`

|                   |                     |
|-------------------|---------------------|
| Patrón (Pattern)|	El elemento central es el patrón, esto es, el patrón de búsqueda general. Se formar a partir de caracteres simples o a partir de una combinación de caracteres simples y especiales .|
|Delimitador (Delimiter)|	El inicio y el final del patrón se identifican con delimitadores. Los delimitadores son, básicamente, todos los caracteres no alfanuméricos (excepto la barra diagonal inversa). Por ejemplo, para PHP las almohadillas `(#pattern#)`, los signos de porcentaje `(%pattern%)`, el signo más `(+pattern+)` o las tildes `(~pattern~)` son delimitadores. La mayoría de lenguajes ya usan las comillas `(“pattern”)` o las barras diagonales `(/pattern/).`|
|Modificador (Modifier)	|Los modificadores pueden añadirse a un patrón de búsqueda para modificar la expresión regular. Un ejemplo es el modificador i, el cual anula la distinción entre mayúsculas y minúsculas. Garantiza que las mayúsculas y las minúsculas se tienen en consideración y que valen por defecto para todas las expresiones regulares.|

<br/>

## Regular Expressions Cheat Sheet

### **Metacaracteres basicos**

|Metacarácter |Descripción |Ejemplo |
|-------------|------------|--------|
|**`-`**      |El guion medio define un rango o intervalo| *`0-9`* |
|**`[ ]`**    |Los corchetes contiene set de caracteres | *`[a-z0-9]`* |
|**`{ }`**    |Las llaves expresan los cuantificadores| *`{2,9}`*|
|**`( )`**    |Los paréntesis realizan agrupaciones de patrones	| *`(5[a-z])\s(6[a-z])`* |
|**`\`**      |La diagonal invertida escapa cualquier caracteres reservados| *`[\*]`* |
|**`[^]`**    |El circunflejo ( ^ ) dentro de conchetes es negación |*`[^0-9]`* |
|**`[!]`**    |El signo de exclamación ( ! ) dentro de corchetes hacen insensible a minúscula o mayúsculas   |*`[!a-z]`* |
<br/>

### **Grupo y rango de caracteres**

| Metacarácter   | Descripción|
| ---------------|------------|
| **`[0-9]`**    |Encuentra un digito entre el **0** y el **9**.|
| **`[a-z]`**    |Encuentra un carácter entre la **a** y la **z** en minúscula.|
| **`[A-Z]`**    |Encuentra un carácter entre la **A** y la **Z** en mayúscula.|
| **`[a-zA-Z]`** |Encuentra un carácter ya sea minúscula o mayúscula del abecedario|
| **`(a\|b)`**   |Encuentra un carácter entre a o b o ambos ab |
| **`[A-z]`**    |Encuentra un carácter ya sea minúscula o mayúscula del abecedario|
| **`[À-ÿ]`**    |Encuentra un carácter con tilde o diéresis| 
| **`[á-ü]`**    |Encuentra toda la vocales con tildes, circunflejo y diéresis| 
| **`[^a-z]`**   |Encuentra un carácter que no este dentro del abecedario.|
| **`[!a-z]`**   |Encuentra un carácter ya sea minúscula o mayúscula del abecedario|
<br/>

### **Clases predefinidas de caracteres**

| Metacarácter|Descripción|Equivalente|
| ------------|-----------|-----------|
| **`\s`**    |Encuentra un espacio en blanco. |*`[ ]`* |
| **`\S`**    |Encuentra cualquier carácter que **no** es un espacio en blanco. |*`[^\t\r\n]`* |
| **`\d`**    |Encuentra un digito o un carácter numérico. |*`[0-9]`* |
| **`\D`**    |Encuentra cualquier carácter que **no** es un digito. |*`[^0-9]`* |
| **`\w`**    |Encuentra cualquier carácter alfanumérico incluido el guion bajo ( _ )|*`[a-zA-Z0-9_]`*|
| **`\W  `**  |Encuentra cualquier carácter **no** alfanumérico|*`[^a-zA-z0-9_]`* |
| **`\x  `**  |Encuentra un carácter ASCII o ANSI especificado por un numero hexadecimal. **Ejemplo:** **`\xA9`**|*`©`* carácter que representa *`\xA9`* |
| **`\u`**    |Encuentra un carácter unicode especificado por su código. **Ejemplo:** **`\u00D8`** |*`Ø`* carácter que representa *`\u00D8`* |
| **`\0`**    |Encuentra un carácter null o nul. | *`NULL`*|
| **`.`**     |Encuentra cualquier carácter excepto salto de línea. |*`[\w\D]`* |
<br/>


### **Cuantificadores**

#### **Greedy** (Codicioso)
Tantos como sea posible (*coincidencia más larga*)
De forma predeterminada, un cuantificador le dice al motor que coincida con tantas instancias de su token cuantificado o subpatrón como sea posible. Este comportamiento se llama codicioso .
<br/>

#### **Lazy** (Perezoso)
Tan pocos como sea posible (*coincidencia más corta*)
En contraste con el cuantificador codicioso estándar, que consume la mayor cantidad posible de instancias del token cuantificado, un cuantificador perezoso (a veces llamado reacio ) le dice al motor que coincida con la menorde los tokens cuantificados según sea necesario.

|Greedy	     |Lazy	    |Descripción |
|------------|----------|------------|
|**`*`**    |\*?	    |0 o más veces|
|**`+`**    |+?	        |1 o más veces|
|**`?`**    |??	        |0 o 1 veces|
|**`{n}`**  |{n}?	    |n veces|
|**`{n,}`** |{n,}?	    |n o más veces|
|**`{n,m}`**|{n,m}?	    |De n a m veces|
<br/>

### **Anclas**

|Metacarácter|Descripción |	    
|------------|------------|
|**`^`**     |Encuentra la coincidencia la inicio de una **línea** de texto. **Ejemplo:** *`^[ab]`*	encuentra la línea que inicia con a o b|
|**`$`**     |Encuentra la coincidencia la final de una **línea** de texto. **Ejemplo:** *`[ab]$`* encuentra la línea que finaliza con a o b |
|**`\b`**    |Encuentra la coincidencia la inicio o final de la *palabra*. **Ejemplo:** **`\bpo`** o **`on\b`** = **po**siti**on** al inicio o final de la *palabra* | 
|**`\B`**    |Encuentra la coincidencia entre la palabra. **Ejemplo:** **`\Bnumer`** =  alfa**numer**ico se encuentra entre la palabra| 
|**`\A`**    |Comienzo de una cadena al igual que ( ^ ) para python|
|**`\Z`**    |Fin de una cadena al igual que ( $ ) para python |
|**`\<`**    |Comienzo de una cadena al igual que ( ^ ) para algunos sistemas linux|
|**`\>`**    |Fin de una cadena al igual que ( $ ) para algunos sistemas linux|
<br/>


### **Caracteres especiales**

|Metacarácter| Descripción|
|------------|------------|
|**`\t`**    |Representa un tabulador|
|**`\r`**    |Representa el retorno de carro o regreso al inicio|
|**`\n`**    |Representa una línea nueva o salto de línea|
|**`\a`**    |Representa una campana o beep que se produce al imprimir este carácter|
|**`\e`**    |Representa la tecla "Esc" o "Escape"|
|**`\f`**    |Representa un salto de página|
|**`\v`**    |Representa un tabulador vertical|
<br/>


### **Modificadores**

|Metacarácter   |Descripción |
|---------------|------------|
| **`i`**        |(insensitive) Indica que las letras del patrón pueden ser mayúsculas o minúsculas|
| **`g`**        |global) indica que los caracteres a buscar pueden  ser encontrados varias veces en la cadena de caracteres.|
| **`m`**        |multiline) Por defecto, los patrones son considerados como una única línea. Este modificador indica que el patrón es multilínea, por lo que los metacaracteres de principio y final de cadena ("^" y "$" respectivamente) también pueden indicar adicionalmente principio y final de línea|
| **`s`**        |Indica que el carácter especial punto "." puede reemplazar a cualquier carácter, incluyendo el salto de línea (por defecto, el punto no reemplaza al salto de línea)|
| **`x`**        |La busqueda permite comentarios y espacion en blaco sin escape|
| **`e`**        |Evalua la cadena para remplazo  ejemplo: *`/cadena/remplazo/e`* sistemas linux|
| **`U`**        |Indica que el patrón está codificado en UTF-8 |
<br/>

### **Posix**
Las expresiones de posix son un tipo especial de clases de caracteres. Las expresiones de corchete posix coinciden con un carácter de un conjunto de caracteres, al igual que las clases de caracteres normales. POSIX define las interfaces de programación de aplicaciones (API) a nivel de sistema y de usuario, junto con los shells de línea de comandos y las interfaces de utilidad, para la compatibilidad del software (portabilidad) con variantes de Unix y otros sistemas operativos.

|posix |Descripción        | Equivalente
|-------------|-------------------|------------|
|**`[:alpha:]`** |Caracteres alfabéticos. |*`[a-zA-Z]`*
|**`[:digit:]`** |Solo Dígitos |*`[0-9]`*
|**`[:alnum:]`** |Caracteres alfanuméricos. |*`[a-zA-Z0-9]`*
|**`[:lower:]`** |Letras minúsculas. |*`[a-z]`*
|**`[:upper:]`** |Letras mayúsculas. |*`[A-Z]`*
|**`[:word:]`**  |Letras, números y el guion bajo. |*`[A-Za-z0-9_]`*
|**`[:blank:]`** |Espacio y tabulador. |*`[\s\t]`*
|**`[:space:]`** |Espacios en blanco, incluido <br/> |*`[\t\r\n\v\f]`*
|**`[:print:]`** |Caracteres visibles y espacios (i.e: excepto los caracteres de control) |*`[\x20-\x7E]`*
|**`[:graph:]`** |Caracteres visibles (i.e: excepto espacios, caracteres de control, etc.)|*`[\x21-\x7E]`*
|**`[:xdigit:]`**|Dígitos hexadecimales |*`[A-Fa-f0-9]`*
|**`[:ascii:]`** |Caracteres ASCII |*`[\x00-\x7F]`*
|**`[:cntrl:]`** |Caracteres de control |*`[\x00-\x1F\x7F]`*
|**`[:punct:]`** |todos los caracteres de puntuación (todos los caracteres gráficos excepto letras y dígitos) |  *`[^_{}~\]\[!#$%&()*+,./:;<=>?@]`*  
|**`[:<:]`** |Inicio de una palabra. |*`\A`*
|**`[:>:]`** |Fin de una palabra |*`\Z`*
|**`[:alnum:]`** |Caracteres alfanuméricos. |*`[a-zA-Z0-9]`*
<br/>

### **referencia trasera**
**Grupos**
<br/>
Un grupo es una sección de una expresión regular encerrada entre paréntesis (). Esto se denomina comúnmente "subexpresión" y tiene dos propósitos:

+ Hace que la subexpresión sea atómica, es decir, coincidirá, fallará o se repetirá como un todo.
+ Se puede acceder a la porción de texto con la que coincidió en el resto de la expresión y el resto del programa.

Los grupos están numerados en los motores de expresiones regulares, comenzando con 1. Tradicionalmente, el número máximo de grupos es 9, pero muchas versiones modernas de expresiones regulares admiten un mayor número de grupos. 

```
(\d[a-z]{2,5})\s([a-z]{2,5})\s(\w)
      $1             $2        $3
```

Algunos tipos de expresiones regulares permiten grupos de captura con nombre . En lugar de un índice numérico, puede hacer referencia a estos grupos por su nombre
`(?<quote>['"])`


| Referencias            |         |           Descripcion  |
|--------------|---------|------------------------|
|*`$n`*        | *`\n`*  | n-ésimo grupo no pasivo. |
|*`?<name>`*   |         | Para asignar un nombre al grupo. **Ejemplo:** *`(?<quote>['"])\w+\k{quote}`*     |
|*`\k<name>`*        | *`\k{name} o \k'name'`*  | Tiene como función referenciar al grupo. **Ejemplo:**  *`(?<quote>['"])\w+\k{quote}`*|
|*`?:`*        |  | Si desea que el motor no numere un grupo, puede declararlo como no capturador. **Ejemplo:**  *`(\d{4}(?:-\d{2}){2} \d{2}:\d{2}.\d{3}) (.*)[\r\n]+\1 \2`*|
<br/>

### **Declaraciones (Assetion)**
|Caracteres | Descripción   |Ejemplo|
|-----------|---------------|-------|
|*`x(?=y)`* | **Aserción anticipada:** Coincide con "x" solo si "x" va seguida de "y".  | *`/Jack(?=Sprat)/`* reconocerá a "Jack" solo si va seguida de "Sprat".   |
|*`x(?!y)`* |**Aserción de búsqueda anticipada negativa:** reconoce la "x" solo si la "x" no va seguida de "y"   |*`/\d+(?!\.)/`* reconoce un número solo si no va seguido de un punto decimal. *`/\d+(?!\.)/.exec('3.141')`* halla el "141" pero no el "3".   |
|*`(?<=y)x`* |**Aserción de búsqueda inversa:** encontrará "x" solo si "x" está precedida por "y".   | *`/(?<=Jack)Sprat/`* reconoce a "Sprat" solo si está precedido por  "Jack" *`/(?<=Jack\|Tom)Sprat/`* empareja "Sprat" solo si está precedido por "Jack" o "Tom". Sin embargo, ni "Jack" ni "Tom" forman parte del resultado. |
|*`(?<!y)x`* |**Aserción de búsqueda inversa negativa:** Reconoce la "x" solo si "x" no está precedida por "y".| *`/(?<!-)\d+/`* encuentra un número solo si no está precedido por un signo menos. *`/(?<!-)\d+/.exec('3')`* encuentra el "3". *`/(?<!-)\d+/.exec('-3')`* no lo reconoce porque el número está precedido por el signo menos.   |
<br/>


### **Operadores Logicos y condicionales**

|Operador |  Descripción |Ejemplo|
|---------|--------------|--------|
|**`\|`** | Operador OR  | *`(x)\|(y)`* |
|**`(?(x) y)`** | Si el patron "x" es verdero entoces coincidir con "y"| *`\b(?(\d{2}-)\d{2}-\d{7}\|\d{3}-\d{2}-\d{4})\b`*  |
|**`(?(x) y\|z)`**  |Si el patron "x" es verdero entoces coincidir con "y" y si no con "z"| *`\b(\d{2}-)?(?(1)\d{7}\|\d{3}-\d{2}-\d{4})\b`*  |
|**`(?(?=x) y\|z)`**|Si el patron "x" es verdero con asercion entoces coincidir con "y" y si no con "z"    | *`\b(\d{2}-)?(?(1)\d{7}\|\d{3}-\d{2}-\d{4})\b`* |
<br/>

### **Comodines Unicode**

|Caracteres   |Descripción   |
|-------------|--------------|
|*`\p{L}`*    | letras       |
|*`\p{Ll}`*   | letras minúsculas|
|*`\p{Lu}`*   | letras mayúsculas|
|*`\p{N}`*    | números |
|*`\p{Nl}`*   | números que se representan como letras. Por ejemplo, los números romanos.|
|*`\p{P}`*    | símbolos de puntuación, como el punto, la coma, el punto y coma, los dos puntos,| comillas.|
|*`\p{M}`*    | caracteres que se combinan con otros, como los acentos, el circunflejo, la diéresis.|
|*`\p{Z}`*    | separadores no visibles, como espacios, cambios de línea. |
|*`\p{S}`*    | símbolos matemáticos, de moneda, dingbats. |
|*`\p{SM}`*   | símbolos matemáticos. |
|*`\p{Sc}`*   | símbolos de moneda. |
<br/>


### **Otros**

+ [Agrupacion Atomica](https://sodocumentation.net/regex/topic/8770/atomic-grouping)
+ [Lookahead y Lookbehind](https://sodocumentation.net/regex/topic/639/lookahead-and-lookbehind)
