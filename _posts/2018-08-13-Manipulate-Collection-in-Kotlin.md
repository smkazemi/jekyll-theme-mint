---
layout: post
---
## `filter`

###### Quick introduction

By this function we can apply a desired predicate as lambda to a collection, like `list.filter { }`
And the result is a new collection that contains only the elements that satisfy the predicate.

```kotlin
>>> val list = listOf(1,2,4,3,5,6)
>>> println(list.filter { it > 3 })
[4,5,6]
```
>the code is in curly braces `{ it > 3 }` is a lambda implementing logic . 

>Note that _filter_ creates an intermediate collection in order to store elements are in accordance with 
>predicate, And these function so-called named as eager function

## `map`
you can access to elements in collection by call `.map` on collection name , like this :

```kotlin
>>> println(list.map {it})
>>> [1,2,4,3,5,6]
```      

###### Combine together
Assume we have a class in order to hold information of people inclusive name, phone number, age, address 
Also a list of people, now we need to write a function to find just people that are older 20 y.o .
do this with the help of `filter` and `map` function :

```kotlin
data class Person(val name: String, val age: Int, val address : String)
 
val list = listOf(
            Person("mrBlue", 36)
            , Person("mrWhite", 52)
            , Person("mrGreen", 20)
            , Person("mrRed", 16)
        )

>>> println(list.filter { p : Person -> p.age >= 20})
[Person(name=mrBlue, age=36), Person(name=mrWhite, age=52), Person(name=mrGreen, age=20)]
```

As you can see by this code we will get a collection of Person instances, But we just can find people by its names,
therefore need to modify above code to achieve names, and at this time will be used `map`

```kotlin
>>> println(list.filter { p : Person -> p.age >= 20}.map { it.name })
[mrBlue, mrWhite, mrGreen]
```

> there is separate functions to handle keys And values of a map Collection
> `filterValues` and `mapValues` filter and transform values respectively
> `filterKeys` and `mapKeys`  filter and transform keys respectively

