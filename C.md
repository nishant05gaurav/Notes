## `C Language`:

#### `Importance of C Language`:

- Fast Execution
- Based on POP (Procedural Oriented Programming)
- Most popular programming language
- Oracle, Core Libraries of Android, MySQL, almost every device driver, Major part of WebBrowser (all are written in C)
- Unix Operating System (developed in C)

![alt text](https://imgur.com/hqNC1XT.png)
![alt text](https://imgur.com/TpiibDq.png)

### `Constants`:

- These are basically data (any information)
  ![alt text](https://imgur.com/hKe18zl.png)

---

### `Variables`:

- Name of memory location where we store data, called **variables**
- Any combination of alphabet, digit and underscore
- A valid variable name cannot start with a digit

---

### `Instructions`:

- Programming statements are called **instructions**
- Instructions are commands
- **Types**:
  - Data Type Declaratation
  - Input Output Instruction
  - Arithmetic Instruction
  - Control Instruction
- **Data Type**:
  - These are the types of data
  - _5 keyboards_ in C Language
  - _Primitive Data Type_:- Collection of keywords and data type

![alt text](https://imgur.com/p1yF6JP.png)

- `unsigned`: used when the value stored will be always +ve
- `flag`: basically flip flops eg: (class A, class B)

---

#### `Escape Sequence`:

- **`\n`** for next line
- **`\t`** for tab space
- **`\b`** for babackspace
- **`\\`** for backslash
- **`\"`** for double quotation
- **`\r`** for shifting positionof cursor to the begining

#### `scanf()`:

- A Predefined function that is used to take data from keyboard and store it in variables
- It takes value untill we press enter
- we use **&** with scanf b/c it is a predefined function which cannot access the value of variable of others fxn but can access
- predominantly _pointer variable_

---

### `Arithmetic Instruction`:

- Instructions that is used to manipulate data using operators.
- `Types`: (**PRICIDENCE RULE**)

  - Unary
  - Arithmetic
  - Bitwise
  - Relational
  - Logical
  - Conditional
  - Assignment

- **`Unary Operator`**:
  - needs only one operands
  - +, -, ++, --, sizeof()
  - `++` : increment operator
    - **pre-increment**: ++x (first increased then value changes)
    - **post-increment**: x++ (first value is as it is then increased) ; least priority even less than assignment operator
  - **sizeof()**:
    - `sizeof (data-type / variable / constant)`
    - Gives the size in bytes
  - _character_ const are treated as integer
  - Real-constant are by deafult of type double (double is more accurate then float)
  - ASCII: American Standard Code for Information Interchange
- **`Arithmetic Operator`**
  - `* / % + -` : left to right precidence.
  - % : Modulus operator gives reminder
- **`Bitwise Operator`**:
  ![alt text](https://imgur.com/lkO5E3L.png)

1. `Right Shift`: **(>>)** shifts towards left
2. `Left Shift`: **(<<)** shifts towards right

- **`Relational Operator`**:
  - <, >, <=, >=
  - == (equal to), != (not equal to)
  - Always yield result either **0** or **1**
  - Every non-zero values is True (1) and Zero is False (0)
- **`Logical Operator`**:
  ![alt text](https://imgur.com/MxM3G6F.png)

- **`Conditional Operator`**:

![alt text](https://imgur.com/6RlLavK.png)

**`Switch Control Instruction`**:

- Use when there are many condition & we have to choose from that
- `switch` followed by an integer/expression to evaluate an integer
- `case` followed by an integer/a character constant

![alt text](https://imgur.com/IqZza81.png)

- **`break`**:
  - used in loops as well as in switch body
  - used to break the normal execution of a loop
- **`continue`**:
  - skip tyhe execution of statemnts after it
  - takes control through the next cucyle of loop

### `Function`:

- Self-contained block of statements that perform a cohernt through task of samekind.
- `OS` calls the **main()** function
- Programme must contains at least one function --> only one function i.e main()
- Function's name must be unique
- Function gets released from RAM once the programe finished
- Function consumes memory only when it is involved and relased from RAM as soon as it finished its job
- A function can only access those variables which are made in their body. for eg: `main` function cannot use variable named in a fxn body. But, can take value of variable from other function
- **TYPES**:
  1. `Predefined`: works without showing what is happening/going. eg: clrscr(), printf(), etc
  2. `Userdefined`: work is shown& it is made by us. eg: add(), sum(), etc

#### `Benefits of Function`:

- Modularization
- Easy to read, debug, modify
- Avoid rewriting of same code over & over
- Better memory utilization
- Creating Reusable Components

`Takes Nothing, Returns Nothing`:

- Neither takes data nor returns data
- **`Interview Points`**:

  - Purpose of _void_ functions: (Modularity, action without input/output)
  - Use cases for _void_ functions: (Initialization, state changes, event handling)
  - Drawbacks of _void_ functions: (Overreliance, difficulty in debugging side effects)
  - Compare and contrast _void_ functions with functions taking parameters and returning values: (Flexibility, modularity, potential efficiency)

  ```c
  void print_welcome_message()
  {
    printf("Welcome to my program!\n");
  }

  int main()
  {
    print_welcome_message();  // Call the void function

      // ... rest of your program
    return 0;
  }
  ```

`Takes Something, Returns Nothing`:

- Functions take value, but don't return

  ```c
  #include <stdio.h>

  void print_doubled(int num)
  {
   int doubled = num * 2;
   printf("The doubled value is: %d\n", doubled);
  }

  int main()
  {
   int value = 10;
   print_doubled(value);  // Call the function to print doubled value
    return 0;
  }
  ```

`Takes Nothing, Returns Something`:

- Function don't takes input, but retorns something.

  ```c
  int get_random_number()
  {
    srand(time(NULL));  // Seed the random number generator (once at program start)
    return rand();     // Generate a random integer
  }
  ```

`Takes Something, Returns Something`:

- Function takes something as well as returns something

  ```c
  #include <stdio.h>

  int add(int x, int y)
  {
   // Function to add two integers
   int sum = x + y;
   return sum;
  }

  int main()
  {
   int a = 5, b = 10;
   int result = add(a, b);  // Call the add function
   printf("The sum of %d and %d is %d\n", a, b, result);
   return 0;
  }
  ```

#### `Recursion`:

- When functions are called repeatedly, they repeatedly consumes memory leaving previous function in paused stage (RAM).
- It's done whenever the base condition is achieved.
- Problems that are solved by the help of recursion, can also be solved by the help of loop but viceversa is incorrect.

![alt text](https://imgur.com/mYG2Chk.png)

### `Array`:

- An array is a fundamental data structure in programming that stores a collection of items of the same data type under a single name
- Also called subscript variable

- ```c
  int main()
  {
    int a[100]; ---> // No. of variables
  }
  ```
  - All have same name "a" but index no. is different 0, 1, 2, 3, ..... 99
  - Accessing way of first array
    - `int a[1000]` ---> index number
    - `int a[0]` ---> index number
  - To put 45 in `a[4]`:
    - `a[4] = 45`;
  - `a[ ]` --> error
  - `a[5]` --> is not an error where 5 is no. of varibales consumes continous memory
  - Ways to assighn value:
    - `int a[5] = {9, 6, 8, 9, 0, 2};`
    - `int a[ ] = {9, 6, 8, 9, 0, 2};`
    - `int a[5] = {9, 6};` --> other values is 0
  - `int a[5] = {9, 6, 8, 9, 0, 2, 3, 45, 90};` ---> if we take values gather than assign, it will show error
- Drawbacks:
  - **Fixed size**: Resizing can be complex or impossible.
  - **Limited data type**: Stores only elements of the same type.

```c
int a[10], i, sum;
float avg;

  pritf("Enter 10 Numbers\n");
    for(i=0; i<9; i++)
    {
      scanf("%d", &a[i]); // &a[i] --> address of index number
    }
    for(i=0; i<9; i++)
    {
     sum = sum + a[i];
    }

  avg = sum/100;
  printf("Average is %f", avg);
```

---

### `2-Dimensional Arrays`:

- No. of variables is "6", This means 1st array will get 3 & 2ns Array will get 3
- Called array of arrays

![alt text](https://imgur.com/97lv8NU.png)

```c
int A[3][3], B[3][3], C[3][3], i, j;

printf("Enter 9 nos. for first matrix\n");
for( i=0; i<=2; i++)
  for( j=0; j<=2; j++)
  {
    scanf("%d",&A[i][j]);
  }
printf("Enter 9 nos. for second matrix\n");
for( i=0; i<=2; i++)
  for( j=0; j<=2; j++)
  {
    scanf("%d",&B[i][j]);
  }

for( i=0; i<=2; i++)
  for( j=0; j<=2; j++)
  {
    C[i][j] = A[i][j] + B[i][j];
    printf("%d",C[i][j]);
  }
  printf("\n");
```

### `Strings`:

- Sequence of characters whose last character is null character.
- ASCII code of null character is 0 (zero).
- If we don't know how much we have to print then we put null character in the last. So, the data by the user gets printed untilnull character

```c
int main()
{
  char s[10] = {'N', 'I', 'S', 'H', 'A', 'N', 'T', '\0'};
  int i;
  for (i=0; i<=8; i++)
  {
    printf("%c",s[i]);
  }

  /* 2nd Method:
  for (i=0; s[i]!='\0'; i++)
  {
    printf("%c",s[i]);
  }

  3rd Method:
  puts(s);
  // Specially used for printing of strings, they do not need special mentions. They automatically transfer cursor to next line after printing.

  4th Method:
  char s[10] = {"NISHANT"};
  int t;
  puts(s);

  5th Method:
  int i;
  printf("%s",s);
  */
}
```

- `puts`: Display only listening at a time & places the cursor to the next line
- `gets`: When we want to print multipple strings

![alt text](https://imgur.com/6tvlVwM.png)

### `Pointers`:

- A Pointer is a varible that stores memory address of another variable
- data_type \*pointer_name;

  ```c
  int  num = 42;
  int *ptr = &num; // ptr stores the memory address of num
  ```

  ![alt text](https://imgur.com/qYFiF2y.png)

- `Extended Concept of Pointers`:

  1. **Level of Indirection (\*)**: Level is defined by counting the number of `*` before the names of variable

  - Example: `**q` --> Level = 2, It contains the address of variable having one less level
    ![alt text](https://imgur.com/Rza9Uo3.png)

  1. `Pointers Arithmetic`:
  2. We can add, multiply or divide two addresses(Substraction is Possible)
  3. We cannot multiply an integer to an address and similarly, we cannot divide an adddress with an integer value.

  ```c
    int a,b;
    int *p, *q;
    p = &a;
    q = &b;

    // (&a + &b) || (p + q)  --> WRONG
    // (&a * 5)  || (&a / 5) --> WRONG
  ```

      3. We can **add/subtract integer to/from an address**:
              `pointer + n = pointer + sizeof(type of pointer) * n`

  ```c
    p + 1
    = &a + 1 // &a = 1000
    = 1002 --> b/c a is of two bits whose two addresses are defined
  ```

      4. `Subtraction`:
         - Possible only when both are of same type
         - `Pointer1 - Pointer2 = Subtraction / sizeof(type of pointer)`

  ```c
    q - p = 1020 - 1000;
          = 20 --> WRONG
          = 10 --> CORRECT
          --> b/c 10 blocks of int i.e, 2 bytes are q & p are int

    // (&a + &b) || (p + q)  --> WRONG
    // (&a * 5)  || (&a / 5) --> WRONG
  ```

- `Application`: **Call by Reference**

```c
void fun(int x, int y);   // declaration
int main()
{
  int a, b;
  ......
   code
  ......
  fun(a, b);  // function called  (a,b)--> Actual Arguments {whatever written in parenthesis during fxn call}
}

void fun (int x, int y)  // definition   --> x,y: Formal Argument {whatever written in parenthesis during fxn defining}
{
  ......
   code
  ......
}

// any change in x and y values will not alter the values of a and b
```

- Call by reference is same as call by address
- Reference means address
- When formal arguments are pointer variables
  eg:
  ````c
      void swap (int *x, int *y)
      {
        t = *x;
        *x = *y;
        *y = t;
      }
      ```
  ````
- `USES`:

  - Allows low-level memory access and dynamic memory allocation
  - Used in case of representing two-dimensional and multi-dimensional arrays.
  - Provides faster access to memory and even stores the addresses of functions
  - Essential for building complex data structures like linked lists, trees, graphs.
  - Handles file and allocate memory dynamically (during run-time via malloc, calloc, etc)

- Why do we use `&` in `scanf()`?
  - B/c scanf is a predefined fxn which cannot access the value of variable of other funxtion but can access its address. Here,scanf has predominantly pointer variables.
- `Pointers with Array`:
  - Array always consumes memory location in continous fashion
  - example: `int a[4]` --> int consumes 2 byte memory in 16 bit architecture
    - Hence, &a[0] = 1000; &a[1] = 1002; and so on...
  - Pointers when incremented, laways point to immediately next bloxk of its own type.

![alt text](https://imgur.com/feZpKdN.png)

- `Pointers with string`:

  - string is stored in char array
  - char pointer can point to char block

  ```c
  char s[10] = "COMPUTER";
  char *p;
  p = &s[0];

  ```

  - Name of array will represent the address of first block of array
    - print(s) ---> 1000
      - &s[0]

  ```c
  // Length of string using pointer:
  int length (char *);
  char* reverse (char *);
  int main()
  {
    printf("%d", length("Computer"));
    printf("%s", reverse("Computer"));
  }
  char* reverse (char *)
  {
    int l, i;
    char t;
    for( l = 0; *(p+l) != '\0'; l++){
    for(i = 0; i < l/2; i++)
    {
      t = *(p+i);
      *(p+i) = *(p+l-1-i);
      *(p+l-1-i) = t;
    }
    return (p);
    }
    int length (char *p){
      int i;
      for(i = 0; *(p+i) != '\0'; i++)
      return (i);
    }
  }
  ```

  ```c
  // Reverse a string:
  char* reverse (char*)
  int main()
  {
    printf("%s", reverse("Computer"));
  }
  char* reverse (char *p)
  {
    int l, i;
    char ch;
    for(l = 0 ; *(p+l) != '\0'; l++){
      for(i = 0 ; i < l/2; i++){
        ch = *(p+i);
        *(p+i) = *(p+l-1-i);
        *(p+l-1-i) = ch;
      }
    }
    return p;
  }
  ```
### `Structure in C`:
- It is a way to group variables (dis-similar elements)
- Defining structures means creating new data-type
  ```c
    // Definition:
    struct tag // (tag == data-type)
    {
     // variable declaration:
    }
  ---

- No memory is consumed for definition of structure
- It can be defined both inside and outside the function

```c
struct date // data-type (int, char, float, etc)
{
  int d, m, y;  // member variable
}

void main()
{
  struct date today, d1;
  today.d = 11;     //
  today.m = 6;      //  can also be assigned as struct data today = {11, 6, 2023};
  today.y = 2023;   //

  d1.d = today.d;   //
  d1.m = today.m;   //  other way, d1 = today;
  d1.y = today.y;   //

  // If we want to add data from user:

  printf("Enter todays date");
  scanf("%d/%d/%d", &d1.d, &d1.m, &d1.y);
  printf("Date: %d/%d/%d", d1.d, d1.m, d1.y);
}

// Other Way:
void main()
{
  struct date today = {6, 1, 1965}, d1;
  d1 = today;
  printf("Enter today's date");
  // ...
  // ...
  // same
  // ...
  // ...
      :memory allocation:
  x--------------------------x
  | x----x   x----x   x----x |
  | | d  |   | m  |   |  y | |
  | x----x   x----x   x----x |
  x--------------------------x
}
```
- When scanf works it shows the data or user get the input
- At the time of gets it doesn't fluid empty input buffer. So, again next scanf works leaving gets keyword
- Hence, we use `fflush(stdin);`
- Many a time, we also need to attach underdenoted function in our program anywhere so that our compiler don't say- "**Floating Point Formats Not Linked**"
as
  ```c
    link float(){
      float a = 0, *b;
      b = &a;  // causes emulator to be linked
      a = *b;  // supresses the warning that variable not found
    }
  ```

### `Union In C`:
- Union is similar to structure, except it allows you to define variable that share storage
- Defining `unions` means creating new data type
![alt text](https://imgur.com/DpgpuAj.png)
![alt text](https://imgur.com/mdxjyHZ.png)
- Union members are accessed in the same manner as we access structure member
- Union is generally used in low-level programming 

### `Dynamic Memory Allocation`:

- **`SMA`**: Static Memory Allocatoion; Decision had been taken that what amnount of memory be consumed for variable at the time of compilation

> int a; --> memory will be given when it will run but quantity of memory is decided during the time of compilation. It will also be decidecd the life span of variable i.e, variable will exist only when they are gets callled and destroyed when after the program ends. During declaration statement

- DMA variable have no name, they are accessed by their address
- It is used when we don't know how many variables sholuld be made during computer programming
  - `malloc()` 
  - `calloc()`
  - `realloc()`
  - `free()`

- `malloc( )`:(**Memory Allocation**)
  - Allocates a block of memory of specified size (in bytes)
  - Returns a pointer to the allocated memory
  - Memory is uninitialized
  - Syntax: `void* malloc(size_t size);`
  - Must cast the returned pointer to the appropriate type
  > It allocates memory from the `heap`. Memory should be freed after use to prevent memory leaks

- `calloc( )`: (**Contiguous Allocation**)
  - Allocates memory for an array of elements, initializing each to zero
  - Takes two arguments: number of elements and size of each element
  - Initializes allocated memory to zero
  - Syntax: `void* calloc(size_t num, size_t size);`
  > Preferred over `malloc()` when you want zero-initialized memory

- `realloc( )`: (**Reallocate Memory**)
  - Resizes previously allocated memory block
  - Can either expand or shrink the memory block
  - Syntax: `void* realloc(void* ptr, size_t size);`
  - If the memory block is moved, data is preserved
  > Used to dynamically adjust memory requirements during runtime

- `free( )`: (**Free Allocated Memory**):
  - Deallocates previously allocated memory
  - Releases memory back to the heap
  - Syntax: `void free(void* ptr);`
  > Always free memory to avoid memory leaks and dangling pointers

- Memory of DMA not get released until programme ends

### `Enumerators`:

- It gives us an opportunity to convert own data type and define what value the variable of this data type can take

![alt text](image-15.png)
- We can write programme without the help of enumerators but, enumerators help in writing clear codes and simplify programming:

![alt text](image-17.png)

### `typedef`:
- Its a keyword which is use to give a new name to the existing data type.
![alt text](image-18.png)

### `Pre-Processor`: 
- Programme which performs before the compilation
- `#` is called pre-processor directive
- It only notices `#` started statements
- Each pre-processing directive must be on its own line
- The word after `#` is called pre-processor command
![alt text](image-20.png)

### `# include`:
- One of the most popular pre-processor command
- It can be used to include any file content to your source file
> `#include <file_name>` ||  `#include "file_name"` || `#include"c:\myprog\clang\list.h"`
- Firstly it is done by pre-processor
- After that, Work is done by compiler

### `#define`:
- The `#define` directive defines an identifier and a character sequence (a set of characters) that eill be substituted for the identifier each time it is encountered in the source file 
```c
#define (identifier ≅ macro_name) (character_sequence)

#define pi 3.14; // this means whenever we write pi in our coding pre-processor will replace it to 3.14
                 // That means, compiler will only see 3.14 at the place of pi  
```
```c
#define PI 3.24
int main(){
  int r; 
  float a;
  printf("Enter a number");
  scanf("%d", &r);
  a = PI * r * r;
  printf("Area of circle is %f", a);
}

#define SUM(a, b) a+b
int main(){
  printf("Sum of 3 and 4 is %d", SUM(3, 4));
}

#define ARANGE (a>25 && a<50)
        FOUND  printf("Virus is here!");

#define PRODUCT(a, b) a*b
int main(){
  printf("Product of 3+2 and 4-6 is %d", PRODUCT(3+2, 4-6));  // Output: 5 as (3+2*4-6)
}
```

### `#undef`: Used to  remove or undefined macros
```c
#define CLOSE(0)
..........                          // CLOSE word will be recognized
..........
..........

#undef CLOSE
..........                          // CLOSE word won't be recognized
..........
..........
```

- When is it best to use `macros` with arguments and when is it better to use a `function`?
  - **`Macro`**: 
    - Make the program run faster but increase the program size
    - Consume more space
    - Takes less time as they have already been expanded and placed in the source code before compilation
  - **`Function`**: 
    - Make the program slow and compact
    - Consumes the same amount of space
    - Take time and slow down the program
- `Macro`  can be split into multiple lines with a `\` backslash present at the end of each line 
> #define HLINC for(i = 0; i < 9; i++)  \  printf("%c", 196);

- `#if`, `#endif`, `#ifdef`, `#ifndef`:

![alt text](image-27.png)

- `#pragma directive`:
  -  Used to turn on/off certain features
  -  Vary a/c to compiler

-  `#pragma startup/ pragma exit`:
   -  Allows us to specify functions that are called upon program startup (before **main()** ) or program exit (just before the program terminates)

### `##`:
- The `##` operator is used with the `#define macro`
- Using ## concentrates what's before it with what's after it
  - Concentration of **a`##`b** is `ab`
```c
#define ACTION(a, b) a##b+a*b
int main()
{
  printf("%d", ACTION(3, 4));
}
---
// OUTPUT
// ACTION(3, 4)
// --> 34 + 3 * 4 = 46
```

### `File Handling`:
- File handling is read and write of data
  - If we make a variable in a program and we want that after execution of the programme, the data 
