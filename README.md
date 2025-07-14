# Fibonacci Java Implementation

A recursive implementation of the Fibonacci sequence in Java demonstrating the classic algorithmic approach.

## Features

- **Classic Recursive Algorithm**: Traditional recursive implementation for educational purposes
- **Simple Interface**: Clean, straightforward method signature
- **Pure Java**: No external dependencies required
- **Integer Input**: Accepts integer position values
- **Long Return Type**: Returns long values to handle larger Fibonacci numbers

## Prerequisites

- [Java Development Kit (JDK)](https://www.oracle.com/java/technologies/downloads/) (version 8 or higher)
- Command line access (Terminal, Command Prompt, or PowerShell)

## Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd fibonacci-java
   ```

2. **Verify Java Installation**
   ```bash
   java -version
   javac -version
   ```

## Usage

### Compiling the Java Code

To compile the Java source code:

```bash
javac Fibonacci.java
```

### Running the Program

Currently, the code provides a static method but no main method. To use it, you can either:

**Option 1: Create a simple test program**
```java
public class FibonacciTest {
    public static void main(String[] args) {
        System.out.println("fibonacci(0) = " + Fibonacci.fibonacci(0));
        System.out.println("fibonacci(1) = " + Fibonacci.fibonacci(1));
        System.out.println("fibonacci(5) = " + Fibonacci.fibonacci(5));
        System.out.println("fibonacci(10) = " + Fibonacci.fibonacci(10));
    }
}
```

**Option 2: Use Java REPL (jshell) - Java 9+**
```bash
jshell
jshell> /open Fibonacci.java
jshell> Fibonacci.fibonacci(10)
```

## Code Structure

### Main Function

The `fibonacci(int n)` method:
- Takes an integer position parameter (0-indexed)
- Returns the Fibonacci number at that position as a long
- Uses recursive approach: `fibonacci(n-1) + fibonacci(n-2)`
- Base case: returns `n` when `n <= 1`

### Example Usage

```java
Fibonacci.fibonacci(0);  // Returns: 0
Fibonacci.fibonacci(1);  // Returns: 1
Fibonacci.fibonacci(5);  // Returns: 5
Fibonacci.fibonacci(10); // Returns: 55
```

## Performance Characteristics

**Current Implementation:**
- **Time Complexity**: O(2^n) - Exponential time due to repeated calculations
- **Space Complexity**: O(n) - Due to recursive call stack
- **Performance**: Becomes very slow for larger values (n > 40)

### Performance Comparison

| Algorithm | Time Complexity | Space Complexity | fibonacci(40) |
|-----------|----------------|------------------|---------------|
| Naive Recursion (Current) | O(2^n) | O(n) | ~1-2 seconds |
| Iterative | O(n) | O(1) | ~0.001 seconds |
| Memoization | O(n) | O(n) | ~0.001 seconds |

## Development

### Project Structure

```
fibonacci-java/
├── Fibonacci.java   # Main Java implementation
├── LICENSE         # License file
├── .gitignore      # Git ignore patterns
└── README.md       # This file
```

### Potential Improvements

The current implementation could be enhanced with:

1. **Input Validation**: Check for negative inputs
2. **Error Handling**: Throw exceptions for invalid inputs
3. **Performance Optimization**: Use iterative or memoized approach
4. **Main Method**: Add executable main method for testing
5. **Overflow Protection**: Handle integer overflow for large values

### Example Iterative Implementation

For better performance, consider this iterative approach:

```java
public static long fibonacciIterative(int n) {
    if (n <= 1) return n;
    
    long prev = 0, curr = 1;
    for (int i = 2; i <= n; i++) {
        long next = prev + curr;
        prev = curr;
        curr = next;
    }
    return curr;
}
```

## Educational Value

This implementation demonstrates:
- **Recursive Problem Solving**: Classic recursive algorithm design
- **Base Cases**: Proper handling of termination conditions
- **Exponential Time Complexity**: Shows why some recursive solutions are inefficient
- **Algorithm Analysis**: Comparison of different approaches

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Learning Resources

- [Java Recursion Tutorial](https://docs.oracle.com/javase/tutorial/java/javaOO/recursion.html)
- [Fibonacci Sequence - Algorithm Analysis](https://en.wikipedia.org/wiki/Fibonacci_number)
- [Dynamic Programming vs Recursion](https://www.geeksforgeeks.org/overlapping-subproblems-property/)