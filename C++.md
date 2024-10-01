# C++

### `Facts`:

- **Bjarne Stroustrup** in `1979` at At&T's Bell Laboratory
- Due to the main use of classes, he initially named it **C with Classes**. But, it was renamed as C++ in 1983
- C++ is the world's 4th most used programming language that was inspired by `Simula67` (A computer simulation language)
- **Java** along with major OS of modern times are written in C++

### `Features`:

- C++ is a **middle-level** language that supports the principle of object-oriented paradigm
- C++ joins three separate programming traditions:
  - Procedural Language tradition, represented by C
  - Object-Oriented Language tradition, represented by class enhancements C++ adds to C
  - Generic Programming, supported by C++ templates
    - `Generic Programming`: A paradigm that allows you to write code that works with various data types without the need to rewrite the code for each type. Achieved primarily through the use of `templates`

### `Comparision b/w C and C++`:

- C++ is a subset of the C language
- C++ program can use existing C software libraries
- C follows **_top-down_** approach and adopts **_POP_** while C++ follows **_bottom-top_** approach and adopts **_OOP_** 

### `OOP`:

- OOP is a programming approach which revolves around the concept **_object_**
- `Object`:
  - Any entity in the system that can be defined as a set of properties and set of operations performed using entity property set
  - It allows the decomposition of a problem into several entities called **object** and then builds data and functions around them

### `Properties`:

1. **`Encapsulation`**: Wrapping up of data and fun into a single unit
2. **` Data Hiding`**: The principle of restricting access to the internal state and implementation details of a class, typically achieved by using access specifiers like *private* and *protected*
3. **`Abstraction`**: Hiding the complex implementation details of a system and exposing only the necessary and relevant features
4. **`Polymorphism`**: Allows a function, method, or object to take on many forms, enabling a single interface to represent different underlying data types or classes, typically achieved through inheritance and function overriding
5. **`Inheritance`**: Concept where a new class (derived class) is created from an existing class (base class), allowing the derived class to inherit and optionally override or extend the properties and behaviors (methods) of the base class
6. **` Data Abstraction`**: Process of reducing a body of data to a specific representation of a whole. Classes use the concept of data abstraction, known as _Abstract Data Types_

### `Concept of Classes and Objects`:

- `Class` is a blueprint of an object while `Object` is a run time entity and is an instance of a class
- Class is a description of Object's property set and set of operations
- Creating a class is as good as defining a new data type 
- Class is a means to achieve encapsulation
- Class members are by default private
  
![alt text](image-1.png)
```md
    TOKENS (smallest individual units in a program)
      |
      |__ Types: 1. Keyword
                 2. Identifiers(name of variables, functions that are created by programmers)
                 3. Constant
                 4. String
                 5. Operator
```

### `Output Instruction`:
- `cout`: used to send data/message to monitor
- **cout** is a predefined object
- The operator `<<` is called the insertion or put to the operator

### `Input Instruction`:
- `cin`: used to input data from the keyboard
- **cin** is a predefined object
- The operator `>>` is called the extraction or get-to operator 
---
A/c to ANSI standards of C language, `explicit declaration` of a function is recommended but not mandatory while for C++, explicit declaration of the function is compulsory

### `wchar_t`

- Data type used to represent wide characters
- Designed to store characters that require more than one byte, such as Unicode
- Used when one needs to handle internationalization and different languages in one program

### `Reference Variable`:

- It is an internal pointer, basically another name provided to the same variable.
- Declaration:
  - Proceed with `&` symbol
  - Must be initialized during the declaration
  - Initailzed with already declared variables only

```cpp
int original = 5;
int& ref = original; // 'ref' is a reference to 'original'
```
```cpp
int main() {
    int original = 5;
    int& ref = original; // 'ref' is now a reference to 'original'

    std::cout << "Original: " << original << std::endl; // Outputs 5
    std::cout << "Reference: " << ref << std::endl; // Outputs 5

    // Modify the original variable using the reference
    ref = 10;
    std::cout << "Original after change: " << original << std::endl; // Outputs 10
    std::cout << "Reference after change: " << ref << std::endl; // Outputs 10

    return 0;
}
```

- `Use Cases`

  - **Function Parameters**: Pass variables by reference to avoid copying large structures or to allow the function to modify the argument.
  ```cpp
  using namespace std;
  void increment(int& num)
  {
    num++;
  }

  int main()
  {
    int value = 5;
    increment(value);
    cout << value <<endl;                          // value is now 6
    return 0;
  }
  ``` 
  - **Return Values**: Functions can return references to allow modification of the caller's data
  ```cpp
  int& getElement(int* array, int index)
  {
    return array[index];
  }

  int main()
  {
    int arr[3] = {1, 2, 3};
    getElement(arr, 1) = 10;                  // Modify the second element
    std::cout << arr[1] << std::endl;        // Outputs 10
    return 0;
  }
  ```

### `Inline Function`:
- We use this to eliminate the cost of calls of small functions, C++ proposes a new feature called inline function
- An inline function is a function that is expanded in line where it is involved
- Compiler replaces the function call with the corresponding function code
- Just write `inline` at defining time 
- Its benefit decreases as the function grows in size
- Compiler ignore the inline function in these listed cases:
  - If function contains loops, switch, goto
  - If there is recursion
  - If it contains static variables
```cpp
inline void fun();
int main()
{
  cout << "You are in main\n";
  fun();
}
void fun ()
{
  cout << "You are in fun\n";
}
```
```cpp
int add (int, int);
int main()
{
  int a, b;
  cout << "Enter two numbers";
  cin >> a >> b;
  cout << "Sum is " << add(a, b);
  int c;
  cout << "\nEnter three numbers";
  cin >> a >> b >> c;
  cout << "Sum is " << add(a, b, c);          //----> error: b/c add is defined only for two inputs
}
int add (int x, int y)
{
  return (x + y);
}
---------------------------------------------------------------------------------------------------------------
                                             CORRECTION
---------------------------------------------------------------------------------------------------------------
int add (int, int, int = 0)
{
  return (x + y + z);
}
```

### `Ways to resolve Function Overloading`:
- `Exact Match`: Here, the actual argument exactly matched with the parameter type of the overloaded function
- `Match Through Promotion`: 
  - char, unsigned char, short is promoted to int
  - float is promoted to double
- `Conversion`: If no promotion is found, C++ tries to find a match through standard conversion

### `General Program in C++`:
```cpp
class Complex  // class do not consume memory
{
  private:
    int a, b;  // instance member variables
  public:
    void setData (int x, int y)  // defined within class
    {
      a = x;
      b = y;
    }
    void showData();
}
int main()
{
  Complex c1; // c1 is an object so it consumes memory
  c1.setData(3, 4);    
  c1.showData();
}
void Complex:: showData()
{
  cout << "\na = "<< a <<" b = " << b ;
}
```

### `Function Call by passing object and returning object`: 
```cpp
class Complex
{
  private:
    int a, b;
  public:
    void set_data (int x, int y)
    {
      a = x;
      b = y;
    }
    void show_data()
    {
        cout << "\na = "<< a <<" b = " << b ;
    }
    Complex add (Complex C)
    {
      Complex temp;
      temp.a = a+c.a;
      temp.b = b+c.b;
      return (temp);
    }
};
int main()
{
  Complex c1, c2, c3;
  c1.setd_data(3, 4);
  c2.setd_data(5, 6);
  c3 = c1.add(c2);   // --> c1 calls the add function where c2 passes as the argurmnt. Whatever c1 returns it get stored in the c3
}

```
### `Static Member Variables`:
- It is declared inside the class body and defined outside the class body 
- Also knows as class member variable
- It belongs to whole class not to any specific object
- There will be only one copy of static variable for the whole class
- Any object can use the same copy of class variable

### `Way to access Static Member Variable`:
- `public`:
```cpp
class Account{
  private: 
    int balance;           // instance member variable
    static float roi;     //  static member variable/ class variable
  public: 
    void setBalance (int b)
    {
      balance = b;
    }
};
float Account :: roi = 3.5f;  
void main()
{
  Account a1, a2;
  Account :: roi = 4.5;
}
```
- `private`:
```cpp
class Account
{
  private:
    int balance;
    static float roi;
  public:
    void setBalance (int b)
    {
      balance = b;
    }
    void setroi (float r)
    {
      roi = r;
    }
};
float Account :: roi = 3.5f;
void main()
{
  Account a1, a2;
  a1.setRoi(4.5f);
}
```
  - `setRoi` is instance member function that requires object 
```cpp
class Account
{
  private:
    int balance;
    static float roi;
  public:
    void setBalance (int b)
    {
      balance = b;
    }
    static void setRoi (float r)
    {
      roi = r;
    }
};
float Account :: roi = 3.5f;
void main
{
  Account a1, a2;
  Account:: setRoi (4.5f);
}
```
  - `setRoi` is instance member function that donot requires object 

### `Static Member Function`:
- Also called class member function
- Can be involved with or without object
- Only access static members of the class

### `Constructor`:
- Here we normally used to write those things, we want to add implement just after object creation
- Member function of a class
- Its name is same as that of class name
- It don't have any return type, so we don't add return keyword
- Must be an instance member function, i.e, it can never be static 

### `Way to call CONSTRUCTOR`:
- Constructor is implicitly involved when an object is created
- Used to solve problem of initialisation
```cpp
class Complex{
  private:
    int a, b;
  public:
    Complex()
    {
      cout << "Hello Constructor\n";
    }
};
int main{
  Complex c1, c2, c3;
  return 0;
}

                    // OUTPUT:

/*
Hello Constructor
Hello Constructor
Hello Constructor
*/
```
- What is the problem of initialisation?
  - Why it is called constructor?
    - b/c it makes object an object
  - What is the problem of initialisation?
    - Whenever an object is created it contain a garbage value which means it doesn't represent to someone, called problem of initialisation
- Constructor is a gurranted fxn that is called/ make whenever an object is created
- If we initialise some value to object using constructor, then it doesn't contain garbage value

```cpp
class Complex
{
  private:
    int a, b;
  public:
    Complex (int x, int y)
    {
      a = x;
      b = y;
    }
};
int main()
{
  Complex c1(3, 4), c2;
}
```
- This will give error because default constructor isn't made. Since, we have constructed a constructor
```cpp
class Complex
{
  private:
    int a, b;
  public:
    Complex (int x, int y)     // Parametrized Consgtructor
    {
      a = x;
      b = y;
    }
    Complex (int k)       // Parametrized Constructor
    {
      a = k;
    }
    Complex()   // default constructor
    { }
};
int main()
{
  Complex c1(3, 4), c2, c3(5);
  Commplex c4(c1);  // here, c1 is taken as single entity not the one who is taking two parameters
}
```
- Complex c4 is not of any of types listed above b/c :
  - c1: Takes 2 arguments
  - c2: Take only 1 argument, of type int not complex
    - Therefore we make `copy-constructor` 

```cpp
Complex(int x, int y)
{
  a = x;
  b = y;
}
Complex (int k)
{
  a = k;
}
Complex (Complex C)
{
  a = c.a;
  b = c.b;
};
int main()
{
  Complex c1(3,4), c2, c3(5);
  Complex c4(c1);
}
```
- This will also give error, since c gets it value from c1 which further leds to recurssion here

![Alt text](image-17.png)
![Alt text](image-18.png)
![Alt text](image-19.png)

### `Operator Overloading`:

- When an operator is overloaded with multiple jobs, it is known as operator overloading.

![Alt text](image-39.png)

- List of operators that cannot be overload are :

1. Scope Resolution Operator ( :: )
2. Ternary or Conditional Operator ( ?: )
3. Member Access or Dot operator ( . )
4. Pointer-to-member Operator ( .\* )
5. Object size Operator ( sizeof )
6. Object type Operator( typeid )
7. static_cast ( casting operator )
8. const_cast ( casting operator )
9. reinterpret_cast ( casting operator )
10. dynamic_cast ( casting operator )

- It is a way to impliment compile time polymorphism.
  - #### `Rules`:
    - Any symbol can be used as function name:
      - If it is a valid operator in C Language.
      - If it is preceded by operator keyboard.
    - You cannot overload `sizeof` and `?:` opeartor.

### FOR BINARY OPERATOR:

- Two operands are namely: caller object and argument.
- In Binary Operator the left operand is the caller object. Like in the 2nd example c3 = c1+c2 , c1 is the caller object.

```cpp
class Complex
{
  private:
   int a,b;
  public:
   void setData ( int x, int y )
   {
    a = x, b = y;
   }
   void showData()
   {
    cout<<"\na = "<<a<<"b = "<<b;
   }
   Complex add ( Complex c )
   {
    Complex temp;
    temp.a = a + c.a;
    temp.b = b + c.b:
    return (temp);
   }
};
void main()
{
  Complex c1, c2, c3;
  c1.setData(3,4);
  c2.setData(5,6);
  //c3 = c1 + c2;------> give error because it is non-preemptive type
  c3 = c1.add(c2);    // Here,c1 calls add function in which c2 is passed as an argument, whatever gets return is passed to the c3.
}
```

- We can use an operator symbol in function name, but only by writing operator before it.
  - #### example `operator+()`
- We can even call them without using dot operator.

```cpp
class Complex
{
  private:
   int a,b;
   public:
   void setData ( int x, int y)
   {
    a = x, b = y;
   }
   void showData ()
   {
    cout<<"\na = "<<a<<"b = "<<b;
   }
   Complex operator +( Complex c)
   {
    Complex temp;
    temp.a = a + c.a;
    temp.b = b + c.b:
    return (temp);
   }
};
void main()
{
  Complex c1, c2, c3;
  c1.setData(3,4);
  c2.setData(5,6);
  c3 = c1 + c2;
  return 0;
}
```

### `Operator *` Overloading:

```cpp
#include <iostream>
using namespace std;
class Multiplication
{
private:
    int n1, n2;

public:
    void set_number(int num1,int num2)
    {
        n1 = num1;
        n2 = num2;
    }
    void show_number()
    {
        cout << " Numbers for multiplications are: " << n1 << " and " << n2 << endl;
    }
    Multiplication operator*(Multiplication m)
    {
        Multiplication temp;
        temp.n1 = n1;
        temp.n2 = n2;
        cout << "\nMultiplication is " << (temp.n1 * temp.n2) << endl;
        return temp;
    }
};
int main()
{
    Multiplication M, m;
    M.set_number(2, 4);
    M.show_number();
    m = M.operator*(M); //  M*M(simply)
    return 0;
}
```

### FOR UNIARY OPERATOR:

- Its operand is caller object.

```cpp
class Complex
{
  private:
   int a,b;
   public:
   void setData ( int x, int y)
   {
    a = x, b = y;
   }
   void showData ()
   {
    cout<<"\na = "<<a<<"b = "<<b;
   }
   Complex operator -( )
   {
    Complex temp;
    temp.a = - a ;
    temp.b = - b :
    return (temp);
   }
};
int main()
{
  Complex c1, c2;
  c1.setData(3,4);
  c2 = c1.operator-();// also -c1();
  c2.showData();
  return 0;
}
```

### Overloadig of unary operator ++(Pre and Post)

- Whenever you call pre and post-increment operators as functions then there is a chance of confusion for the compiler to decide between them. Therefore in c++ we pass an int argument in case of post increment operator

```cpp
class Integer
{
  private:
    int x;
  public:
    void setData ( int a )
    {
      x = a;
    }
    void showData ()
    {
      cout<<"x = "<<x;
    }
    Integer operator++()  //pre-increment
    {
      Integer i;
      i.x = ++x;
      return (i);
    }
    Integer operator++(int) // post-increment
    {
      Integer i;
      i.x = x++;
      return (i);
    }
};
void main()
{
  Integer i1, i2;
  i1.setData(3);
  i1.showData();
  i2 = i1++;  // i2 = i1.operator++();
  i1.showData();
  12.showData();
  return 0;
}
```

### `Friend Function`:

- Friend Function is not a member function of a class to which it is a friend.
- Friend Function is declared in the class with friend keyboard.
- It must be definition outside the class to which it is friend.

```cpp
class Complex
{
  private:
     int a, b;
  public:
    void set_data ( int x, int y )
    {
      a = x, b = y;
    }
    void showData ()
    {
      cout<<"\na"<<a<<" b"<<b;
    }
    friend void fun (Complex c);
};
void fun ()
{
  cout<<"Sum is "<<c.a+c.b;
}
void main ()
{
  Complex c1;
  c1.set_data();
  fun(c1);
  return 0;
}
```

### `Frind Fxn can become friend to more than one class`:

```cpp
class B;
class A
{
  private:
    int a;
  public :
    void setData (int x)
    {
      a = x;
    }
    friend void fun(A,B);
}
class B
{
  private :
    int b;
  public:
    void setData (int y)
    {
      b = y;
    }
    friend void fun (A,B);
};
void fun (A o1, B o2)
{
  cout<<"sum is "<<o1.a+o2.b;
}
int main()
{
  A obj1;
  B obj2;
  obj1.setData(2);
  obj2.setData(3);
  fun(obj1,obj2);
  return 0;
}
```

### Overloading of functions using Friend Function:

`Plus(+) Operator:`

```cpp
class Complex
{
  private:
    int a,b;
  public:
    void setData (int x, int y)
    {
      a = x;
      b = y;
    }
    void showData()
    {
      cout<<"\na="<<a<<" b="<<b;
    }
    friend Complex operator+ ( Complex X, Complex Y );
};
Complex operator+(Complex X, Complex Y)
{
  Complex temp;
  temp.a = X.a+Y.a;
  temp.b = X.b+Y.b;
  return (temp);
}
int main()
{
  Complex c1, c2, c3;
  c1.setData(3,4);
  c2.setData(5,6);
  c3 = c1+c2; // c3 = operator+(c1,c2);
  c3.showData();
  return 0;
}
```

### Overloading of unary operator as a friend function:

```cpp
class Complex
{
  private:
    int a, b;
  public:
    void setData (int x, int y)
    {
      a = x; b = y;
    }
    void showData ()
    {
      cout<<"\na="<<a<<" b="<<b;
    }
    friend Complex operator-(Complex);
};
Complex operator-(Complex)
{
  Complex temp;
  temp.a=-X.a;
  temp.b=-Y.b;
  return (temp);
}
int main()
{
  Complex c1, c2;
  c1.setData (3,4);
  c2=-c1; /*c2 = operator-(c1)*/
  c1.showData();
  c2.showData();
}
```

### Overloading of insertion and Extraction operator

```cpp
class Complex
{
  private:
    int a, b;
  public:
    void setData (int x, int y)
    {
      a = x;
      b = y;
    }
    void showData ()
    {
      cout<<"\na="<<a<<" b="<<b;
    }
    friend ostream& operator<<(ostream&, Complex);
    friend istream& operator>>(istream&, Complex);
};
ostream&  operator <<(ostream & dout, Complex C)
{
  cout<<"\na="<<C.a<<" b="<<C.b;
}
istream& operator>>(istream &din, Complex &C)
{
  cin>>C.a>>C.b;
  return (din);
}
int main()
{
  Complex c1;
  cout<<"Enter a complex number";
  cin>>c1;
  cout<<"You entered";
  cout<<c1<<C2; // operator<<(cout,c1);
}
```

#### Member function of one class can become friend to another class:

```cpp
class A
{
  public:
  void fun()
  {     }
  void foo ()
  {     }
};
class B
{
  // friend void A: (to make all functions of class A friend.)
  friend void A::fun();
  friend void A::foo();
};
void fun()
{

}
```

### `Inheritance`:

- It is a process of inheriting properties and behaviours of existing class into a new class. The capability of a class to derive properties and characteristics from another class is called Inheritance.
- Existing class = old class = Parent class = Base class
- New class = Child class = Derived Class
- The derived class now is said to be inherited from the base class.
- Inheritance is one of the most important features of Object-Oriented Programming.
- When a base class is privately inherited by the derived class, public members of the base class becomes the private members of the derived class and therefore, the public members of the base class can only be accessed by the member functions of the derived class. They are inaccessible to the objects of the derived class.
- On the other hand, when the base class is publicly inherited by the derived class, public members of the base class also become the public members of the derived class. Therefore, the public members of the base class are accessible by the objects of the derived class as well as by the member functions of the derived class.

```markdown
### Syntax:

class Base_Class
{

};
class Derived_Class : Visibility_Mode Base_Class
{

};

Example:
class Car
{

};
class SportsCar : public Car
{

};
```

#### Types of Inheritance

- Single Inheritance.
- Multilevel Inheritance.
- Multiple Inheritance.
- Hierarchical Inheritance.
- Hybrid Inheritance.

#### `Single Inheritance`:

- In single inheritance, a class is allowed to inherit from only one class. i.e. one subclass is inherited by one base class only.

![Alt text](image-24.png)
![Alt text](image-38.png)

#### `Multilevel Inheritance`:

- In this type of inheritance, a derived class is created from another derived class.

![Alt text](image-25.png)
![Alt text](image-31.png)

#### `Multiple Inheritance`:

- Multiple Inheritance is a feature of C++ where a class can inherit from more than one class. i.e one subclass is inherited from more than one base class.

![Alt text](image-26.png)
![Alt text](image-30.png)

#### `Hierarchical Inheritance`:

- In this type of inheritance, more than one subclass is inherited from a single base class. i.e. more than one derived class is created from a single base class.

![Alt text](image-27.png)
![Alt text](image-29.png)

#### `Hybrid (Virtual) Inheeritance`:

- Hybrid Inheritance is implemented by combining more than one type of inheritance. For example: Combining Hierarchical inheritance and Multiple Inheritance.

![Alt text](image-28.png)

#### `Multipath inheritance`:

- A derived class with two base classes and these two base classes have one common base class is called multipath inheritance.
- Ambiguity can arise in this type of inheritance.

```cpp
// C++ program demonstrating ambiguity in Multipath
// Inheritance

#include <iostream>
using namespace std;

class ClassA {
  public:
    int a;
};

class ClassB : public ClassA {
  public:
    int b;
};

class ClassC : public ClassA {
  public:
    int c;
};

class ClassD : public ClassB, public ClassC {
  public:
    int d;
};

int main()
{
    ClassD obj;

    // obj.a = 10;                  // Statement 1, Error
    // obj.a = 100;                 // Statement 2, Error

    obj.ClassB::a = 10;   // Statement 3
    obj.ClassC::a = 100; // Statement 4

    obj.b = 20;
    obj.c = 30;
    obj.d = 40;

    cout << " a from ClassB  : " << obj.ClassB::a;
    cout << "\n a from ClassC  : " << obj.ClassC::a;

    cout << "\n b : " << obj.b;
    cout << "\n c : " << obj.c;
    cout << "\n d : " << obj.d << '\n';

    /*
    In the above example, both Class-B and Class-C inherit Class-A, they both have a single copy of Class-A. However Class-D inherits both Class-B and Class-C, therefore Class-D has two copies of Class-A, one from Class-B and another from Class-C.
    If we need to access the data member of Class-A through the object of Class-D, we must specify the path from which a will be accessed, whether it is from Class-B or Class-C, bcz compiler can’t differentiate between two copies of Class-A in Class-D.*/
}
```

#### `There are two wayas to Avoid this Ambiguity`:

1. Avoiding ambiguity using the scope resolution operator: Using the scope resolution operator we can manually specify the path from which data member a will be accessed
2. Avoiding ambiguity using the virtual base class:

```cpp
#include<iostream>

class ClassA
{
  public:
    int a;
};

class ClassB : virtual public ClassA
{
  public:
    int b;
};

class ClassC : virtual public ClassA
{
  public:
    int c;
};

class ClassD : public ClassB, public ClassC
{
  public:
    int d;
};

int main()
{
    ClassD obj;

    obj.a = 10;       // Statement 3
    obj.a = 100;      // Statement 4

    obj.b = 20;
    obj.c = 30;
    obj.d = 40;

    cout << "\n a : " << obj.a;
    cout << "\n b : " << obj.b;
    cout << "\n c : " << obj.c;
    cout << "\n d : " << obj.d << '\n';
}
```

- According to the above example, Class-D has only one copy of Class-A, therefore, statement 4 will overwrite the value of a, given in statement 3.

### Visibility Modes:

- `Private Mode`: If we derive a subclass from a Private base class. Then both public members and protected members of the base class will become Private in the derived class.
- `Protected Mode`: If we derive a subclass from a Protected base class. Then both public members and protected members of the base class will become protected in the derived class.
- `Public Mode`: If we derive a subclass from a public base class. Then the public member of the base class will become public in the derived class and protected members of the base class will become protected in the derived class.
- The private members in the base class cannot be directly accessed in the derived class, while protected members can be directly accessed.

![Alt text](image-32.png)

### Constructor & Destructor in Inhritance:

- ### Some Rules:
  - Child class constructors call the parent class constructor.
  - Order of execution of constructor in innhritance: from `parent to child`.
  - Order of call of constructor in inheritance: from `child to parent`.

```cpp
class A
{
  public:
   A() // Default Constructor
   {  }
};
class B : public A
{
  public:
   B():A() // Way to call parent constructor.
   {  }
   /*
   B(){} -----> here compiler itself write the calling statement for the default constructor of parent class. i.e. B():A(){ }
   */
};
/*
Here, ""In B():A(){ }"" -----> this emplies that firstly the Child constructor gets called after that the control passed to the parent class, in this way firstly the execution of parent constructor takes place.
*/
int main()
{
  B obj;
}
```

- If we don't make child class constructor, then compiler makes the default constructor and calls the parent default constructor.
  - If there is already a constructor present in parent class, then this will show error and for this we have to call the parent constructor with default arguments.
- If we don't write the constructor for the parent class then, by default compiler calls the default constructor.

#### Way to pass the arguments using constructor:

```cpp
class A
{
  int a;
  public:
   A(int k)
   {
    a = k ;
   }
};
class B : public A
{
  int b;
  public:
   B(int x, int y):A(x)
   {
    b = y;
   }
};

int main()
{
  B obj(1,2);
}
```

- In case of `destructor`( to delete the resource memory of objects ), firstly the coding of child class gets executed thereafter the parent calss gets executed. ------> opposite to constructor.

```cpp
class A
{
  int a;
  public:
   A(int k)
   { a = k ;}
   ~A() { };
};
class B : public A
{
  int b;
  public:
   B(int x, int y):A(x)
   { b = y; }
   ~B(){ };
};
/*
At first the destructor of child gets called and after that the destructor of parent gets called.
*/

int main()
{
  B obj(1,2);
}
```

### `Object Pointer`: A pointer containing the address of an object.

example:

```cpp
class Box
{
  private:
   int l, b, h;
  public:
   void setDimension (int x, int y, int z)
   {
    l = x, b = y, h = z;
   }
   void showData ()
   {
    cout<<"\nl = "<<l<<" b = "<<" h = ";
   }
};
int main()
{
  Box *p, smallBox;
  p = &smallBox;
  p->setDimension(12,10,5)// same as smallBox.setDimension(12,10,5);
  p->showDimension()// same as smallBox.showDimension()
  return 0;
}

```

![Alt text](image-49.png)

### **This Pointer**:

- this is a keyboard.
- this is a local object pointer in every instance member function containig address of the caller object.
- this pointer cannot be modify.
- it is used to refer caller object in member function.
- this pointer contains the address of the caller object.

```cpp
class Box
{
  private:
   int l, b, h;
  public:
   void setDimension (int l, int b, int h)
   {
     // name  conflict happens,as both the l are considered the local variables.
     this->l = l, this->b = b, this->h = h;
   }
   void showData ()
   {
    cout<<"\nl = "<<l<<" b = "<<" h = ";
   }
};
int main()
{
  Box smallBox;
  smallBox.setDimension(12,10,5);
  smallBox.showDimension()
  return 0;
}
```

### **new & delete**:

- `new`:

  - variables made from new are the exaples of DMA.
  - Therefore, they gets memory at run time.

  ```cpp

  int *p = new int;
  float *q = new float;
  Complex *ptr = new Complex;
  float *q = new float[5];
  ```

- `delete`:
  ```cpp
   delete p;
   delete []p;
  ```

### `Method Overhiding`:

1. **Method overloading** -------> function overloading
2. **Method overriding** -------> function overrinding ------> function name as well as its prototype is same both in parent in child class.
3. **Method Hiding** --------> function hiding ------> function name is same, the only difference is in the argumennts.

![Alt text](image-50.png)
![Alt text](image-51.png)

- Their is an error (==> since obj jo hai wo B ka hai to f2 function B mein searrch hoga , lekin yahan pe f2 function to hai lekin prototype different hai esliye errror show karega.)

**_Early Binding_**: In this concept, its compiler duty to match the accurate function during the compilation.

![Alt text](image-53.png)

### Function Overloading:

For function overloading all the versions of function must lie on the same class, otherwise we cannot say it's function overloading.

### `Virtual Function`:

- If you have made a pointer of `parent` class then it can point to `child` class too, or you can say it can point to all the descendinmg classes. But, viceversa is not true.
- used in case of function overriding.
- In case of early binding, two cases happens:
  1. For object:- Here, compiler decides as per the type of object that what functions to bind.
  2. For Pointers:- Here, compiler decides according to caller of pointer class that what functions to bind.

```cpp

class A
{
  public:
   void f1() { }
};
class B: public A
{
  public:
   void f1() { } // function overriding
   void f2() { }
};
int main()
{
      //  For Pointers:
  A *p, o1;
  B o2;
  p = &o2;
  p->f1();  // A

      //   For Objects:
  A *p, o1;
  B o2;
  p = &o2;
  o2.f1();  //  B
}
/*
Child ke object ke liye child ki pointer chale; lekin hm jaise parent ke pointer k through calling  karte hai, child k object bnane ke to bhi child k nhi chal tha balki pointer k chal rha.

Solution: To avoid early binding. i.e, Replace void f1() { } by ------> virtual void f1() {}
*/
```

#### **Virtual Function Working Concept**:

![Alt text](image-54.png)
![Alt text](image-55.png)
![Alt text](image-56.png)

- For late binding ----------> We take pointer's type as our choice.
- In case of inheritance, If in any class that has at least one `virtual function`, the compiler will automatically declare a variable within that class as a member, named `*_vptr` (instance member).
- In a child class, a separate `vptr` is not created because it is inherited.
- Compiler makes a static array (called `vtable`) whose address is stored in vptr.
- This static array is made for each class.
- In every class that contains a virtual function, and in all its descending classes the compiler will create a vtable; a `vtable` is a static array of virtual functions
- They contain address of only virtual function.

### **Abstract in C++**:

A class that contains at least one pure virtual function is called an `abstract class`, and an object of such a class is never instantiated.

### Pure Virtual Functions:

- A do nothing function is a pure virtual function.
- `example`: virtual void fun( )= 0;
- A class that has functions with no implementation cannot have an object; to use such a class, a child class must be created.
- When creating its child class, it is necessary to perform function overriding so that it can call those functions.
- If early binding occurs, the parent class can execute; therefore, we make it virtual. To determine what the pointer is pointing to, we consider it as the base—refer to the virtual function concept for more information.

### **Templet in C++**:

- The keyword template is used to define function template and class template.
- It is a way to make your function or class generalise as far as data type is concern.

  - #### 1. `FUNCTION TEMPLATE`:

    - While performing early binding, the compiler replaces the placeholders, such as `x` with the data type observed in the argument.
    - If we need to perform function overloading only because the number of arguments is the same, and only the data type differs, in such a case, instead of creating different functions, you can create a single function that is generalized enough.
    - If you pass values of different types, it will show results according to the type of values. This can be achieved using `function templates`.
    - A `function template` is a generic function, and to create it, we use the template keyword before the function. Inside angular brackets, we use class, and then placeholders like X, so that X can be replaced with the data type.
    - template<class type> type func_name(type arg1,...)

```cpp
#include <iostream>
using namespace std;
/*            "WITHOUT TEMPLATE"
int big(int a, int b)
{
    if (a > b)
        return (a);
    else
        return (b);
}
double big(double a, double b)
{
    if (a > b)
        return (a);
    else
        return (b);
}
int main()
{
    cout << big(4, 5);
    cout << big(5.6, 3.4);

    return 0;
}
*/
        // "WITH TEMPLATE"
template <class X> X big(X a, X b)
{
    if (a > b)
        return (a);
    else
        return (b);
}
/*          "TEMPLATE FOR TWO DATATYPES"
template <class X> X big(X a, X b)
{
    if (a > b)
        return (a);
    else
        return (b);
}
*/
int main()
{
    cout << big(4, 5);
    cout << big(5.6, 3.4);

    return 0;
}
```

#### 2. `CLASS TEMPLATE`:

- Class template is also known as generic class.
- template<class type> class class_name{.....}

```cpp
#include <iostream>
using namespace std;
class ArrayList
{
private:
    struct ControlBlock
    {
        int capacity;
        int *arr_ptr;
    };
    ControlBlock *s;

public:
    ArrayList(int capacity)
    {
        s = new ControlBlock;
        s->capacity = capacity;
        s->arr_ptr = new int[s->capacity];
    }
    void addElement(int index, int data)
    {
        if (index >= 0 && index <= s->capacity - 1)
            s->arr_ptr(index) = data;
        else
            cout << "\nArray index is not valid";
    }
    void viewElement(int index, int &data)
    {
        if (index >= 0 && index <= s->capacity - 1)
            data = s->arr_ptr(index);
        else
            cout << "\nArray index is not valid";
    }
    void viewList()
    {
        int i;
        for (i = 0; i < s->capacity; i++)
            cout << " " << s->arr_ptr[i];
    }
};
int main()
{
    int data;

    ArrayList list1(4);
    list1.addElement(0, 32);
    list1.addElement(1, 41);
    list1.addElement(2, 55);
    list1.viewList();

    return 0;
}
```

### FIle Handling In C+++:

- #### `Data Persistence`:

  - Life of Data.
  - To make the data to exist after the complition of programe, we need file handling.

  ![Alt text](image-57.png)

- #### `Streams`:
  ![Alt text](image-58.png)
- **Output Stream**: Data flows from variable to file.
- **Input Stream**: Data flows from file to variables.
- All those functions that manages the input and output strings are defined in a class in c++
- We can represent the input & output streams by making the objects of some pre-defined class.
- We can represent the output stream using the object of `ofstream class`
- We can represent the input stream using the object of `ifstream class`
- To take input we make an object of ifstream function.
- To make output we make an object of ofstream function.
- For file handling we use: ifstream, fstream, ofstream.
- For file handling we use the header file `fstream`.

![Alt text](image-59.png)

```cpp
#include<fstream>
#include<iostream>

int main()
{
  ofstream fout;
  fout.open("myfile.dat");
  fout<<"hello";
  return 0;
}
```

```cpp
#include<iostream>
#include<fstream>

int main()
{
  ifstream fin;
  char ch;
  fin.open("myfile.dat");
  fin>>ch;
  while(!fin.eof())
  {
    cout<<ch;
    fin>>ch;
  }
  fin.close();
  return 0;
}
```

- #### **File Opening Mode**:
  ```cpp
  /*
  ios::in       ------>    input/read
  ios::out      ------>    output/write
  ios::app      ------>    append
  ios::ate      ------>    update
  ios::binary   ------>    binary
  */
  ```
  - `Where to write modes:`
    - As a second argument of open() function.
    ```cpp
    ofstream fout;
    fout.open("file name",file_opening_mode);
    ifstream fin;
    fin.open("file name",file_opening_mode);
    fstream file;
    fout.open("file name",file_opening_mode);
    ```
    - Text mode is the default opening mode.
    - Binary mode can be specified with
    ```cpp
    ios::binary
    ```

### tellp()

- Defined in ostream class.
- Its prototype is -`streampos tell`;
- Returns the position of the current character in the output stream.

```cpp
#include<iostream>
#include<fstream>
using namespace std;

int main()
{
  ifstream fin;
  char ch;
  fin.open("abc.txt");
  int pos;
  pos = fin.tellg();
  cout<<pos;
  fin<<ch;
  pos = fin.tellg();
  cout<<pos;
  fin>>ch;
  pos = fin.tellg();
  cout<<pos;
  return 0;
}

/*
OUTPUT:  012;
*/
```

```cpp

#include<iostream>
#include<fstream>

int main()
{
  ofstream fout;
  char ch;
  int pos;
  pos = fout.tellp;
  cout<<pos;
  fout<<"mysirg";
  pos = fout.tellp();
  cout<<pos;
  fout.close();
  return 0;

}
```

### seekg():

- Defined in istream class.
- Its prototype is
  - istream & seekg(streampos pos);
  - istream & seekg(streamoff off, ios_base::seekdir way);
- `pos` is new absolute position within the stream (relative to the begining).
- `off` is offset value, relative to the _way_ value ios_base::beg, ios_base::cur and ios_base::end.

  ```cpp
  #include<iostream>
  #include<fstream>
  using namespace std;

  int main()
  {
    ifstream fin;
    fin.open("abc.txt");
    cout<<fin.tellg();
    cout<<"\n"<<(char)fin.get;
    cout<<(char)fin.get;
    cout<<"\n"<<fin.tellg();
    fin.seekg(6);
    cout<<"\n"fin.tellg();
    cout<<"\n"(char)fin.tellg();
    cout<<"\n"fin.tellg();
    fin.seekg(2,ios_base::cur);
    cout<<"\n"<<fin.tellg();

    return 0;
  }
  ```

  ```cpp
  #include<iostream>
  #include<fstream>
  using namespace std;

  int main()
  {
    ofstream fin;
    fout.open("abc.txt",ios::ate);
    cout<<fout.tellp();
    fout<<"ABCDEFG";
    cout<<fout.tellp();
    fout.close();
    return 0;
  }
  ```

```cpp
  #include<iostream>
  #include<fstream>
  using namespace std;

  int main()
  {
    ofstream fout;
    fout.open("abc.txt",ios::ate|ios::app);
    cout<<fout.tellp();
    fout.seekp(2,ios_base::beg);
    cout<<fout.tellp();
    fout.close();
    return 0;
  }
```

### Initializers in C++:

- **Intializer List** is used to initialize data members of a class.
- The list of members to be initialized is indicated with constructor as a comma separated list followed by a colon.

```cpp
  // Constructor:
#include<iostream>
class Dummy
{
  private:
   int a,b;
   cost int x;
  public:
   Dummy():x(5)
   { }
};
void fun()
{
  const int k = 5;
  k++;
}
```

```cpp
    // Reference Variable:
#include<iostream>
class Dummy
{
  private:
   int a,b;
   cost int x;
   int &y;
  public:
   Dummy(int &n):x(5),y(n)
   { }
};
int main()
{
  int m = 6;
  Dummy d1(m);
}
void fun()
{
  const int k = 5;
  k++;
}
```

- `Why Initialisers ?`
  - There are situations where initialization of data members inside constructor doesn't work and Initialiser List must be used.
  - For initialization of non-static const data members.
  - For initialization of reference members.

### Deep Copy & Shallow Copy:

- `Using Copy Constructor`:-
  After the initialization of object like **Dummy d1=d2;**

```cpp
#include<iostream>
using namespace std;
class Dummy
{
  private:
    int a, b;
  public:
    void setData(int x, int y)
    {
      a = x;
      b = y;``
    }
    void showData()
    {
      cout<<"\na = "<<a<<" b = ";
    }
    /*Hoe Compiler Makes copy Constructor:
    Dummy (Dummy &d)
    {
      a = d.a;
      b = d.b;
    }
    */
};
int main()
{
  Dummy d1;
  d1.setData(3,4);
  Dummy d2 = d1;  // Using Copy Constructor;
  d2.showData();
  return 0;
}
```

- `Using Implicit Copy assighnment Operator`:- (Also called **Default assighnment operator**) After we make the class; i.e, on the next line
  **Dummy d1;
  d1 = d2;**

```cpp
#include<iostream>
using namespace std;
class Dummy
{
  private:
    int a, b;
  public:
    void setData(int x, int y)
    {
      a = x;
      b = y;``
    }
    void showData()
    {
      cout<<"\na = "<<a<<" b = ";
    }
};
int main()
{
  Dummy d1;
  d1.setData(3,4);
  Dummy d2;
  d2 = d1; // Using Implicit Copy assighnment Operator
  d2.showData();
  return 0;
}
```

#### `Shallow Copy`: Creating copy of object by copying data of all member variable.

#### `Deep Copy`: Creating an object by copying data of another object along with the values of memory resources resides outside the object but handeled by that object.

### `Type Conversions`:

- #### Primitive type to Class type:

```cpp
#include<iostream>
class Complex
{
  private:
   int a, b;
  public:
    void setData (int x, int y)
   {
     a = x;
     b = y;
   }
   void showData()
   {
    cout<<"\na = "<<a<<" b = "<<b;
   }
};
int main()
{
  Complex c1;
  int x = 5;
  //  c1 = x;   -------> error
  c1.showData();
  return 0;
}
```

`CORRECTION`: Through Constructors

```cpp
#include<iostream>
class Complex
{
  private:
   int a, b;
  public:
    Complex() {   }
    Complex(int k)
    {
      a = k;
      b = 0;
    }
    void setData (int x, int y)
   {
     a = x;
     b = y;
   }
   void showData()
   {
    cout<<"\na = "<<a<<" b = "<<b;
   }
};
int main()
{
  Complex c1;
  int x = 5;
  c1 = x;   // c1.Complex(x);
  c1.showData();
  return 0;
}
```

- #### Class type to Primitive type:
  ![Alt text](image-60.png)

```cpp
#include<iostream>
using namespace std;

class Complex
{
 private:
  int a, b;
 public:
  void setData(int x, int y)
  {
    a = x;
    b = y;
  }
  void showData()
  {
    cout<<"\na = "<<a<<" b = "<<b;
  }
};
int main()
{
  Complex c1;
  c1.setData(3,4);
  c1.showData();
  int x;
  x = c1; // --------> error
  cout<<"\nx = "<<x;
  return 0;
}
```

`CORRECTION`:

- Use `casting operator`:
  ```cpp
      // how to use casting operator.
  operator (type)
  {
    ....
    return (type-data);
  }
  ```

```cpp
#include<iostream>
using namespace std;

class Complex
{
 private:
  int a, b;
 public:
  void setData(int x, int y)
  {
    a = x;
    b = y;
  }
  void showData()
  {
    cout<<"\na = "<<a<<" b = "<<b;
  }
  operator int()
  {
    return (a);
  }
};
int main()
{
  Complex c1;
  c1.setData(3,4);
  c1.showData();
  int x;
  x = c1; // x = c1.operator int ()
  cout<<"\nx = "<<x;
  return 0;
}
```

- #### **One Class type to another class type**:

![Alt text](image-61.png)
![Alt text](image-62.png)

```cpp
#include<iostream>
using namespace std;

class Item
{
  private:
    int a, b;
  public:
   void showData()
   {
    cout<<"\na = "<<a<<" b = "<<b;
   }

};
class Product
{
  private:
   int m, n;
  public:
   void setData (int x, int y)
   {
    m = x;
    n = y;
   }
};
int main()
{
  Item i1;
  Product p1;
  p1.setData(3,4);
  i1 = p1;
  i1.showData();

  return 0;
}
```

`CORRECTION`:

```cpp
#include<iostream>
using namespace std;

class Product
{
  private:
   int m, n;
  public:
   void setData (int x, int y)
   {
    m = x;
    n = y;
   }
   int getM()
   {
    return (m);
   }
   int getN()
   {
    return (n);
   }
};

/*

Why did we change the position of Product class with Item class?

We change the position of classes because of the error message as the members gteM & getN are not accessible directly because of the undecleration of them initially;

#include<iostream>
using namespace std;

int getM();
int getN();

class Item
{
  private:
    int a, b;
  public:
   void showData()
   {
    cout<<"\na = "<<a<<" b = "<<b;
   }
   Item() { };
   Item(Product p)
   {
    a = p.getM();
    b = p.getN();
   }

};
class Product
{
  private:
   int m, n;
  public:
   void setData (int x, int y)
   {
    m = x;
    n = y;
   }
   int getM()
   {
    return (m);
   }
   int getN()
   {
    return (n);
   }
};

int main()
{
  Item i1;
  Product p1;
  p1.setData(3,4);
  i1 = p1;
  i1.showData();

  return 0;
}

*/
class Item
{
  private:
    int a, b;
  public:
   void showData()
   {
    cout<<"\na = "<<a<<" b = "<<b;
   }
   Item() { };
   Item(Product p)
   {
    a = p.getM();
    b = p.getN();
   }

};

int main()
{
  Item i1;
  Product p1;
  p1.setData(3,4);
  i1 = p1;
  i1.showData();

  return 0;
}
```

### **Exception Handling**:

- Exceptiom is nay abnormal behaviour, run time error.
- Exceptions are off beat situation in your programwhere your program should ready to handle it with appropriate response.
- C++ provides a built-in error handling mechanism that is called exception handling.
- Using exception handling, you can more easily manage and response to runtime errors.
- `try, catch, throw`:
  - Program statements that you want to monitor for exceptions are contained in a **try** block.
  - If any exception occurs within the try block, it is throw (using **throw**)
  - The exception is caught, using **catch**, and processed.
- We have to write catch block just after the try block.-----> (it is necessary)

![Alt text](image-63.png)

```cpp
#include<iostream>
using namespace std;

int main()
{
  cout<<"Welcome";
  try
  {
    throw 10;
    cout<<"\nIn Try";
    /*Not executed, because after the throw whatever be the statements gets ignored by the compiler.*/
  }
    catch (int e)
    {
      cout<<"\nException no: "<<e;
    }
    cout<<"\nLast Line";
    return 0;

}

```

```cpp
/*
When only throw statement is there like:
 //try
 //{
   throw 10;
   cout<<"\nIn throw";
// }
//  catch (int e)
//  {
//      cout<<"\nExceptio//n no: "<<e;
//  }
   cout<<"\nLast Line";
    return 0;

```

`Then`:

- Whenever throw is there but no catch is present, then automatically termiante functions gets execute and this function calls abirt function hence, program finished

![Alt text](image-64.png)
![Alt text](image-65.png)

`Another Case`:

```cpp
try
{
  throw 10;
    cout<<"\nIn Try";
    catch (double e)
    {
      cout<<"\nException no: "<<e;
    }
}
```

`PROBLEM`: double is present instead of int, compiler shows:
![Alt text](image-66.png)
Means non-appropriate catch is present

`ANOTHER CASE`: More than one catch statements are present:

```cpp
try
{
  throw 10;
  cout<<"\nIn Try";
}
catch (double e)
  {
    cout<<"\nException no: "<<e;
  }
catch (int e)
  {
    cout<<"\nException no: "<<e;
  }
cout<<"\nLast Line";
```

- Here, compiler matches the throw with the rescpective data tye i.e, here with the int version.

- #### **Catch**:
  - When an exception is caught, arg will recieve its value.
  - If you don't need access to thr exception itself, specify only type in the catch clause-arg is optional.
  - Any type of data can be caught, including classes that you create.
- #### **Throw**:
  - The general form of the throw statement is: `throw exception;`
  - Throw must be executed either within the try block proper or from any function that the code within the block calls.

### **Dynamic Constructor**:

- Constructor can allocate dynamically created memory to the object.
- Thus, object is going to use memory region, which is dynamically created by constructor.

### **namespace in C++**:

- Namespace is a container for identifiers.
- It puts the names of its members in a distinct space so that they don't conflict with the names in other namespaces or global namespace.
- `How to create namespace`?
  - Namespace definition doesn't terminates with a semicolon like in class definition.
  - The namespace definition must be done at global scope, or nested inside another namespace.
  - You can use an alias name for your namespace name, for ease of use
    - namespace ms = `Myspace`;

```cpp
namespace Myspace
{
  // Declarations
}
```

- There can be `unnamed` namespaces too.

```cpp
namespace
{
  //  declarations
}
```

- A namespace definition can be continued and extende over multiple files, they are not redefined or overridden.

![Alt text](image-67.png)

### Accessing members of namespace:

- Any name (identifier) declared in a namespace can be explicitly specified using the namespace's name and the scope resolution `::` operator with the identifier.

```cpp
#include<iostream>
using namespace std;
namespace Myspace
{
  int a;
  void f1;
  class Hello
  {
    public:
      void hello()
      {
        cout<<"Hello";
      }
  };
}

void Myspace::f1()
{
  cout<<"In f1";
}

int main()
{
  Myspace::a = 5;
  Myspace::Hello obj;
  obj.hello();
  Myspace::f1();
}
```

### The `using` directive:

- **_using_** keyword allows you to import an entire namespaceinto your program with a global scope.
- It can be used to import a namespace into another namespace or nay progtam.

```cpp
#include<iostream>
using namespace std;
namespace Myspace
{
  int a;
  void f1;
  class Hello
  {
    public:
      void hello()
      {
        cout<<"Hello";
      }
  };
}
using namespace Myspace;
void Myspace::f1()
{
  cout<<"In f1";
}

int main()
{
  a = 5;
  Hello obj;
  obj.hello();
  f1();
}
```

### Virtual Destructor in C++:

### Nested Class:

- Class inside a class is called nested class
- A nested class is a member and such has the same access rights as any other members.
- The members of an enclosing class have no special access to members of a nested class; the usual access rules shall be obeyed

```cpp

#include<iostream>
using namespace std;
class Student
{
  private:
    int rollno;
    char name[20];
    class Address
    {
      private:
       int houseno;
       char street[20];
       char city[20];
       char state[30];
       char pincode[7];
      public:
        void setAddress(int h, char *s, char *c, char *st, char *p)
        {
          houseno = h;
          strcpy(street,s);
          strcpy(city,c);
          strcpy(state,st);
          strcpy(pincocde,p)
        }
      };
      Address add;
  public:
    void setRollno(int r)
    {
     rollno = r;
    }
    void setName(char *n)
    {
     strcpy(name,n);
    }
    void setAddress(int h, char *s, char *c, char *st, char *p)
    {
     add.setAddress(h,s,c,st,p);
    }
    void show Student ()
    {
     cout<<"Student Data"<<endl;
     cout<<rollno<<" ";
     cout<<name<<" ";
     add.showAddress();
    }
};
int main()
{
  Student::Address a1;
  Student s1;
  s1.setRollno(100);
  s1.setName("Rahul");
  s1.setAddress(301,"hanuman gali",bhopal","462042","MP");
  s1,showStudent();
}

```

### **Introduction to STL in C++**:

- STL is Standard Template Library.
- It is a powerful set of C++ template classes.
- At the core of the C++ Standard Template Library are following three well-structured components.
  - Containers
  - Algorithms
  - Iterators

### **Containers**:

- Containers are used to manage collections of objects of a certain kind.
- Container library in STL provide containers that are used to create data structure like arrays, linked list, trees, etc.
- These containers are generic, they can hold elements of any data types.
  - example: **vector** can be used for creating dynamic arrays of char, integer, float and other types.

### **Algorithms**:

- Algorithma act on containers. They provide the means by ehich you will perform initialization, sorting, searching, and transforming of the contents of containers.
- Algorithms library contains built in functions that perform complex algorithms on the data structures.
  - Example:
    - One can reverse a range with reverse() function, sort a range with sort() function, search in a range with binary_search() and so on.
- Algorithm library provides abstraction, i.e you don't necessarily need to know how the algorithm works.

### **Iterators**:

- Iterators are used to step through the elements of collections of objects. These collections may be containers or subsets of containers.
- Iterators in STL are used to point to the containers.
- Iterators actually acts as a bridge between containers and algorithms.
  - Example: sort() algorithm have two parameters, starting iterator and ending iterator, now sort() compare the elements pointed by each of yhese iterators and arrange them in sorted order, thus it does not matter what is the type of the container and some sort() can be used on different types of containers.

### **Containers**:

- Container library is a collection of classes.
- The containers are implemented as generic class templates.
- Containers helps us to implement and replicate simple and complex data structures very easilyy like arrays, list, trees, associative arrays and many more.
- Containers can be used to hold different kind of objects.

![Alt text](image-68.png)

![Alt text](image-69.png)

- When we use list containers to implement linked list we just have to include the list header file and use list constructor to initialise the list.

```cpp
#include<iostream>
#include<list>
int main()
{
  list<int>mylist;
}
```

### **Array**:

- Array is a liners collection of similar elements.
- Array containers in STL provides us the implementation of static array.

```cpp
  //Use header array:
   #include<array>
  // how to call:
  array<object_type,array_size>array_name;
  int main()
  {
    // Assignment of values during declaration:
    array<int,4>odd_numbers = {2,4,6,8};
  }
```

- It creates an empty array of **object_type** with maximum size of **array_size.**
- Member Functions:

  - Following are the important and most used member functions of array template:
    -     at
    -     [ ]operator
    -     front()
    -     back()
    -     fill()
    -     swap()
    -     size()
    -     begin()
    -     end()

- **at()**:
  - This method returns value in the array at the given integer

---
