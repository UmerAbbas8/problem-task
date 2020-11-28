### Problem solving

## Problem Statement
Given a string str consisting of letters only and an integer n, the task is to replace every character of the given string by a character which is n times more than it. If the letter exceeds ‘z’, then start checking from ‘a’ in a cyclic manner.

Examples:
Input: `str = “abc”, n = 2`
Output:`cde`
a is moved by 2 times which results in character c
b is moved by 2 times which results in character d
c is moved by 2 times which results in character e

Input: `str = “abc”, n= 28`
Output: `cde`
a is moved 25 times, z is reached. Then the 26th character will be a, 27th b and 28th c.
b is moved 24 times, z is reached. 28-th is b.
c is moved 23 times, z is reached. 28-th is e.

## Question: 
A. Write an algorithm to solve the above issue. Please consider the complexity of the algorithm.

## Solution (Algo)

1. get all the possible values
2. string under considration
3. shift values
4. take sum of position of the character position value in the string and the shift value then take modulus of the result with sum of total possible number of value to get the position of shift character value in the array list.
5. repeat for all the charater position values in the string under considration.

## Solution (php Code)
```php
$alphabet_str = "abcdefghijklmnopqrstuvwxyz";
$alphabet_arr = str_split($alphabet_str);
$alphabet_arr_count = count($alphabet_arr);

$n = 3;
$str = "abc";
$str_arr = str_split($str);

foreach($str_arr as $key=>$val){
    $replace_with = (($key + $n) % $alphabet_arr_count);    
    echo $alphabet_arr[$replace_with];
}
```

## Question: 
B. What is the disadvantage of using the ASCII value of the letters to solve this problem?

## Solution
Although this porblem can be solved by ASCII values too, but if we use ASCII values then we are limited to use ASCII characters only for this algo. if we use position based apporach we can put anyhting in that list and still get a desired result form our Algo.



