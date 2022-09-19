# Array

### Definition

An array is a collection of items that are store contiguously in memory. (in order)

Array data structure organizes elements sequentially i.e one after the other in memory.

array is also known as list.

**Array Types**

- Static array - The memory allocation is done at the compile time and the memory is allocated in the stack memory. The size of the array is fixed. (Array size is specified ahead of time).

- Dynamic array - The memory allocation is done at the runtime and the memory is allocated in the heap memory. The size of the array is not fixed

```
const myArray = [1, 'one', {some: 'object'}, new Date()]
```

![](https://docs.oracle.com/javase/tutorial/figures/java/objects-tenElementArray.gif)

### Operations

| Operation  | Big O |
| ---------- | :---: |
| **Lookup** | O(1)  |
| **Push**   | O(1)  |
| **Insert** | O(n)  |
| **Delete** | O(n)  |

### Usage of arrays

**Creating an array**

```
/**** create new variable ****/
const grades = [1,2,3];          // this is the best way to create an array.
const grades = new Array(1,2,3); // use of the constructor.
const grades = new Array(3);     // will initialize the array with the length of 3.
const newGradesArray = [...grades, grade];   // will declare the newGradesArray variable and assign the values from the grades array and from grade.
/**** create new variable ****/
/**** change const to let ****/
let grades = [1,2,3];          // this is the best way to create an array.
let grades = new Array(1,2,3); // use of the constructor.
let grades = new Array(3);     // will initialize the array with the length of 3.
grades = [...grades, grade];     // will reinstantiate the grades variable.
/**** change const to let ****/
// use of the concat() function.
const a = [1,2,3];
const b = [4,5,6];
const c = a.concat(b); // this creates a new array by concatenating the 2 arrays.
```

or using strings to create an array, by using the **_split_** method and space ' ' delimiter will create a new array containg the words of the text.

```
const words = someStringText.split(' ');
```

**Inserting elements to an array**
There are several ways to add a new element to the array for example:

```
// This two operations will add a new element at the end of the array.
grades.push(element);
grades[grades.length + 1] = grade;
// use of unshift() method will insert a new element at the front of the array.
grades.unshift(grade);
//use of the splice() method will insert a new element at the position indicated.
grades.splice(position, 0, grade);
```

The splice() method, has the ability to insert or to remove an element, the first parameter of the method indicates the position, the second parameter indicates the type of operation 0 = insert, 1 = delete, and the third parameter is the new value to insert.
**Deleting elements to an array**

```
// use of the splice() method.
grades.splice(position, numElementsToDelete);
```

### Examples

- [Array exercises and examples codes in ES6](./02-chapter-Arrays.js)
