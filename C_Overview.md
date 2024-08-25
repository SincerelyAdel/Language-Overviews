# C Overview

## Empty Main Function

stdio.h is a C header file containing function definitions, this specific one is for input/output.

the main function is the entry point of the program, try removing it!
```c
#include <stdio.h>

int main() {
    // enter code here, exit 0 means no errors!
    return 0;
}
```

## Simple Variable Declaration

```c
#include <stdio.h>

int main() {
    // Declare and initialize variables
    int age = 25;
    float height = 1.75;
    char name[] = "John";

    // Print the variables
    printf("Age: %d, Height: %.2f, Name: %s\n", age, height, name);
    return 0;
}
```

## Control Structure - Conditional If

```c
#include <stdio.h>

int main() {
    // Conditional if, else if, else
    int number = 10;

    if (number > 0) {
        printf("Number is positive\n");
    } else if (number < 0) {
        printf("Number is negative\n");
    } else {
        printf("Number is zero\n");
    }

    return 0;
}
```

## Control Structure - For Loop

```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("Iteration: %d\n", i);
    }

    return 0;
}
```

## Control Structure - While Loop

```c
#include <stdio.h>

int main() {
    int count = 0;

    while (count < 5) {
        printf("Count: %d\n", count);
        count++;
    }

    return 0;
}
```

## Simple Function

```c
#include <stdio.h>

int addNumbers(int a, int b) {
    return a + b;
}

int main() {
    int result = addNumbers(4, 5);
    printf("Result: %d\n", result);
    return 0;
}
```

## Empty Struct

Structs are similar to classes where-as they build complex data types from the original "primitive" ones.

```c
struct Person {
    // no members.
};
```

## Struct - Variables

```c
struct Rectangle {
    double width;
    double height;
};
```

## Struct - Functions

```c
#include <stdio.h>

struct Rectangle {
    double width;
    double height;
};

double calculateArea(struct Rectangle rect) {
    return rect.width * rect.height;
}

int main() {
    // instantiation
    struct Rectangle rect = {3.0, 4.0};
    double area = calculateArea(rect);
    printf("Area of rectangle: %.2f\n", area);
    return 0;
}
```

## Pointers

A pointer is used to statically assign memory to a certain data-typed variable and accessing it is called 'dereferencing' it.

```c
#include <stdio.h>

int main() {
    int num = 10;
    int *ptr = &num;

    printf("Value: %d\n", *ptr); // Dereferencing the pointer
    return 0;
}
```

## Arrays
Arrays in C allow you to store multiple elements of the same data type in a contiguous block of memory.

### Array Declaration and Initialization
```c
#include <stdio.h>

int main() {
    // Declaration and initialization of an integer array
    int numbers[5] = {1, 2, 3, 4, 5};

    // Accessing and printing elements of the array
    for (int i = 0; i < 5; i++) {
        printf("Element %d: %d\n", i, numbers[i]);
    }

    return 0;
}
```

Bonus: An array's variable name is a pointer and it can be dereferenced.

### Dynamic Memory Allocation with `malloc()`

In C, making an array inside a function reserves the memory inside the stack, to make sure it can transfer to any other stackframe, you need to reserve some space in the heap. this is done using the `malloc()` function from the `stdlib.h` library. you only need to return the array pointer to access all that data inside:

```c
#include <stdio.h>
#include <stdlib.h>

int *createDynamicArray(int size) {
    int *arr = (int *)malloc(size * sizeof(int));

    if (arr == NULL) {
        printf("Memory allocation failed\n");
        exit(1); // Exit the program with an error
    }

    for (int i = 0; i < size; i++) {
        arr[i] = i + 1;
    }

    return arr;
}

int main() {
    int *dynamicArr = createDynamicArray(5);

    for (int i = 0; i < 5; i++) {
        printf("%d ", dynamicArr[i]);
    }

    // Free the memory used. IMPORTANT
    free(dynamicArr);

    return 0;
}
```
