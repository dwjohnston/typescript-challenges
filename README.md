# typescript-challenges


## Basics 

1. Create a function `myFunction` that only accepts a value of type string, and returns a number 


```
myFunction("hello"); //ok
myFunction(1) // wrong 

const a: number = myFunction("hello"); //ok
const a: string = myFunction("hello"); //wrong

```


2. Create a type `User` that represents this data: 

```
{
    name: "John", 
    age: 33, 
    isMale: true, 
}
```

usage: 

```
const a: User = {
    name: "John", 
    age: 33, 
    isMale: true, 
}; //ok

const b: User = {
    name: "John", 
    age: "33", 
    isMale: true, 
}; //wrong

```


3. Create a type `FooConfig` that represets this object: 

```
const myObject = {
    name: "someObject", 
    onClick: () => {
        return "hello world!"; 
    }
}

```

usage: 

```
const a : FooConfig = {
    name: "someObject", 
    onClick: () => {
        return "hello world!"; 
    }
}; // ok

const b: FooConfig = {
    name: "someObject", 
    onClick: () => {
        return 99; 
    }
}; //wrong 


const c: FooConfig = {
    name: "someObject", 
} // wrong
```


4. Create a function `logMessage` that accepts a string or a number, and returns nothing 

usage: 

```
    logMessage(1); //ok
    logMessage("hello"); // ok
    logMessage({
        hello: "world"
    }); //wrong 
    const a : number = logMessage(1); //wrong
    
```

5. Merge the following types to create type C: 


```
type A = {
    foo: string; 
}

type B = {
    bar: string; 
}
```

So that: 


```
const a: C = {
    foo: "hello", 
    bar: "world"
}; //ok 

const b: C = {
    bar: "world"
}; // wrong


const c: C = {
    foo: "hello",
}; // wrong

```

6. Create a type User, where the property `role` can only be "admin", "owner", or "editor". 


usage: 

```

const a : User = {
    name: "bob", 
    role: "admin"
}; // Ok

const b : User = {
    name: "bob", 
    role: "owner"
}; // Ok

const c : User = {
    name: "bob", 
    role: "foobar"
}; // Wrong


```

7. Create a type 
