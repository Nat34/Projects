# Setting Up a Development Server


This folder contains practice files.  These files are created while learning to setup a development server.

## Project: 
To setup a development server

## Drivers:
Testing is fast, errors or security problems are kept local

## Technology: 
LAMP(Linux, Apache, MySQL, and PHP)

## Resources: 
Learning PHP, MySQL, JavaScript, and CSS text, Mozilla Developer Network (MDN), 

## Task List

My First Inter*active* App
- [ ] Installing LAMP

## Examples:

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
