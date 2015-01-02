**Problem:**

What is the result of executing the following code in the REPL?

  List(1, 2).map { i => println("Hi"); i + 1 }
  List(1, 2).map { println("Hi"); _ + 1 }


**Prints:**
```
     Hi
     Hi
     List[Int] = List(2, 3)
     Hi
     List[Int] = List(2, 3)
```

**Explanation:**

The first statement, { i => println("Hi"); i + 1 }, is identified as one function literal expression of the form arg => expr, with expr here being the block, println("Hi"); i + 1.

Whereas the second statement, { println("Hi"); _ + 1 }, is identified as two expressions: println("Hi") and _ + 1. The block is executed, and the last expression (which is conveniently of the required function type, Int => Int) is passed to map. The println statement is not part of the function body. It is invoked when the argument to map is evaluated, not as part of the execution of map.
