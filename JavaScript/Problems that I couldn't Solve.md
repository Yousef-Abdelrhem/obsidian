
## ==typeof == 'number'==
in javascript there's operator call typeof operator.
`typeof` (returns a string indicating the type of a variable)
```js 
 if(typeof input !== 'number')

        return 'Not a Number'
```


## ==Count The Multiplication limit 10 , num1 = 3 , num = 5;==
```js
console.log(sum(10));

function sum(limit){
  let sum=  0;

    for(let i = 0; i <= limit ;i++){

        if( i % 3 === 0 || i % 5 === 0)

            sum += i;
    }

     return sum;

}****
```


## ==Is Prime ()== 
Number is prime if it accept division on himself and 1 only
first solve is bad for efficiency
```
showPrime(10);
function showPrime(limit){

 for(let i = 2; i <= limit ; i++){

  let isPrime = true;

  for(let factor = 2; factor <  i; factor++){

      if(i % factor === 0) isPrime = false;

  }

  if(isPrime) console.log(i);

 }

}
```
Second one is good for efficiency
```
```

## ==Shift number to specific offset using splice function==
```js 
const number = [1 ,2 ,3 ,4];

console.log(move(number,0,-1)); 

function move(array , index , offset){

  let position = index + offset;

   if(position >= array.length || position <= 0){
    console.error("Invalid Number");
   return

   }
   let output = [...array];
   const element = output.splice(index,1)[0];
   output.splice(position,0, element);
   return output;
}
```
## ==count Occurrences && get Max using reduce== 
```js 
const number = [1 ,2 ,2 ,4];

function countOccurrences(array , searchElement){
  return array.reduce((accumulator , currentVal) => {
  const count = (currentVal === searchElement) ? 1 : 0;
  return accumulator + count;
  }, 0);
}
console.log(countOccurrences( number, 2));
```
```js
const number = [1 ,2 ,2 ,4];
function getMax(array){
 return array.reduce((a , b) => (a > b) ? a : b);
}
console.log(getMax(number));
```
## ==Pick up titles of movie objects using filter() sort() map()==
```js 
const movies = [
  {title: 'a' , year : 2018 , rating : 4.5},
  {title: 'b' , year : 2018, rating : 4.7},
  {title: 'c' , year : 2018, rating : 3},
  {title: 'd' , year : 2017, rating : 4.5},
];
// all movies in 2018 rating > 4
/// sort them by thier rating
// descending order
// pick thier title

 const title = movies
 .filter(m => m.year === 2018 && m.rating > 4)
 .sort((a,b) => (a.rating - b.rating))
 .reverse()
 .map(m => m.title);
 console.log(title);
```