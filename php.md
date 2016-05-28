# PHP 


This folder contains practice files.  These files are created while learning PHP.

## Project: 
To setup a development server, learn a simple but powerful language

## Drivers:
Testing is fast, errors or security problems are kept local

## Technology: 
LAMP(Linux, Apache, MySQL, and PHP)

## Resources: 
Learning PHP, MySQL, JavaScript, and CSS text, Mozilla Developer Network (MDN), 

## Task List


- [x] Installing LAMP
- [x] PHP Structure
- [x] Basic Syntax
- [x] Operators, Variables, and more
- [ ] Expressions and Control Flow
- [ ] PHP Functions and Objects
- [ ] PHP Arrays

## Examples:

###### Modulus Operator

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

Use case: FizzBuzz game: Counting incrementally, print numbers 1 through 100, replacing any number divisible by three with the word "fizz", any number divisible by five with the word "buzz", and any number divisible by three AND five with the word "FizzBuzz"

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
###### 12^9

Everything that exists in one but not both
12 is made up of 8 and 4. 9 is made up of 9 and 1.
8 exists in both, but 1 and 4 exist in one but not both.

The ^ symbol is a bitwise operator, allowing evaluation and manipulation of specific bits within an integer.

```
<?php
$x = 12^9;
print $x; //output 5
?>

```
###### the "==" operator and the "===" operator

The Equal operator returns true if $x is equal to $y. The Identical operator returns true if $x is equal to $y, and they are of the same type. Both are comparison operators. 

```
$x == $y
$x === $y
```

The === operator can be used to distinguish boolean from non-boolean values.

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
```
<?php
$friends = array('Alejandro', 'Andrea', 'Emma', 'Kate', 'Sean',);
	echo "<h1>FRIENDS</h1>";
for ($i = 0 ; $i < 5 ; ++$i)
	echo "<br>$i: $friends[$i]<br>";
?>
```	



