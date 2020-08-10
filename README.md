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

## Generics

1. Create a type `PurchaseOrder` using generics, where the following would be valid: 

```

type Book = {
     name: string; 
     value: number; 
}

type Movie = {
    title: string; 
    year: number; 
}


// incomplete! you need to add generic typings
type PurchaseOrder = {
    date: string; 
    item: ???
}


// incomplete! add typings
function getItemFromPurchaseOrder(purchaseOrder) {
    return purchaseOrder.item; 
}

const a = getItemFromPurchaseOrder({
    date: "today", 
    item: {
        name: 'book', 
        value 1, 
    }
});

console.log(a.name); //shouldn't error
console.log(a.title); //should error 

const b = getItemFromPurchaseOrder({
    date: "today", 
    item: {
        tile: 'movie', 
        year 1, 
    }
});

console.log(b.name); //should error
console.log(b.title); //shouldn't error 

```

2. Declare an async function that returns a an item of type `Foo` when the promise resolves. 


3.  Given the types `Foo` and `Bar` write a function that will return an array of both `Foos` and `Bar`, and then seperate the foos and bars into seperate lists. 

```
type Foo = {
   foo: string; 
}

type Bar = {
   bar: number; 
}

```

```
const listOfFoosAnBars = getListOfFoosAndBars(); // You need to implmeent this function. 


//These need to be typed objects. How do you seperate them? 
const listOfFoos = ??? 
const listOfBars = ???


````


## Object mapping

Given the following: 

```
type Order = {
    id: string; 
    name: string; 
    value: number; 
}

type OrderMap = Record<string, Order>; 


const orders : Array<Order> = [
    {
        id: "aaa", 
        name: "a", 
        value: 1
    },
        {
        id: "bbb", 
        name: "b", 
        value: 2
    },
    {
        id: "ccc", 
        name: "c", 
        value: 3
    }
]; 
```

Create a function that uses  the `Object.reduce` function to convert the array of Orders into a map of orders, indexed by id. 

ie. the final result should be 

```


function createOrderMap(array: Array<Order>) : OrderMap {
    //implement
}

const orderMap: OrderMap = {
     "aaa": {
        id: "aaa", 
        name: "a", 
        value: 1
    },
     "bbb" : {
        id: "bbb", 
        name: "b", 
        value: 2
    },
    "ccc" : {
        id: "ccc", 
        name: "c", 
        value: 3
    }

}

```





```
