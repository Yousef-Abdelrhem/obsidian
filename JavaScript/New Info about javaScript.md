## ==In JavaScript There's typeof  "NaN"  is 'number' but not valid mathematical number==

## ==Clone an objects with different ways==
```js
/* copy one or more from target objects or compine into single object
*/
const another = Object.assign({}, the object you want to clone);
```
that the simplest way to clone an object (spreed operator)
```js 
const another = { ...circle };
```

## ==Template ``  keeps the format==
You can add place holder ${name}`
```js 
const another = `Hi ${name} ${2 + 3}`
```

## ==Factory function==
```js
let address1 = showAddress('a', 'b' , 124);

console.log(address1);

  

// factory functions

function showAddress(street , city , zipcode){

  return {

    street,

    city,

    zipcode,

  };

}
```

## ==Constructor Function==
we use name conviension Pascal Notation
```js
// constructor function

const address2 = new Address('a', 'b' , 121);

console.log(address2);

  

function Address(street , city , zipcode) {

  this.street = street;

  this.city = city;

  this.zipcode = zipcode;

}
```

## ==Search for objects inside array== 
because of every object have different reference we use find()
```js
const courses = [
  {id : 1 , name: 'a'},
  {id: 2, name: 'b'}
];

let course = courses.find(
  function(course){return course.name === 'a'});
  console.log(course);
```
in E6
```js
let course = courses.find((course) => course.name === 'a')
```
Search in array
```js 
const numbers = [1,2,3,4];
console.log(numbers.include(1));
```

## ==Search into arrays==
![[Pasted image 20240220191829.png]]
## ==Removing Elements in Arrays== 
```js
const number = [1,2,3];
// exclude the number from the array
const output = except(numbers , [1]);
```
## ==Emptying Array== 
![[Pasted image 20240220193034.png]]
## ==Combine and Slice Arrays==
if the object the gets copy by reference
![[Pasted image 20240220193552.png]]
New way in ES6 to combine using spread operator
```js 
 const first = [1,2,3];
 const second = [4,5,6];
 const combined = [...first , ...second];
  const combined = [...first , 'a' ,...second];
```


## ==iteration on array using forEach==
```js
const numbers  = [1 , 2, 3];

numbers.forEach((index ,number) => console.log(index , number));
```
## ==Combine URL using Highphynes of joining array==
```js
	const numbers = [1 , 2 ,3];

const joined = numbers.join('-');

console.log(joined);

/// techinque is useful to build url slug  transfer string to array then join('-')

const message = 'This is my first message';

const parts = message.split(' ');
console.log(parts);

const combined = parts.join('-');
console.log(combined);
```
## ==Sort Objects in array==
```js 
const courses = [

  {id : 1 , name :'Node.js'},

  {id : 2 , name : 'javascript'}

];

const sorted = courses.sort((a,b) => {
  let nameA = a.name.toLowerCase();
  let nameB = b.name.toLowerCase();
  
  if(nameA <nameB) return -1;

  if(nameA >nameB) return 1;

  return 0;

})

console.log(sorted);
```
## ==Check if every element in the array is Positive==
```js
const array = [1 , 2, -3];

// every checks every element

// some checks if there at least one element

let allPostives = array.every(num => {return num >= 0});
let atleastOnePostive = array.some(num => {return num >= 0});
```
## ==Filter The Array== 
```js
const array = [1 , 2, -3];

// filter
const filtered = array.filter(value => value >= 0);

console.log(filtered);
```
 Mapping Elements  & Objects 
```js 
const array = [1 , 2, -3];

// filter
const filtered = array.filter(value => value >= 0);

const items = filtered.map(n => '<li>' + n +'</li>');

const html = "<ul>"+ items.join('')+ "</ul>";

console.log(html);
```
Mapping object
```js
const array = [1 , 2, -3];
// filter
const filtered = array.filter(value => value >= 0);
const items = filtered.map(n => ({value: n});
);
console.log(items);
```
Chaning Method
```js 
const array = [1 , 2, -3];

// we put every function on seperate line 

const items = array
  .filter(value => value >= 0)
  .map(n => ({value: n}));
  .filter(obj => obj.value > 1)
  .map(obj => obj.value);
  
console.log(items);
```
## ==Reducing Array || S == 
```js 
const array = [1 , 2, -3 , 3];
const sum = array.reduce((accumulator , currentValue) => accumulator + currentValue);

console.log(sum);
```
## ==This Keyword==
```js
const video ={
  title : 'a',
  tags : ['a', 'b', 'c'],
  showTags() {
    this.tags.forEach(function(tag){
      console.log(this.title,tag);
    }, this);
  }
};

video.showTags();
```
![[Pasted image 20240301172224.png]]