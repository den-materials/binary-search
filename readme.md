<!--9:02 WDI5 -->

<!--Actually 9:05 -->

<!-- Hook: How many of you are looking to get a job in development after this class?  Today, we're going to start introducing you to common concepts in Computer Science.  While these are incredibly useful thought exercises, and will help you to grow into a great problem solver, there is a more immediate need to learn these concepts: you will see them in interviews.-->

# Binary Search

Binary search is a type of search method used to find the position of a target item in a sorted array.

``` js
function binarySearch(array, target) {
  // your code here
};

var sample = [0, 1, 3, 5, 8, 13, 21];
var target = 3;

binarySearch(sample, 3); 
// 2 (the index it is located at in the sample array)

```

The binary search algorithm begins by comparing the target value to the value of the middle element of the sorted array.

``` js
var low = 0;
var high  = array.length - 1;
var mid = Math.floor((low + high) / 2);

mid;
//  =>  3
```

If the target value is equal to the middle element's value, then the position is returned and the search is finished.

``` js
array[mid] === target // 3 === 1
// Nope, keep going
```

If the target value is less than the middle element's value, then the search continues on the lower half of the array; or if the target value is greater than the middle element's value, then the search continues on the upper half of the array.

``` js
array[mid] > target // 3 > 1
// Yep, move to lower half

array[mid] < target // 3 < 1
// Nope, you shouldn't be here
```

This process continues, eliminating half of the elements, and comparing the target value to the value of the middle element of the remaining elements - until the target value is either found (and its associated element position is returned), or until the entire array has been searched (and "not found" is returned).

[Source Wikipedia](https://en.wikipedia.org/wiki/Binary_search_algorithm)

<!--9:14 -->

## A real-life example

Searching for a name in a telephone book using [Binary Search](https://study.cs50.net/binary_search) (an awesome introduction to the concept).

<!--CFU Mimic the cs50 approach with a piece of paper with a lot of numbers on it, at each step ask students, "Now what do I do?" and rip accordingly.  -->

<!--9:19 -->

### A Few Words About Recursion:

Recursion is a technique where a function calls itself to do the same repetitive task 
on smaller versions of the original argument.

We're going to create a function to `countRecursively` which calls itself:

``` js
var countRecursively = function(num){
    console.log(num);
    if(num > 0) {
        countRecursively(num-1)
    };
};

```

For simple tasks you may be able to accomplish the same result with a `while` statement:

``` js
var countD = function(num){
    var i = 0;
    while (i < num) {
       i += 1;
       console.log(i);
    }
};

```

But for more complex tasks, recursion is a useful tool. Here is another recursive function: 

``` js
var singBottles = function(c){
  if (c > 0){
      console.log(
        c, ' bottles of beer on the wall,',
        c, ' bottles of beer! Take one down, pass it around,',
        (c-1), ' bottles of beer on the wall!'
      );
      c--;
      singBottles(c);
  } else {
      console.log("*BUUUUUUUURP!!!*");
  }
}

```

Binary search offers an excellent challenge to practice writing a recursive function.

<!--9:24 -->

## Exercise

Each student will be assigned a number. Based on their number, the students will sort themselves lowest to highest. The instructor will then act as the `mid` variable, determining which half of the students to continue navigating through in search of the target value.

After this real-life demo, students will pseudocode their plan for implementing a binary search, swap solutions with a partner from across the room, exchange feedback, and then start coding.

<!--9:30 -->
<!--WDI5 9:41 after individual pseudo-coding -->
<!--9:28 WDI4 After individual pseudo-coding-->
<!--9:33 WDI4 After squad discussion -->
<!--10:14 WDI4 After walking through solution -->

**Stretch**

1. Implement a recursive solution (instead of iterative).
1. Implement a solution for an array of names (strings).
1. Refactor the string search to alphebetize and capitalize first and last initials
1. Implement a solution that handles non-unique data sets. _No solution provided_


### Sample Data

``` js
var primeNumbers = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 
    41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97, 101, 103,
    107, 109, 113, 127, 131, 137, 139, 149, 151, 157, 163, 167, 
    173, 179, 181, 191, 193, 197, 199, 211, 223, 227, 229, 233, 
    239, 241, 251, 257, 263, 269, 271, 277, 281, 283, 293, 307, 
    311, 313, 317, 331, 337, 347, 349, 353, 359, 367, 373, 379, 
    383, 389, 397, 401, 409, 419, 421, 431, 433, 439, 443, 449, 
    457, 461, 463, 467, 479, 487, 491, 499, 503, 509, 521, 
    523, 541];

// string arrays to sort:
var months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "jul",
    "Aug", "Sept", "Oct", "Nov", "Dec"];

var codeWalkerStudents = ["Brian", "Clay", "Douglas", "Erik", "Gisella", "Guy", "Kevin", "Larry", "Merry", "Micah", "Nate"];
```

<!--WDI5 let devs run until 10:25, then break at 10:33 after solution runthrough -->
<!--WDI6 finished pseudocoding with squads around 9:40, coding until 10:30, then solution runthrough-->

## Solutions
[Solutions](solution.js)

### Further Reading (Includes sample code in Ruby and C++)

- [Big O Notation cheatsheet](http://bigocheatsheet.com/)
- [Carnegie Mellon University - Binary Search](http://www.cs.cmu.edu/~15110-f12/Unit05PtB-handout.pdf)
- [Rob Bell - beginner's guide to Big O notation](https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)

## Licensing
All content is licensed under a CC­BY­NC­SA 4.0 license.
All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
