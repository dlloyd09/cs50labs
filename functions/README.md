# Functions

In this lab you will learn:

- What is a function
- Why programmers use functions
- How to write your own functions in C

## What is a Function?

Since the first program we wrote together, we've been using functions! These were functions that were given to us, that we didn't have to create ourselves, such as `printf()`, `get_int()`, etc.

These functions were written by programmers many years ago, and are made available to us so we don't have to constantly recreate the wheel! We are able to use these functions over and over again. This points to one key reason why programmer use functions, which is **reusability**. 

Imagine what programming would be like if we had to recreate `printf()` every time we wanted to output something to our terminal window! It would take forever to complete the simplist program! 

The other key reason that programmers use functions is **abstraction**. To use `get_int()` for instance, we need to know 
* The name of the function
* What the function does
* What arguments to give to the function
* What kind of result the function returns

One thing we **don't** need to know is **how the function works inside**! You don't have to know anything that goes on inside of the function.

{% next %}

## Writing our own Functions

We can write our own functions as well! Once we've taken the time to program and debug our function, we can use it over and over again in multiple programs. Using functions, our code becomes **simpler**, more **organized**, and **easier to debug**!

Every C program that we've written so far contains one function, the **main function**. We can define our own custom functions with similar syntax. 

The first line of a function requires three parts: **first**, the function's **return type**, which is the data type of the function's output that is "returned" to where the function was called. The return type of the `get_int()` function, for instance, is an `int`. Sometimes a function does not return a value, (such as `printf()`), in which case the return type is `void`. 

**Second**, the function's **name**; this cannot include spaces and cannot be one of C's existing keywords. 

**Third**, in parentheses, the function's parameters, also known as **arguments**. These are the function's inputs (if there are none, use `void`). The data type of each argument must be included in front of the argument name.

After this first line (known as the declaration line), the code defining the function itself is enclosed in curly braces.

{% next %}

Here is an example of our 

```c
#include <cs50.h>
#include <stdio.h>

int square(int n)
{
    return n *  n;
}

int main(void)
{
    int side = get_int("Enter the side length: ");

    printf("The area is %i.\n", square(side));
}
```

We've created a custom function named `square()`. We declare the function with the return type `int`, the name, `square`, and the argument with it's type, `(int n)`. Our `main()` function calls the `square()` function when printing the square of the input. We call the function using its name `square` with the value we are passing into that function `side`. The previous line of code declares and gets a value for `side`, so this variable is already initialized.

The function now runs and the value that's is passed it when it's called (stored in `side`) is copied into the variable defined as an input in the function (`n`). We now calculate the square and return it's value, which is an `int` since the function was declared with an `int` return value.

Note that our function, `square()`, is defined outside of and before the `main()` function. Placing our function before `main()`, allows the computer recognize it before our `main()` calls it.

Feel free to try typing this code into a new file, compiling it, and testing it.

{% next %}

## Your Turn

Now you will create a custon function `get_positive_int()`, which you will be able to use in future programs.

The code is already started, with a function declaration already done. However the function itself, always returns a special value `INT_MAX` which already exists for you, which is the largest possible value that can be held by an int. This value is sometimes used in functions you already used (such as `get_int()`) when an input for some reason can't be read.

So the return type `int`, the function name `get_positive_int`, and the input argument `prompt` which has a `string` datatype, are already defined for you. Your job is to change the code in curly brackets to print this `prompt`, to ask the user for a positive `int`, check a condition, and repeat this process when a number less than or equal to zero, is input. Think back to the lab where you used a loop to validate user input. Can an approach like that work here?

Try to get the function to do one thing at a time. Perhaps you try to get a loop working without a `prompt`, that only accepts positive numbers. Then try to add the `prompt`.

{% spoiler "Hint for using `prompt`" %}

If you wish to use `get_int()`, using `prompt` directly inside the parentheses won't work. This is because the input for `get_int()` uses placeholders for variables. So you may need to syntax something like 

```c
result = get_int("%s", prompt);
```

to use the parameter with `get_int()`.

{% endspoiler %}

If you are really stuck, try to write some pseudocode first. 

{% spoiler "Need help with the pseudocode?" %}

1. Declare a new variable to store the user input.
2. Get an value from the user and store in your new variable.
3. Check to see if the value of this variable is less than or equal to zero.
    1. If it is, go back to step 2.
4. Return the value that we know now is a positive number.


{% endspoiler %}


[For more information on functions download our CS50 Functions Reference Sheet](https://ap.cs50.school/assets/pdfs/unit2/functions.pdf) 