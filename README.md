# TrailingClosures
Trailing Closures


**Trailing closure syntax**

func trailingClosure(closure10: () -> Void) {
    print("==========")
    closure10()
    print("==========")
}
trailingClosure {
    print("trailing closure")
}

func trailingClosure2(param: Double, for trailingClosure: () -> Void) {
    print("==========")
    trailingClosure()
}
trailingClosure2(param: 17, for: {
    print("trailing closure2")
})

trailingClosure2(param: 19) {
    print("trailing closure3")
}

func trailingFunc(argument trailingClosure: () -> Void) {
    print("==========")
    trailingClosure()
}
trailingFunc {
    print("trailing closure")
}
