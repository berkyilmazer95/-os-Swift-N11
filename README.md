class HomeworkFunctions {

    //Write two functions that overload of each others.
    func writeString(str:String) -> Void {
        print((str))
    }

    func writeString(str: Bool) -> Void {
        print("Bool type: \(str)")
    }
    
    //Write a function which has default parameter value.
    func eatMenu(eatType: String, drink :String = "Cola"){
        print("Menu: \(eatType) with \(drink)")
    }
    
    //Write a function which has one paremeter and one variadic parameter.
    func vehicleModels(brand: String, model: String ...){
        print("Vehicle Brand: \(brand) => Model: \(model)")
    }
    
    //Write a function which has ignored external parameter name.
    func areYouHungry(_ hungry: Bool){
        print("Are You Hungry? \(hungry)")
    }
    
    //Write a function inside a function.
    func drivingLicense(age: Int){
        func suitable() -> Bool{
            if age > 18 {
                return true
            }
            else{
                return false
            }
        }
        if suitable() {
            print("You can take driving license")
        }
        else{
            print("You can't take driving license")
        }
    }
    
    //Write a recursive function.
    func doubleCountingDown(_ startNumber: Int){
        print(startNumber)
        if startNumber > 0 {
            doubleCountingDown(startNumber-2)
        }
    }
    
    //Write typealias for a function type which has different parameter types.
    typealias Counter = (String) -> (Int)
    
    //Pass function as a value to another function.
    let counter: Counter = { (item: String) -> Int in
        let str: String  = item
        return str.characters.count
    }
    
    func letterCount(_ textToCount: String, _ op:Counter){
        print("Text is: \(textToCount)")
        let result = op(textToCount)
        print("Letter count is: \(result)")
    }
    
}

// ************ Test  *****************************
let functions = HomeworkFunctions()

print("Write two functions that overload of each others.")
functions.writeString(str: "N11 Ios Swift")
functions.writeString(str: true)
print(" ")

print("Write a function which has default parameter value.")
functions.eatMenu(eatType: "Big Mac")
functions.eatMenu(eatType: "Big Mac", drink: "Ice Tea")
print(" ")

print("Write a function which has one paremeter and one variadic parameter.")
functions.vehicleModels(brand: "Toyota", model: "Auris", "Verso", "Hilux")
print(" ")

print("Write a function which has ignored external parameter name.")
functions.areYouHungry(true)
print(" ")

print("Write a function inside a function.")
functions.drivingLicense(age: 20)
functions.drivingLicense(age: 1)
print(" ")

print("Write a recursive function.")
functions.doubleCountingDown(3)
print(" ")

//Function 7 & 8 - TEST
typealias Counter = (String) -> (Int)
let letterCounter: Counter = { (item: String) -> Int in
    let str: String  = item
    return str.characters.count
}
functions.letterCount("N11 Ios Swift Programming", letterCounter)
