# Pursuit-Core-iOS-Extra-Optionals-Questions

## Question 1

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)
```
answer:
```swift
var scores: (Int?, Int?, Int?)?
var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo = ( 4, 4, 7)
var sum = 0

scores = testCaseOne
if let one = scores?.0 {
    sum += one
}
if let two = scores?.1 {
    sum += two
}
if let three = scores?.2 {
    sum += three
}
print(sum)
```

## Question 2

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```
answer:
```swift
var tuple: (Int, Int)?
if Bool.random() {
    tuple = (5, 3)
}

if let unwrap = tuple {
    print(unwrap)
}
```
## Question 3

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
var myInt: Int?
if Bool.random() {
 myInt = 5
}
```
answer:
```swift
var myInt : Int?
if Bool.random() {
    myInt = 5
}

if let integer = myInt {
    print(integer * 2)
} else {
    print("Error message.")
}
```

## Question 4

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}
```
answer:
```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
    myDouble = 12
}

if let doubleOne = myDouble {
    print(doubleOne * doubleTwo)
} else {
    print("Error message.")
}
```

## Question 5

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```


## Question 6

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
```
answer:
```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
var sum1 = 0

if let firstNumber = myTuple.0 {
    sum1 += firstNumber
}
if let secondNumber = myTuple.1 {
    sum1 += secondNumber
}
if let thirdNumber = myTuple.2 {
    sum1 += thirdNumber
}
if let fourthNumber = myTuple.3 {
    sum1 += fourthNumber
}
```

## Question 7

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
```
answer:
```swift
let pokemonArray = ["Pikachu", "Bulbasaur", "Charmander", "Squirtle", "Not a Pokemon"]
let stoneArray = ["Electric","Grass","Fire","Water","No Stone"]
var pokemonCanEvolve : Bool?
pokemon = starterPokemon()
evolutionaryStone = eStone()

for index in 0...pokemonArray.count - 2 {
    if pokemon! == pokemonArray[index] && evolutionaryStone! == stoneArray[index] {
        pokemonCanEvolve = true
        break
    }
}
if pokemonCanEvolve != nil {
    print("\(pokemon!) can evolve using \(evolutionaryStone!) stone.")
}
```


## Question 8

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```
answer:
```swift
var numberOfPeople : Int?

if Bool.random() {
    numberOfPeople = 108
}

if let people = numberOfPeople {
    if people % 2 == 0 {
        print(people)
    }
}
```

## Question 9

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```
answer:
```swift
var someNumbers : [Int?] = []
var product = 1

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}

for i in 0..<someNumbers.count {
    if let number = someNumbers[i] {
        product *= number
    }
}

print(product)
```

## Question 10

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```
answer:
```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]
var cityNames = [String]()

for name in poorlyFormattedCityNames {
    if let cityName = name {
        cityNames.append(cityName.capitalized)
    }
}
print(cityNames)
```


## Question 11

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```
answer:
```swift
var aBunchOfNumbers: [Int?] = []
var evenNumberArray = [Int]()

for _ in 0..<20 {
    aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
for index in 0..<aBunchOfNumbers.count {
    if let number = aBunchOfNumbers[index] {
        if number % 2 == 0 {
            evenNumberArray.append(number)
        }
    }
}
print(evenNumberArray)
```


## Question 12

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`
answer:
```swift
let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]
var zipCodeNumbers = [Int]()

for zipCode in zipCodeStrings {
    zipCodeNumbers.append(Int(zipCode)!)
}
print(zipCodeNumbers)
```

## Question 13

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.

`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`

- Print the names of the students that do not have a favorite color.

```swift
for student in studentInfo {
    if student.2 == nil {
        print(student.0)
    }
}
```
- Print the names of the students that don't have a favorite color or a favorite food.
```swift
for student in studentInfo {
    if student.1 == nil && student.2 == nil {
        print(student.0)
    }
}
```
- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.

```swift
var completeStudentInfo = [(String, String, String)]()

for student in studentInfo {
    if let _ = student.1, let _ = student.2 {
        completeStudentInfo.append(student as! (String, String, String))
    }
}
print(completeStudentInfo)
```


## Question 14

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`


## Question 15

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`


## Question 16

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 17

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
