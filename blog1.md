# From JS to F#

I like a lot of the newer developers learnt how to code using Javascript. I loved how quickly I could get a project up and running. But it always came with a cost of bugs and surprises for the QA team. Since JS has no type safety its up to us developers to run through the possibilities and ensure weird bugs dont pop up and thats hard.

Typescript to the rescue! Even though I got to use the awesome features that JS/TS had to offer, it always felt like extra work, like fighting an uphill battle especially with the `any` type in play.

# The Pit of success // TODO: link to Mark Seemans blog

How do you win the uphill battle? Flip it on its head and make it hard to do the wrong thing. Thats why I fell in love with F#.
It is a functional first language that is type safe and has all the features you love about JS and a lot more! The biggest difficulty I had when trying to learn a statically typed langauage was all the pre setup and the verbose syntax of having to specify everything coming from a world where I could just focus on the code. But with F# that isnt the case.

Here's a few direct comparisons

Mapping through a list

JS

```
const oneToFive = [1,2,3,4,5]

const doubleInput = input => input.map(x => x * 2)
// doubleInput(oneToFive)
// [2,4,6,8,10]

```


F#
```

let oneToFive = [1;2;3;4;5]

let doubleInput input = input |> List.map (fun x -> x * 2) // int list -> int list
// notice how the F# compiler has picked up on that input is an int list without being told as its looking at the context of the map function

// F# is often like maths if something is on both sides it can often be ommited giving an even cleaner syntax
// let doubleInput = List.map ((*) 2)

// input |> doubleInput
// [2;4;6;8;10]


```
Updating a field in an object/record

JS

```
const person1 = {firstName: "Akash", age: 24}

const updatePerson1 = {...person1, age: 25}
// {firstName: "Akash", age: 25}

```

F#

```
type Person = {
    FirstName: string
    Age: int
}

let person1 = 
    { FirstName = "Akash" 
      Age = 24 } // Person

let updatePerson1 = { person1 with Age = 25 }
// { FirstName = "Akash"; Age = 25 }  Person

// Here we define a type of Person but F# has picked up that both person1 and updatedPerson1 are both of type Person
```
Control Flow - Ternary Operator

JS
```
const isTrue = true ? 'This is the value' : 'Never get reached'
```

F#
```
let isTrue = if true then 'This is the value' else 'Never get reached' // string
```

Control Flow - If/Switch 

JS

```

```

F#

```
```

For me F# gets the balance between having to specify types and letting you focus on solving the problem! From the examples above we can see that F# is succinct and can be cleaner than JS but has full type safety.
