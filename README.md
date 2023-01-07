# TrailingClosures
Trailing Closures


**Trailing closures:**
```
func trailingClosure(closure10: () -> Void) {
    closure10()
}
trailingClosure {
    print("trailing closure")
}

func trailingClosure2(param: Double, for trailingClosure: () -> Void) {
    trailingClosure()
}
trailingClosure2(param: 17, for: {
    print("trailing closure2")
})

trailingClosure2(param: 19) {
    print("trailing closure3")
}

func trailingFunc(argument trailingClosure: () -> Void) {
    trailingClosure()
}
trailingFunc {
    print("trailing closure")
}
```


**Set closures as parameters and they get parameter:**
```
func paramClosure(closure: (String) -> Void) {
    closure("parameter")
}
paramClosure { param in
    print("it is a trailing closure with input \(param).")
}
```

**Set closures as a parameters and they returns values:**
```
func returningTrailingValuesFunc(param: (String) -> String) {
    print("I'm getting ready to go.")
    let const = param("Ankara")
    print(const)
    print("I arrived.")
}
returningTrailingValuesFunc { (param: String) -> String in
    return "I'm going to \(param)"
}

func trailingTwoParametersFunc(_ param1: [Int], for closure: (Int, Int) -> Int) {
    var variable = param1[0]
    
    for int in param1 {
        variable = closure(variable, int)
    }
}

let array = [30, 50, 40]
trailingTwoParametersFunc(array) { (firstValue: Int, secondValue: Int)  in
    return firstValue + secondValue
}
let sumOfParams: () = trailingTwoParametersFunc(array, for: +)
print(sumOfParams)
```


**Shortaned closure parameter callings:**
```
func shortanedEqualClosureFunctionCalls(closure: (String) -> String) {
    let const = closure("Ahmet")
    print(const)
    
}
shortanedEqualClosureFunctionCalls { (param: String) -> String in
    return "Closure1 \(param)"
}
shortanedEqualClosureFunctionCalls { param -> String in
    return "Closure2 \(param)"
}
shortanedEqualClosureFunctionCalls { param in
    return "Closure3 \(param)"
}
shortanedEqualClosureFunctionCalls { param in
    "Closure4 \(param)"
}
shortanedEqualClosureFunctionCalls {
    "Closure5 \($0)"
}
```

**Multiple parameters closures:**
```
func closureWithMultipleParameters(params: (String, Int) -> String) {
    let const = params("closure", 18)
    print(const)
}
closureWithMultipleParameters {
    "This is a \($0) which has \($1) parameters."
}


func anim(completion: () -> Void) {
    completion()
}
anim {
    print("Ahmet")
}
```


**Returns closures:**
```
func returningClosuresFromFunctions() -> () -> Int {
    let closure = {
        Int.random(in: 1...10)
    }
    return closure
}
let object = returningClosuresFromFunctions()
let random = object()
print(random)


func returningClosuresFromFunctions2() -> (String) -> Void {
    return {
        print("returning Closures From Functions \($0)")
    }
}
let object3 = returningClosuresFromFunctions2()
object3("2")


func returningClosuresFromFunctions3() -> () -> String {
    return {
        return "closure"
    }
}
let object4 = returningClosuresFromFunctions3()()
print(object4)


func returningClosuresFromFunctions4() -> (Int) -> String {
    return {
        return "\($0)"
    }
}
let object5 = returningClosuresFromFunctions4()(4)
```

