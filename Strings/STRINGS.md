
# __*Know Thy Strings*__
[String Method Guide](https://www.w3schools.com/js/js_string_methods.asp)
### **Finding String Characters**
* **indexOf()** - returns the index of the first occurrence of a specified text in a string.
* **lastIndexOf()** - returns the index of the last occurrence of a specified text in a string.
    * You can add a **second paramter** as the **starting position** of each search.
        * Ex - string.indexOf("b", 4) - starts search for b at index 4.
* If the text is not found in the string, both **indexOf** and **lastIndexOf** will **return -1**.

### **Extracting String Parts**
* There are 3 methods for extracting part of a string:
    * **slice(start,end)**
    * **substring(start,end)**
    * **substr(start,length)**
* **slice()** - extract part of a string and returns the extracted part in a new string.
    * Two parameters: **starting index** and **ending index**.
        * If the parameters are **negative**, the position is counted from the **end of the string**.
        * If you **omit** the second parameter, the method will **slice out** the **rest** of the string.
* **substring()** - **cannot** accept **negative** indexes, otherwise functions the same as slice.
* **substr()** - same as slice but the **second parameter** specifies the **length** of the extracted part.

### **Replacing String Content**
* Use the **replace()** method to **replace** an **existing** value in a string with a **specified** value.
    * replace(existing, new)
* The replace method returns a **new string**. (Does **not** change **original** string!)
    * Example:
        * str = "I hope you have a bad day.";
        * var newStr = str.replace("bad", "good");
        * newStr = "I hope you have a good day."
* Case **insensitive** replacement:
    * Use a regular expression with an **/i** flag
    * var newStr = str.replace(/bad/i, "good");
* Replace **all** matches with **global** match:
    * var newStr = str.replace(/bad/g, "good");

### **Text Transformations**
* str.**toUpperCase()** - transforms all characters to uppercase.
* str.**toLowerCase()** - transforms all characters to lowercase.
* Capitalize **first letter** of a **string**: use **charAt()** and **toUpperCase()**, and **slice()**.
<pre>function capitalizeFirstLetter(string){
        var upperFirstLet = string.charAt(0).toUpperCase() + string.slice(1);
    }
</pre>

### **Joining Strings**
* The **concat()** method **joins** two or more **strings** together.
    * Concat can be used instead of the plus operator.
* string1.concat(" ", string2) will result in "string1 string2".

### **Extracting Characters**
* **charAt(index)** - returns the **character** at an index.
* **charCodeAt(index)** - returns the **unicode** of the character at an index.

### **String to Array**
* The **split** method converts a string to an array.
    * str.split("where to split");
        * If separator is left **blank**, the array will contain the **complete string** at **index 0**.
        * If separator is **empty quotes** (""), the array will be split **after each character**.