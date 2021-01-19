# Destructuring Exercise
## Object Destructuring
### 1 Object Destructuring 1
What does the following code return/print?
```javascript 
let facts = {numPlanets: 8, yearNeptuneDiscovered: 1846};
let {numPlanets, yearNeptuneDiscovered} = facts;

console.log(numPlanets); // ?
console.log(yearNeptuneDiscovered); // ?
```
### 1 solution 
```javascript
console.log(numPlanets); // print 8
console.log(yearNeptuneDiscovered); // print 1846
```

===

### 2 Object Destructuring 2
What does the following code return/print?
```javascript
let planetFacts = {
  numPlanets: 8,
  yearNeptuneDiscovered: 1846,
  yearMarsDiscovered: 1659
};

let {numPlanets, ...discoveryYears} = planetFacts;

console.log(discoveryYears); // ?
```
### 2 solution 
```javascript
console.log(discoveryYears);
{
  yearNeptuneDiscovered: 1846,
  yearMarsDiscovered: 1659
}
```

=== 

### 3 Object Destructuring 3
What does the following code return/print?
```javascript
function getUserData({firstName, favoriteColor="green"}){
  return `Your name is ${firstName} and you like ${favoriteColor}`;
}

getUserData({firstName: "Alejandro", favoriteColor: "purple"}) // ?
getUserData({firstName: "Melissa"}) // ?
getUserData({}) // ?
```
### 3 solution 
```javascript
getUserData({firstName: "Alejandro", favoriteColor: "purple"}) 
//print "you name is Alejandro and you like purple"

getUserData({firstName: "Melissa"})
// print "you name is Melissa and you like green"

getUserData({})
// print "you name is undefined and you like green"
```

===

## Array Destructuring 
### 1 Array Destructuring 1
What does the following code return/print?
```javascript 
let [first, second, third] = ["Maya", "Marisa", "Chi"];

console.log(first); // ?
console.log(second); // ?
console.log(third); // ?
```
### 1 solution 
```javascript
console.log(first); // print Maya
console.log(second); // print Marisa
console.log(third); // print Chi
```

=== 

### 2 Array Destructuring 2
What does the following code return/print?
```javascript 
let [raindrops, whiskers, ...aFewOfMyFavoriteThings] = [
  "Raindrops on roses",
  "whiskers on kittens",
  "Bright copper kettles",
  "warm woolen mittens",
  "Brown paper packages tied up with strings"
]

console.log(raindrops); // ?
console.log(whiskers); // ?
console.log(aFewOfMyFavoriteThings); // ?
```
### 2 solution 
```javascript
console.log(raindrops); // print Raindrops on roses
console.log(whiskers); // print whiskers on kittens
console.log(aFewOfMyFavoriteThings)
// return 
[
  "Bright copper kettles",
  "warm woolen mittens",
  "Brown paper packages tied up with strings"
]
```

===

### 3 Array Destructuring 3
What does the following code return/print?
```javascript 
let numbers = [10, 20, 30];
[numbers[1], numbers[2]] = [numbers[2], numbers[1]]

console.log(numbers) // ?
```
### 3 solution
```javascript
console.log(numbers)
// return 
[10,30,20]

```

===

## ES2015 Refactoring
In this exercise, you’ll refactor some ES5 code into ES2015.
### 1 ES5 Assigning Variables to Object Properties
```javascript 
var obj = {
  numbers: {
    a: 1,
    b: 2
  }
};

var a = obj.numbers.a;
var b = obj.numbers.b;
```
### 1 solution 
```javascript
const obj = {
  numbers: {
    a: 1,
    b: 2
  }
}

const {numbers:{a,b}} = obj
```

===

### 2 ES5 Array Swap 
```javascript
var arr = [1, 2];
var temp = arr[0];
arr[0] = arr[1];
arr[1] = temp;
```
### 2 solution 
```javascript 
let arr = [1,2]
[arr[0],arr[1]]=[arr[1],arr[0]]
```

===

## raceResults()
Write a function called raceResults which accepts a single array argument. It should return an object with the keys first, second, third, and rest.

first: the first element in the array
second: the second element in the array
third: the third element in the array
rest: all other elements in the array
Write a one line function to make this work using
An arrow function
Destructuring
‘Enhanced’ object assignment (same key/value shortcut)
```javascript
raceResults(['Tom', 'Margaret', 'Allison', 'David', 'Pierre'])

/*
  {
    first: "Tom",
    second: "Margaret",
    third: "Allison",
    rest: ["David", "Pierre"]
  }
*/
```
### raceResults() solution
```javascript
const raceResults = ([first,second,third,...rest])=>({first,second,third,rest})
```