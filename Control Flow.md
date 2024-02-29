In Bash scripting, control flow structures allow you to make decisions and control the flow of execution in your script. Here are key control flow structures:

### 1. **if-else Statements:**

```bash
#!/bin/bash

# Prompt the user for a number
echo -n "Enter a number: "
read num

# Check if the number is positive, negative, or zero
if [ $num -gt 0 ]; then
    echo "The number is positive."
elif [ $num -lt 0 ]; then
    echo "The number is negative."
else
    echo "The number is zero."
fi
```

In this example:
- `if` checks if the number is greater than 0.
- `elif` (else if) checks if the number is less than 0.
- `else` covers the case when the number is zero.

### 2. **for Loop:**

```bash
#!/bin/bash

# Iterate over a range of numbers
for i in {1..5}; do
    echo "Iteration $i"
done
```

This script uses a `for` loop to iterate from 1 to 5, and the variable `i` takes on each value in the specified range.

### 3. **while Loop:**

```bash
#!/bin/bash

# Initialize a counter
counter=1

# Use a while loop to count up to 5
while [ $counter -le 5 ]; do
    echo "Count: $counter"
    ((counter++))
done
```

Here, a `while` loop is used to increment a counter from 1 to 5.

### 4. **case Statement:**

```bash
#!/bin/bash

# Prompt the user for a color
echo -n "Enter a color (red, green, or blue): "
read color

# Check the color using a case statement
case $color in
    "red")
        echo "Roses are red."
        ;;
    "green")
        echo "Grass is green."
        ;;
    "blue")
        echo "The sky is blue."
        ;;
    *)
        echo "Not a recognized color."
        ;;
esac
```

The `case` statement checks the value of the color variable against various patterns and executes the corresponding block of code.

These control flow structures provide the foundation for decision-making and looping in Bash scripts. They allow you to create more complex and responsive scripts based on different conditions and scenarios.