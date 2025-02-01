## *Annotation*

- let sales: number = 123_456_789;
- let numbers: number[] = [1, 2, 3];
## *Tuples*

- let user: [number, string] = [1, 'Joe'];
## *Union types*

- let **weight**: **number** | **string** = 1;
- **weight** = '1kg';

## *objects*

let **employee**: {
**id**: number;
**name**: string;
**retire**: (date: Date) => void } 
= {
**id**: 1,
**name**: 'Ahmed',
**retire**: (date: Date) => {}, 
};

### *Literal types*

**type** Quantity = 50 | 100;
**type** UserId = string | number;
### *Optional chaining (?.)*

**customer**?.**birthdate**?.getFullYear();
customers?.[0];
log?.('message');

-------
# readonly

**readonly** id: number --> can't mutate **!**

let users: **readonly** string[]: ['user1','user3','user3'];

---------------------
const user = {
id: 1,
name: "mo'men".
age: 28,
} **as const**; --> makes object **immutable**

const x = [1,2,3] **as const**; -->  makes array **immutable**

---------------
## **Dynamic obj**

const x : {
	[ key: string ] : **number** | **boolean**;
} = {
	HTML : true,
	 CSS: true,
	 JS: true
}
x.TS = true --> error

--------------
# **Functions**

function calculateTax( income: **number** ): **number**
{ return income * .2; }

const subtract = ( a: **number**, b: **number** ): **string** =>${a + b};

function printUser( **firstName**: string, **lastName**?:string){

if(**lastName**){
console.log(**lastName**?.toUpperCase);
}
}

---------------------
## **interfaces**

**interface** **Calendar** {
name: string; 
addEvent(): void; 
} 

**interface** A **extends** B { 
}

---------------------
## **Omit**
let **product**: **Omit**<Product, 'name'>;

-----------------
# *Template Literal Types*

type EmailLocaleIDs = "welcome_email" | "email_heading";

type FooterLocaleIDs = "footer_title" | "footer_sendoff";

type AllLocaleIDs = `${EmailLocaleIDs} { FooterLocaleIDs}`;

-----------------

- The **any** type can represent any kind of value. It’s something we should avoid as much as possible because it defeats the purpose of using TypeScript in the first place. A variable of type any can take any kind of value!

- The **unknown** type is the type-safe version of any. Similar to any, it can represent any value but we cannot perform any operations on an unknown type without first narrowing to a more specific type.

- Using **optional chaining** **(?.)** we can simplify our code and remove the need for null checks.

 - Using type mapping we can create new types based off of existing types. For example, we can create a new type with all the properties of another type where these properties are **readonly**, optional, etc
 
- With intersection types, we can combine multiple types into one (eg Draggable & Resizable).
   **type** UIWidget = Draggable **&** Droppable
