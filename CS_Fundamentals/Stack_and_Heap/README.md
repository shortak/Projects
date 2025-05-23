# Overview

This directory contains all my learnings on the fundamentals of CS. 

# The Stack and The Heap

The stack and heap are regions of static and dynamic memory, respecitvely, that programmers can use to further increase their program's efficiency and handle large datasets.

## The Stack

The stack is primarily used for function calls, local variables and flow control (return addresses, for example). 

Some key characteristics of the stack include:

1. Fast (LIFO - Last in, First out)
    - The last piece of data you send to the stack is the first to leave (grows downwards)
2. Automatic management
    - Memory si freed when the function exits
3. Fixed size
    - Stack overflows can occur if the programs tries to access too much memory in the stack
4. Temporary data storage

This uses a portion of the RAM.

## The Heap

The heap is primarily used for dynamic memory allocation. If there is an object whose size is unkown at compile time (either the data set is very large or the size changes while the program runs), you can send that object to the heap. The heap is also used for any data that must persist beyond a function's scope.

Some key characteristics include:

1. Slow
    - Requires allocation and deallocation
2. Manual management
    - "new"/"delete" in C++ or "malloc"/"free" in C
3. Very large memory
4. Flexible size and lifetime

Uses a different portion of the RAM.

```cpp
#include <iostream>

using namespace std;

int main()
{
    int size = 5;

    // Allocate an array and variable on the heap
    int* arr = new int[size];
    int* val = new int(10);

    // Fill the array
    for (int i = 0; i < size; ++i)
    {
        arr[i] = i * 10;
    }

    // Print the array
    for (int i = 0; i < size; ++i)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    // Free the heap memory
    delete[] arr;
    delete val;
}
```

Proper memory allocation and deallocation is demonstrated in the above code.

If the heap is not deallocated, the OS will automatically clear the heap when the program exits. For small, personal use, this is excusable. However, this is not okay if you are using a heap in a larger program that runs in the background.

NOTE: the integer "val" doesn't do anything here other than show how you would handle allocation and deallocation of multiple variables. 

