# Important
Every Kotlin code has a main() function which will execute at the start.
You can test simple Kotlin code in the [Kotlin Playground](https://developer.android.com/training/kotlinplayground)
# Variables
## Declare
```kotlin
var x: Int = 8 // Standard way of declaring a variable
var x = 8 //Shortened way
```
## Val 
Val declares a variable that cannot be modified
```kotlin
val x: Int = 8; //This will not change 
x = x + 1 //This will fail
```

# Functions
## Declare
```kotlin
fun myfunction(parameters) {
	body
}
```
## Return Types
### Unit
If you don't specify a return type on a function the default will be Unit which means it doesn't return anything.
Example:
```kotlin
fun helloWorld() { 
	println("Hello World")
}
fun helloWorld(): Unit {
	println("Hello World")
}
```
The two functions above will produce the same output
### String
To return a String you use the following syntax
```kotlin
fun myfunction(): String {
	//Do anything here
	return //Whatever you want
}
```
Example: 
```kotlin
fun helloWorld(): String {
	val hello = "Hello "
	val world = "World!"
	return "$hello$world" //Here we are returning both values in a single return statement instead of having to use another variable by putting both together in a single string
}
```
Now, to print this our main function should look something like this:
```kotlin
fun main() {
	println(helloWorld()) //Output: "Hello World!"
}
```
### Int
Int looks similar to String
```kotlin
fun valueOfX(): Int {
	var x = 9
    return x //This returns a 9
}
```

## Using Parameters
### Important!
Unlike in some languages, such as Java, where a function can change the value passed into a parameter, parameters in Kotlin are immutable. You cannot reassign the value of a parameter from within the function body.

### Single parameter
The syntax is very simple
```kotlin
fun nameOfFunction(paremeter: dataType): returnType {
	body
}
```
Example
```kotlin
fun helloSomething(something: String): String {
	val helloWithParam = "Hello $something!"
	return helloWithParam
}
//We pass the parameter like this
fun main() {
	println(helloSomething("World")) //Output: "Hello World!"
	println(helloSomething("Sonic")) //Output: "Hello Sonic!" 
}
```
### Multiple Parameters
You must separate the parameters by comas on both functions:
```kotlin
fun giveAge(name: String, age: Int): String {
	val yourAge = "You are $name and you are $age years old!"
	return yourAge 
}
fun main() {
	println(giveAge("Javi", 35)) //Output: You are Javi and you are 35 years old!
}
```
### Named Arguments
You don't have to put the parameters in order, you can specify which one is each one and get the same output.
Example with the same function as before:
```kotlin
fun main() {
	println(giveAge(age = 35, name = "Javi"))//Output: You are Javi and you are 35 years old!
}
```
### Default Arguments
You can give a default parameter to your function and, unless specified otherwise, it will be used in your function. 
Example: 
```kotlin 
fun giveAge(name: String = "Omar", age: Int = 19): String {
	val yourAge = "You are $name and you are $age years old!"
	return yourAge 
}
fun main() {
	println(giveAge())//Output: "You are Omar and you are 19 years old!"
	println(giveAge(age = 43))//Output: "You are Omar and you are 43 years old!"
	println(giveAge("Javi"))//Output: "You are Javi and you are 19 years old!"
	println(giveAge("Derek", 33))//Output: "You are Derek and you are 33 years old!"
}
```

# Additional Information
## println
println() prints messages on different lines

## Comment
```kotlin
//This is a single line comment
/*
This is a multiple line comment
This is a multiple line comment
This is a multiple line comment
*/
```

## Ignore the next character
You can print symbols you usually won't be able to using \.

Ex:
```kotlin
fun main() {
	val name = "Pepe"
	println("Hola $name")//Output: "Hola Pepe"
	println("Hola \$name")//Output: "Hola $name"
}
```
## Documentation
You can read the docs of Kotlin [here](https://kotlinlang.org/docs/home.html)
## Keywords
You can find the keywords of Kotlin [here](https://kotlinlang.org/docs/keyword-reference.html)
# Exercices 
Use the [Kotlin Playground](https://developer.android.com/training/kotlinplayground) to solve this exercises. 

1.- Write a main() function that prints the following messages in different lines.
```
Use the val keyword when the value doesn't change. 
Use the var keyword when the value can change.
When you define a function, you define the parameters that can be passed to it. 
When you call a function, you pass arguments for the parameters.
```

2.- The following code has an error
```kotlin
fun main() {     
	println("New chat message from a friend'}
}
```
Correct it so that it prints the following
```
New chat message from a friend
```

3.- Correct the following code
```kotlin
fun main() {    
	val discountPercentage: Int = 0
	val offer: String = ""    
	val item = "Google Chromecast"    
	discountPercentage = 20    
	offer = "Sale - Up to $discountPercentage% discount on $item! Hurry up!"        
	println(offer)
}
```
It must print the following
```
Sale - Up to 20% discount on Google Chromecast! Hurry up!
```

4.- Correct the following code
```kotlin 
fun main() {    
	val numberOfAdults = "20"    
	val numberOfKids = "30"    
	val total = numberOfAdults + numberOfKids    
	println("The total party size is: $total")
}
```
It must print the following
```
The total party size is: 50
```

5.- To the following code add a function called add() that adds 2 numbers together
```kotlin
fun main() {    
	val firstNumber = 10    
	val secondNumber = 5    
	val thirdNumber = 8        
	val result = add(firstNumber, secondNumber)    
	val anotherResult = add(firstNumber, thirdNumber)   
	println("$firstNumber + $secondNumber = $result")    
	println("$firstNumber + $thirdNumber = $anotherResult")
}
```
It must print the following 
```
10 + 5 = 15
10 + 8 = 18
```

6.- Write a function that compares the time in minutes that you spent on your phone today versus the time spent yesterday. The function accepts two integer parameters and returns a boolean value.

The first parameter holds the number of minutes that you spent today and the second parameter holds the number of minutes that you spent yesterday. The function returns a `true` value if you spent more time on the phone today compared to yesterday. Otherwise, it returns a `false` value.

For example, if you called the function with these named arguments:

- timeSpentToday = 300 and timeSpentYesterday = 250, the function returns a true value.
- timeSpentToday = 300 and timeSpentYesterday = 300, the function returns a false value.
- timeSpentToday = 200 and timeSpentYesterday = 220, the function returns a false value.




