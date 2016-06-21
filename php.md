# PHP
## General Knowledge

1. Explain what the modulus operator does. 
	* Answer: The modulus operator returns the remainder from integer division. 
	* Examples:

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
2. What does the expression `12^9` mean?
	* Answer: The `^` symbol is a bitwise operator, allowing evaluation and manipulation of specific bits within an integer. Everything that exists in one but not both. 12 is made up of 8 and 4. 9 is made up of 9 and 1. 8 exists in both, but 1 and 4 exist in one but not both.

```
<?php
$x = 12^9;
print $x; //output 5
?>

```
3. Explain the difference between the "==" operator and the "===" operator.
	* Answer: The Equal operator returns true if `$x` is equal to `$y`. The Identical operator returns true if `$x` is equal to `$y`, and they are of the same type. Both are comparison operators. The `===` operator can be used to distinguish boolean from non-boolean values.

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


###### Regular Assignment vs. Assigning by reference

Within a regular assignment, the left operand gets set the value of the assignment of the expression on the right, whereas assignment by reference points the left and right operand to the same place.

PHP Syntax:`$a = $b`
* $a is pointing to $b

PHP Syntax:`$a =& $b`
* $a is not pointing to $b or vice versa.
* $a and $b are pointing the same place

Explain how to pass a variable by reference to a function.

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
###### foreach loop vs. for loop within an associative array

* Access: numerical / associative
* Numerical: PHP handles the location numbers / each time a value is assigned to the array, the first empty location within the array is used to store the value
* Associative: Reference the items in the array by name rather than by number / give each element in the array an identifying name and explanatory string value
* Names (Alejandro, Andea) are called *indexes or keys*
* Item are called *values*
* **index => value** format

```
<?php
$friends = array('Alejandro', 'Andrea', 'Emma', 'Kate', 'Sean',);
	echo "<h1>FRIENDS</h1>";
for ($i = 0 ; $i < 5 ; ++$i)
	echo "<br>$i: $friends[$i]<br>";
?>
```	
```
<?php
echo "<br>";
$artfriends = array('Emma' => "Bridgeport",
                 'Alejandro' => "Spain",
                 'Kate' => "Denver",
                 'Andrea' => "Cicero",
                 'Sean' => "Quincy");

foreach ($artfriends as $name => $city)
        echo "$name lives in $city!<br>";

?>
```
###### Test Your Knowledge
   Explain why you would use a foreach loop instead of a for loop, when using data in an associative array.   
   Answer : I would use a foreach loop instead of a for loop to create a loop that extracts values to the variables, since associative arrays contain items referenced by name using the index => value format and they do not require numeric indexing.
   


