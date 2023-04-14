# 301-knowledge-base
Knowledge Base for the TechEd-301 course.


## Destructuring

```js
const book {
  title: "Curious George",
  author: "Rey",
  year: 1941,
  isbn: "whatever"
}

const {title, year} = book;

console.log(title);
console.log(year);
```

Not mine
```js
"use strict";

// Example Constructor Function
function Person(nameInput, ageInput) {
  this.name = nameInput;
  this.age = ageInput;
  // add a method
  this.sayHello = function () {
    console.log("Hello, my name is " + this.name);
  };
}

// Example of creating new objects using the constructor function
const person1 = new Person("John", 30);
const person2 = new Person("Jane", 25);
const person3 = new Person("Jack", 20);


// Example of calling the prototype method
person1.sayHello();
person2.sayHello();
person3.sayHello();

// Example of passing our Person objects to an array

// Create an empty array
const people = [];

// Push our Person objects into the array
people.push(person1, person2, person3);

// Example of using Local Storage to store our People array
localStorage.setItem("people", JSON.stringify(people));

// Example of retrieving our People array from Local Storage
const retrievedPeople = JSON.parse(localStorage.getItem("people"));

// When you run console.log(retrievedPeople) you will find that the objects in the array are missing the method we gave them, we can add this back in by passing our retrievedPeople through the Person constructor again, here is how we would do this.
retrievedPeople.forEach(function(theperson) {
  people.push(new Person(theperson.name, theperson.age));
})

// You can then use console.log(people) to see the updated array and each of these will now have the sayHello() method again.

// Example of clearing Local Storage
localStorage.clear();
```
