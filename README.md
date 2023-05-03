Download Link: https://assignmentchef.com/product/solved-cs141-assignment-7-dynamic-array-of-integers-class
<br>
Create a class named DynamicArray that will have convenient functionality similar to JavaScript’s Array object and Java’s ArrayList class. The class allows to store array of integers that can grow and shrink as needed, search and sort itself, add and remove elements.

You are not allowed to use ArrayList object as well as any methods from java.util.Arrays class.

Please see the list of required features and methods below.

<ol>

 <li>private int array[] You MUST store the data internally in a regular partially-filled array of integers. Please DO NOT USE ArrayList. The size of the allocated array is its capacity and will be discussed below.</li>

 <li>private int size This variable stores the number of “occupied” elements in the array. Set to 0 in the constructor.</li>

 <li><em>Constructor with parameter</em>. The parameter defines the capacity of initial array. Allocates array of given capacity, sets size field to 0. In case the parameter given to constructor is less than 0, IllegalArgumentException is being thrown.</li>

 <li><em>No-argument constructor</em>. Allocates array of size 10, sets size field to 0.</li>

 <li><em>Copy constructor</em>. The constructor takes an object of type DynamibcArray as a</li>

</ol>

parameter and copies it into the object it creates. The constructor throws

IllegalArgumentException if the object that was passed to copy from is null.

<ol start="6">

 <li>int getSize() returns the size – a number of occupied elements in the array.</li>

 <li>int [] toArray() accessor returns the array. Make sure you DO NOT</li>

</ol>

return the private array field. Instead, allocate memory for the new array, copy your array field into that new object, and return the new array.

<ol start="8">

 <li>public void push(int num) adds a new element to the end of the array and increments the size field.</li>

</ol>

If the array is full, you need to increase the capacity of the array:

<ol>

 <li>Create a new array with the size equal to double the capacity of the original one.</li>

 <li>Copy all the elements from the array field to the new array.</li>

 <li>Add the new element to the end of the new array.</li>

 <li>Use new array as an array field.</li>

</ol>

<h2>9. public int pop() throws RuntimeException  removes the last</h2>

element of the array and returns it. Decrements the size field. If the array is empty a RuntimeException with the message “Array is empty” must be thrown. At this point check the capacity of the array. If the capacity is 4 times larger than the number of occupied elements (size), it is time to shrink the array:

<ol>

 <li>Create a new array with the size equal to half of the capacity of the original one.</li>

 <li>Copy all the elements from the array field to the new array.</li>

 <li>Use new array as an array field.</li>

</ol>

<h2>10. int get(int index) throws IndexOutOfBoundsException</h2>

returns element of the array with the requested index. If the index provided is too large or negative, the IndexOutOfBoundsException is thrown with the message “Illegal index”.

<ol start="11">

 <li>int indexOf(int key) returns the index of the first occurrence of the given number. Returns -1 when the number is not found.</li>

</ol>

<h2>12. void add(int index, int num) throws</h2>

IndexOutOfBoundsException  adds a new element (passed as parameter

num) to the location of the array specified by index parameter. If the index is larger than size of the array or less than 0, IndexOutOfBoundsException is thrown. When adding the element into the middle of the array, you’ll have to shift all the elements to the right to make room for the new one. If the array is full and there is no room for a new element, the array must be doubled in size. Please follow the steps listed in the push() method description to double the capacity of the array.

<h2>13. int remove ( int index) throws</h2>

IndexOutOfBoundsException  removes the element at the specified position in this array. When the element is removed from the middle of the array, all the elements must be shifted to close the gap created by removed element. If the index value passed into the method is more or equal to the size or less than 0 the IndexOutOfBoundsException must be thrown.

At this point check the capacity of the array. If the capacity is 4 times larger than the number of occupied elements (size), it is time to shrink the array.

<ol start="14">

 <li>boolean isEmpty() returns true if the size of the array is 0.</li>

 <li>void sort() – sorts the elements of the array. You can choose any sorting algorithm you prefer.</li>

 <li>void shuffle() – shuffles the elements of the array. Please do not use any methods from any collection objects to do the shuffling. Instead apply popular Fisher–Yates shuffle algorithm (find algorithm and even its Java encoding online).</li>

 <li>int findMin()throws RuntimeException returns the smallest element in the array. If the array is empty throws RuntimeException</li>

 <li>int findMax()throws RuntimeException returns the largest element in the array. If the array is empty throws RuntimeException</li>

 <li>String toString() – returns an array as a string of comma-separated values.</li>

 <li>boolean equals(DynamicArray obj) compares two objects (this one and the one passed as parameter) element-by-element and determines if they are exactly the same. The capacity of two compared objects is not being compared.</li>

</ol>