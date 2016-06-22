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

The `^` symbol is a bitwise operator, allowing evaluation and manipulation of specific bits within an integer. Everything that exists in one but not both. 12 is made up of 8 and 4. 8 is made up of 9 and 1. 8 exists in both, but 1 and 4 exist in one but not both.

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

Passing a variable by reference to a function allows the function to modify the variable.

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

**Example: for loop**

```
<?php
$friends = array('Alejandro', 'Andrea', 'Emma', 'Kate', 'Sean',);
	echo "<h1>FRIENDS</h1>";
for ($i = 0 ; $i <= 4 ; ++$i)
	echo "<br>$i: $friends[$i]<br>";
?>
```
**Example foreach loop**

```
<?php
$myfriends = array('Emma' => "Bridgeport",
                 'Alejandro' => "Spain",
                 'Kate' => "Denver",
                 'Andrea' => "Cicero",
                 'Sean' => "Quincy");

foreach ($myfriends as $name => $city)
        echo "$name lives in $city.<br>";
?>
```

### 6. Describe an example of when omitting a break from a switch case would be helpful.

Omitting a break from a switch means you would not exit the case statement from which the break was omitted, but it seems to be the default behavior to end each switch with a break. Perhaps omitting the break could be helpful if you want to run multiple case statements sequentially.

### 7. Explain the difference between public, private, and protected for class properties and methods.

* Public: any code could directly access and change the values for these class properties and methods
* Private: class properties and methods cannot be accessed outside of the class itself
* Protected: class properities and methods can be accessed within the class itself and by inherited classes
* var: treated as public

### 8. Explain what it means to define a method as abstract.

Defining a method as abstract means to implement the method outside of the abstract class, where it can also be modified.  If you have an `abstract class Man` and an `abstract public function Run()` you could implement the abstract function `Run()` in a more specific child class, `class Nathan extends Man`. In the context of OOP PHP it could help the programmer follow good coding standards.

### 9. Explain what it means to define a method as static.

PHP OOP views a static attribute as shared by every object and can be called using the object reference operator `::`. It does not require instantiation. If you had a `class Man` and created a method `static function Run();` you could call it using `echo Man::run();`  Creating a static method could be useful if you know the value is not going to change.

### 10. Explain what it means to define a method as final.

A final attribute is constant and methods within extended classes of the parent class cannnot override the method with a final attribute.

### 11. When running PHP from the command line, describe how to access command input data inside the script.

Usage syntax looks like this `php <file> [--] [args...]`

### 12. When fetching content with an HTTP request, describe how to get header information from the response.

The `get_headers` URL function fetches header information

## Code Examples
```
$fruit_counts=array('apple'=>3, 'banana'=>4, 'orange'=>0);
$fruit_colors=array('apple'=>'red', 'banana'=>'yellow', 'orange'=>'orange', 'plum'=>'purple');

foreach ($fruit_colors as $fruit => $color) {
	if (isset($fruit_counts[$fruit])) {
		$fruit_counts[$fruit] = $fruit_counts[$fruit] + 1;
	} else {
		$fruit_counts[$fruit] = 1;
	}
}

$fruitStore = array();

foreach ($fruit_counts as $fruit => $count) {
	$fruitStore[] = "There are {$count} {$fruit_colors[$fruit]} {$fruit}s.</br>";
```
It helps me to try and explain what is going on here. I also really enjoy writing it out.  The `foreach` construct is iterating over the `$fruit_colors` array.  On each iteration, the value of the current element (first iteration = 'apple') is assigned to $value (first iteration = 'red.'). 

Now, the statement to be executed is an `ifelse` statement. Why this control structure? We want something to happen if a certain condition is met, and something different if the condition is not met.  In this instance, we want to add a fruit of each color and we must take into account that `'plum'=>'purple'` is null, therefore the expression evaluated is *if $fruit_counts is set* (`isset` determines if a variable is set and not null in the fruit_counts index).  When this expression evaluates **TRUE** the code to execute is an arithmetic operation of `$fruit_counts[$fruit] + 1` and sets `$fruit_counts[$fruit]` a new value.  We are using the array access operator `[]` to specify a location within an array, pointing to `$fruit`.  When this expression evaluates **FALSE** the code to execute is the assignment of a value to the `$fruit_counts[$fruit]` that is not set. In this instance `'plum'=>'purple'`. 

Moving along, initialize an array `$fruitStore = array();` and iterate over the array using a `foreach` construct, because we want to output a string describing the color and new amount(count) of *each* fruit. The variable here is `$fruit_counts` the `$key` is `$fruit` and `$value` is `$count`. The code to be executed uses the array access operator `[]` and '{}' curly braces for defining inital values in array declarations. The output is a string first accessing the new {$count} value, then accessing the color of the fruit and then name of the fruit.


