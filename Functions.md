In Bash, functions allow you to group a series of commands into a reusable block of code. They are defined using the `function` keyword or simply by providing the function name followed by parentheses. Here's a basic syntax for defining and using a function:

```bash
function my_function() {
    # Commands to be executed
    echo "Hello from my_function!"
}

# Call the function
my_function
```

or

```bash
my_function() {
    # Commands to be executed
    echo "Hello from my_function!"
}

# Call the function
my_function
```

Let's break down the key components of Bash functions with examples:

1. **Function Definition:**
   ```bash
   my_function() {
       # Commands to be executed
       echo "Hello from my_function!"
   }
   ```
   This defines a function named `my_function`. The function body contains the commands to be executed when the function is called.

2. **Calling a Function:**
   ```bash
   # Call the function
   my_function
   ```
   This line calls the `my_function` and executes the commands inside it.

3. **Passing Arguments to a Function:**
   Functions in Bash can take arguments, similar to scripts. For example:
   ```bash
   greet() {
       echo "Hello, $1!"
   }

   greet "Alice"
   ```
   Here, the function `greet` takes one argument (the name) and prints a greeting.

4. **Returning Values:**
   Bash functions can return values using the `return` statement. For example:
   ```bash
   add() {
       local result=$(( $1 + $2 ))
       return $result
   }

   add 3 5
   sum=$?
   echo "Sum: $sum"
   ```
   The function `add` calculates the sum of two numbers, and the result is retrieved using `$?`.

5. **Local Variables:**
   Using `local` declares a variable with local scope within the function. It prevents variable name clashes with variables outside the function. For example:
   ```bash
   multiply() {
       local result=$(( $1 * $2 ))
       echo $result
   }

   product=$(multiply 4 6)
   echo "Product: $product"
   ```

6. **Recursive Functions:**
   Bash supports recursive functions. For example, a simple factorial function:
   ```bash
   factorial() {
       if [ $1 -le 1 ]; then
           echo 1
       else
           local subfactorial=$(factorial $(( $1 - 1 )))
           echo $(( $1 * $subfactorial ))
       fi
   }

   result=$(factorial 5)
   echo "Factorial of 5: $result"
   ```

Remember that Bash functions can also have local and global variables, and they can access environment variables. Functions provide modularity and improve code readability and maintainability.