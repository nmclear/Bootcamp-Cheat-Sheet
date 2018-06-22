# __*Get Accustomed with Arrays*__
[Array Method Guide](https://www.w3schools.com/jsref/jsref_obj_array.asp)

## **Converting Arrays to Strings**
* **toString()** - converts array to a string of array values separated by commas.
* **join()** - joins all array elements into a string.
    * Behaves similar to toString(), but you can **specify** the **separator**
        * insert desired separator as a parameter.
        * Inserting **blank quotes** joins character after character with **no space or comma between**.
    * Default separator is a **comma**.


## **Removing Elements from Arrays**
* **pop()** method - **removes** the **last** element from an array.
    * pop() returns the value that was popped out.
    * Remove - **pop** items **off**
* **shift()** method - **removes** the **first** element from an array.
    * Remove - **shift** items **out**
    * All other **elements** are **shifted** to a **lower index**.
    * shift() returns the string that was shifted out.
* See splicing section..


## **Adding Elements to Arrays**
* **push()** method **adds** a new element to the **end** of an array.
    * Add - **push** items **in**
    * push() returns the new array length.
* **unshift()** method **adds** a new element to the **start** of an array.
    * All other **elements** are 'unshifted' to a **higher index**.
    * unshift() returns the new array length.
* Use the **length property** to **append** a new **element**.
    * Example:
        * var sports = ["Football", "Basketball", "Soccer"]
        * sports[sports.length] = "Baseball"
        * now the array will be ["Football", "Basketball", "Soccer", "Baseball"]
* See splicing section..


## **Changing Elements in Arrays**
* **Elements** can be changed by **accessing** their **index** number and setting the new desired value.
    * Example:
        * var sports = ["Football", "Basketball", "Soccer"]
        * sports[2] = "Futbol"
        * now the array will be ["Football", "Basketball", "Futbol"]

## **Splicing Multitool**
* **splice()** can be used to add new items to an array and can remove elements in the array.
* **First parameter** defines the position **where** the new elements should be **added**.
* **Second parameter** defines **how many** elements should be **removed** to make space for addition.
* **Remaining parameters** define new **elements added**.
    * Addition Example:
        * var sports = ["Football", "Basketball", "Soccer"]
        * sports.splice(2,0, "Baseball");
        * now the array will be ["Football", "Basketball", "Baseball", "Soccer"]
    * Removal Example:
        * var sports = ["Football", "Basketball", "Soccer"]
        * sports.splice(0,1);
        * now the array will be ["Basketball", "Soccer"]
    * Combo Example:
        * var sports = ["Football", "Basketball", "Soccer", "Hockey"]
        * sports.splice(2,1, "Baseball"); (replaces 1 element at 2nd index)
        * now the array will be ["Football", "Basketball", "Baseball", "Hockey"]

## **Merging Arrays**
* **concat()** - method **creates new** array **by** merging **existing arrays**.
* concat() method can take **any number** of array arguments.
    * var newArr = firstArr.concat(secArr);
    * var newArr = firstArr.concat(secArr, thirdArr);
    * var newArr = firstArr.concat(secArr, thirdArr, fourthArr);
* concat() method can take **values** as **arguments**.
    var firstArr = ["New York", "LA"];
    var newArr = firstArr.concat(["Chicago", "DC", "San Fran"]);

## **Slicing an Array**
* **slice()** method slices **out** a **piece** of an array **into** a **new array**.
* slice method creates a new array, it does not remove any elements from the source array.
* slice(start, end) method can take two arguments:
    * **first** argument - where to **start** slice
    * **second** argument - where to **end** slice, but **not** including **end argument**.
    * if **end** argument is **omitted**, slice() **slices out** the **remaining** array.

## **Sort / Reverse Arrays**
* **sort()** method sorts array elements **alphabetically**.
    * Sorts strings values as string by default.
    * If array of numbers, sort() alone will not work.
* **reverse()** method reverse the elements in an array.
* **Combine** reverse() with sort() to **sort** an array in **descending** order.
    * arr.sort(); then arr.reverse();

## **Numeric Sort**
* Add a compare function to fix numerical sort issue.
* **Ascending** Sort:
    * arr.sort(function(a,b){
        return a-b;
    })
* **Descending** Sort:
    * arr.sort(function(a,b){
        return b-a;
    })
* **Compare function** will return a negative, zero, or positive value depending on arguments.
    * After arguments are compared via function, array elements sorted by return values.

## **Random Order Sort**
* arr.sort(function(a,b){
    return 0.5 - Math.random()
});

## **Highest - Lowest Array Value**
* There are no built-in functions for finding the max or min, but you can **sort** the **array** then **find** the values via **indecies**.
    * arr.sort(function(a,b){
        return a-b;
    })
    * var maxValue = arr[arr.length - 1]
    * var minValue = arr[0]
* Sorting a whole array is inefficient if you only want the min or max.
* **Math.max().apply** - finds highest number in array.
    * function maxValArr(arr) {
        return Math.max.apply(null, arr);
    }
* **Math.min().apply** - finds lowest number in array.
    * function minValArr(arr) {
        return Math.min.apply(null, arr);
    }