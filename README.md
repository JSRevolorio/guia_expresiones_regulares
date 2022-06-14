
```diff
+ Green
- Red
! Orange
```

<style>
b { color: Blue }
r { color: red }
g { color: Green }
</style>

[<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--xNN3N2qj--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lfeb29tti4oe0efwgu65.jpeg" width="600" height="200" />](dedde)

# Guía de expresiones regulares

## Expresiones regulares
Las expresiones regulares son patrones utilizados para encontrar una determinada combinación de caracteres dentro de una cadena de texto. Las expresiones regulares proporcionan una manera muy flexible de buscar o reconocer cadenas de texto.

<br/>

### *Que podemos hacer con las expresiones regulares?*

+ **Encontrar (Find):** Realiza una búsqueda de un patrón dentro de una cadena de caracteres.
+ **Remplazar (Replace):** Realiza un remplazo de un patrón dentro de una cadena de caracteres.
+ **Separar (Split):** Realiza una separación de una cadena de caracteres de acuerdo con un patrón.  
+ **Contar (Count):** Realiza el conteo de las coincidencias del patrón encontradas en la cadena de caracteress.
+ **Posición (Position):** Muestra la posición de la coincidencia del patrón en una cadena caracteres.

<br/>
<br/>

[<img src="https://i.ibb.co/d4DVvrH/Partes-de-Regex.png" width="600" height="250" />](dedde)

## Sintaxis de expresiones regulares
La expresión regular es una cadena de texto, compuesta por delimitadores, patrones y modificadores opcionales.
 **Ejemplo:** `/patrón/modificadores`

|                   |                     |
|-------------------|---------------------|
| Patrón (Pattern)|	El elemento central es el patrón, esto es, el patrón de búsqueda general. Se formar a partir de caracteres simples o a partir de una combinación de caracteres simples y especiales .|
|Delimitador (Delimiter)|	El inicio y el final del patrón se identifican con delimitadores. Los delimitadores son, básicamente, todos los caracteres no alfanuméricos (excepto la barra diagonal inversa). Por ejemplo, para PHP las almohadillas (#pattern#), los signos de porcentaje (%pattern%), el signo más (+pattern+) o las tildes (~pattern~) son delimitadores. La mayoría de lenguajes ya usan las comillas (“pattern”) o las barras diagonales (/pattern/).|
|Modificador (Modifier)	|Los modificadores pueden añadirse a un patrón de búsqueda para modificar la expresión regular. Un ejemplo es el modificador i, el cual anula la distinción entre mayúsculas y minúsculas. Garantiza que las mayúsculas y las minúsculas se tienen en consideración y que valen por defecto para todas las expresiones regulares.|
<br/>

<br/>
<br/>

## Regular Expressions Cheat Sheet
#
<br/>

## Grupo y rango de caracteres

| Metacarácter   | Descripción|
| ---------------|------------|
| **`[0-9]`**   |Encuentra un digito entre el **0** y el **9**.|
| **`[a-z]`**   |Encuentra un carácter entre la **a** y la **z** en minúscula.|
| **`[A-Z]`**   |Encuentra un carácter entre la **A** y la **Z** en mayúscula.|
| **`[a-zA-Z]`**|Encuentra un carácter ya sea minúscula o mayúscula del abecedario|
| **`(a\|b)`**  |Encuentra un carácter entre a o b o ambos ab |
| **`[À-ÿ]`**   |Encuentra un carácter con tilde o diéresis| 
| **`[^a-z]`**  |Encuentra un carácter que no este dentro del abecedario.|
| **`[!a-z]`**  |Encuentra un carácter ya sea minúscula o mayúscula del abecedario|
| **`[^]`**     |El circunflejo ( ^ ) dentro de conchetes es negación como ( ! ) en programación|
| **`[!]`**     |El signo de exclamación ( ! ) dentro de corchetes hacen insensible a minúscula o mayúsculas la expresión|
<br/>

## Clases predefinidas de caracteres

| Metacarácter|Descripción|Equivalente|
| ------------|-----------|-----------|
| **`\s`**      |Encuentra un espacio en blanco. |*`[ ]`* |
| **`\S`**      |Encuentra cualquier carácter que **no** es un espacio en blanco. |*`[^\t\r\n]`* |
| **`\d`**      |Encuentra un digito o un carácter numérico. |*`[0-9]`* |
| **`\D`**      |Encuentra cualquier carácter que **no** es un digito. |*`[^0-9]`* |
| **`\w`**      |Encuentra cualquier carácter alfanumérico incluido el guion bajo ( _ )|*`[a-zA-Z0-9_]`*|
| **`\W  `**      |Encuentra cualquier carácter **no** alfanumérico|*`[^a-zA-z0-9_]`* |
| **`\b`**      |Encuentra la coincidencia la inicio o final de la *palabra*. **Ejemplo:** **`\bpo`** o **`on\b`** |*`po`siti`on`* al inicio o final de la *palabra* |
| **`\B`**      |Encuentra la coincidencia entre la palabra. **Ejemplo:** **`\Bnumer`** |*alfa`numer`ico* se Encuentra entre la palabra |
| **`\x  `**      |Encuentra un carácter ASCII o ANSI especificado por un numero hexadecimal. **Ejemplo:** **`\xA9`**|*`©`* carácter que representa *`\xA9`* |
| **`\u`**      |Encuentra un carácter unicode especificado por su código. **Ejemplo:** **`\u00D8`** |*`Ø`* carácter que representa *`\u00D8`* |
| **`\0`**      |Encuentra un carácter null o nul. | *`NULL`*|
| **`.`**       |Encuentra cualquier carácter excepto salto de línea. |*`[\w\D]`* |
<br/>


## Cuantificadores

### **Greedy** (Codicioso)
Tantos como sea posible (*coincidencia más larga*)
De forma predeterminada, un cuantificador le dice al motor que coincida con tantas instancias de su token cuantificado o subpatrón como sea posible. Este comportamiento se llama codicioso .
<br/>

### **Lazy** (Perezoso)
Tan pocos como sea posible (*coincidencia más corta*)
En contraste con el cuantificador codicioso estándar, que consume la mayor cantidad posible de instancias del token cuantificado, un cuantificador perezoso (a veces llamado reacio ) le dice al motor que coincida con la menorde los tokens cuantificados según sea necesario.

|Greedy	     |Lazy	    |Descripción |
|------------|----------|------------|
|**`*`**    |\*?	    |0 o más veces|
|**`+`**    |+?	    |1 o más veces|
|**`?`**    |??	    |0 o 1 veces|
|**`{n}`**  |{n}?	    |n veces|
|**`{n,}`** |{n,}?	    |n o más veces|
|**`{n,m}`**|{n,m}?	|De n a m veces|

<br/>

## Anclas

|Metacarácter|Descripción |	    
|------------|------------|
|**`^`**    |Encuentra la coincidencia la inicio de una **linea** de texto. **Ejemplo:** *`^[ab]`*	encuentra la linea que inicia con a o b|
|**`$`**    |Encuentra la coincidencia la final de una **linea** de texto. **Ejemplo:** *`[ab]$`* encuentra la linea que finaliza con a o b |
|**`\A`**   |Comienzo de una cadena de texto (string). Nunca final de línea.|
|**`\Z`**   |Fin de cadena de texto (string). Nunca final de línea.|
|**`\\<`**   |Comienzo de una palabra|
|**`\\>`**   |Fin de una palabra|
<br/>

## Patrón Modificador

Modificadores	Descripción
i	Insensible a las mayúsculas y minúsculas Wstar (case insensitive)
g	Busqueda global (global match)
m	Busqueda en multiples líneas de texto. (Multiple lines)
s	Incluye saltos de línea. Sin él, las nuevas líneas son excluidas.
<br/>





1. Modificadores (Pattern Modifi)
2. Metacarateres basicos
7. Retroferencias
8. Declaraciones (Assetion)
9. Posix
12. Escape sequences
13. string Replacement
10. Comodines Unicode
11. Utiles
