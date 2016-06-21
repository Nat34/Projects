# PHP
## General Knowledge

#### 1. Explain what the modulus operator does. 

The modulus operator returns the remainder from integer division. 

**Examples**

```
<?php
  for ($i = 1; $i <= 10; $i++) {
    if(($i % 2) == 1)  //odd
      {echo "<div class=\"dark\">$i</div>";}
    else   //even
      {echo "<div class=\"light\">$i</div>";}
   }
?>
```
```
<?php

$fizz = "Fizz";
$buzz = "Buzz";
$fizzbuzz = "FizzBuzz";

for ($i = 1; $i <= 100; ++$i) {         
  if ($i%3 === 0 && $i%5 === 0) {      
         echo "<p>" . $fizzbuzz . "</p>";
    } else if ($i%3 === 0) { 
         echo "<p>" . $fizz . "</p>";
    } else if ($i%5 === 0) { 
         echo "<p>" . $buzz . "</p>";
    } else { 
         echo "<p>" . $i . "</p>";}
}
?>
```
### 2. What does the expression `12^9` mean?

The `^` symbol is a bitwise operator, allowing evaluation and manipulation of specific bits within an integer. Everything that exists in one but not both. 12 is made up of 8 and 4. 9 is made up of 9 and 1. 8 exists in both, but 1 and 4 exist in one but not both.

**Example**

```
<?php
$x = 12^9;
print $x; //output 5
?>

```
### 3. Explain the difference between the "==" operator and the "===" operator.

The Equal operator returns true if `$x` is equal to `$y`. The Identical operator returns true if `$x` is equal to `$y`, and they are of the same type. Both are comparison operators. The `===` operator can be used to distinguish boolean from non-boolean values.

**Example**

```
<?php

$x = 3;
$y = "3";

if ($x == $y) {
    echo 'true.</br>';
} else {
    echo 'false.';
}

if ($x === $y) {
    echo 'true.';
} else {
    echo 'false.';
}
?>
```


### 4. Explain the basic difference between a regular assignment, and assigning by reference. 

Within a regular assignment, the left operand gets set the value of the assignment of the expression on the right, whereas assignment by reference points the left and right operand to the same place.

**Example**

`$x = $y`
* $x is pointing to $y

`$x =& $y`
* $x is not pointing to $y or vice versa.
* $x and $y are pointing the same place

	* Explain how to pass a variable by reference to a function.

To pass a variable by reference to a function

1. Declare the function by giving the function  a name that reflects what the function does
2. Specify the variable after the function name, inside the parentheses with the reference sign on the variable.  

```
function functionName(&$a) {
    code to be executed;
}
```

To call the function, just write its name:

```
<?php
function writeMsg() {
    echo "Hello world!";
}

writeMsg(); // call the function
?>
```
### 5. Explain why you would use a `foreach` loop instead of a `for` loop, when using data in an associative array.

The conversation here is between numerical vs. associative.  In an associative array PHP references the items in the array by name rather than by number. You give each element in the array an identifying name and explanatory string value.  I would use a `foreach` loop instead of a `for` loop to create a loop that extracts values to the variables, since associative arrays contain items referenced by name using the **index => value** format and they do not require numeric indexing.

**Examples**

```
<?php
$friends = array('Alejandro', 'Andrea', 'Emma', 'Kate', 'Sean',);
	echo "<h1>FRIENDS</h1>";
for ($i = 0 ; $i <= 4 ; ++$i)
	echo "<br>$i: $friends[$i]<br>";
?>
```	
```
<?php
echo "<br>";
$myfriends = array('Emma' => "Bridgeport",
                 'Alejandro' => "Spain",
                 'Kate' => "Denver",
                 'Andrea' => "Cicero",
                 'Sean' => "Quincy");

foreach ($myfriends as $name => $city)
        echo "$name lives in $city!<br>";

?>
```
### 6. Describe an example of when omitting a break from a switch case would be helpful.

Omitting a break from a switch means you would not exit the control structure, but it seems to be the default behavior to end each switch with a break. Perhaps omitting the break could be helpful if you want to run multiple case statements.

### 7. Explain the difference between public, private, and protected for class properties and methods.
	* Public: any code could directly access and change the values for these class properties and methods
	* Private: class properties and methods cannot be accessed outside of the class itself
	* Protected: class properities and methods can be accessed within the class itself and by inherited classes
	* var: treated as public
### 8. Explain what it means to define a method as abstract.

Defining a method as abtract means to modify the properties after inheritance.

**Example**

**When is it helpful**

### 9. Explain what it means to define a method as static.


### 10. Explain what it means to define a method as final

### 11. When running PHP from the command line, describe how to access command input data inside the script.

### 12. When fetching content with an HTTP request, describe how to get header information from the response.


