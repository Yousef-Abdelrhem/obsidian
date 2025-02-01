

## **The never type**

- #### The **never** type represents values that never occur. We often use them to annotate functions that never return or always throw an error.
-
```
function **processEvents**(): never 
{ 
// This function never returns because 
// it has an infinite loop.
while (true) {} 
}
```



--------------------------------------------------

- type UserKeys = keyof User; // "id" | "number" |  "user" 

- type  UserKeys = keyof typeof user;

- type AgeType = User['name'];
----------------------------
 
function udateUser(user: User , updateProperties: User){
return {
	user,
	udateUser
}
}

