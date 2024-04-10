# C++

![Alt text](image-3.png)
![Alt text](image-4.png)
![Alt text](image-5.png)
![Alt text](image-6.png)
![Alt text](image-7.png)
![Alt text](image-8.png)
![Alt text](image-9.png)
![Alt text](image-10.png)
![Alt text](image-11.png)
![Alt text](image-12.png)
![Alt text](image-13.png)
![Alt text](image-14.png)
![Alt text](image-15.png)
![Alt text](image-16.png)
![Alt text](image-17.png)
![Alt text](image-18.png)
![Alt text](image-19.png)

### `Operator Overloading`:
- When an operator is overloaded with multiple jobs, it is known as operator overloading.

![Alt text](image-39.png)

The list of operators that cannot be overloaded are :
1. Scope Resolution Operator  ( ::  )    
2. Ternary or Conditional Operator (  ?:  )   
3. Member Access or Dot operator  ( .  )   
4. Pointer-to-member Operator ( .* )  
5.  Object size Operator (  sizeof  ) 
6.  Object type Operator( typeid  ) 
7.  static_cast ( casting operator  )
8.  const_cast (  casting operator  )
9.  reinterpret_cast (  casting operator  )
10. dynamic_cast (  casting operator  ) 

- It is a way to impliment compile time polymorphism.
  - #### ``Rules``:
    - Any symbol can be used as function name:
      - If it is a valid operator in C Language.
      - If it is preceded by operator keyboard.
    - You cannot overload ``sizeof`` and ``?:`` opeartor. 
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
  -  #### example ``operator+()``
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
### ```Friend Function```:
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
### ``Frind Fxn can become friend to more than one class``:
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

``Plus(+) Operator:``
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
### ``Inheritance``:
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

#### ``Multipath inheritance``:
- A derived class with two base classes and these two base classes have one common base class is called multipath inheritance.
-  Ambiguity can arise in this type of inheritance. 
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
- ``Private Mode``: If we derive a subclass from a Private base class. Then both public members and protected members of the base class will become Private in the derived class.
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
    - If there is already a constructor present in  parent class, then this will show error and for this we have to call the parent constructor with default arguments.
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
  -  In case of `destructor`( to delete the resource memory of objects ), firstly the coding of child class gets executed thereafter the parent calss gets executed. ------> opposite to constructor.

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
-  it is used to refer caller object in member function.
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
  -  variables made from new are the exaples of DMA.
  -  Therefore, they gets memory at run time.
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
1. **Method overloading**      -------> function overloading
2.  **Method overriding**             -------> function overrinding    ------> function name as well as its prototype is same both in parent in child class.
3.  **Method Hiding**              --------> function hiding            ------> function name is same, the only difference is in the argumennts.

![Alt text](image-50.png)
![Alt text](image-51.png)
- Their is an error (==> since obj jo hai wo B ka hai to f2 function B mein searrch hoga , lekin yahan pe f2 function to hai lekin prototype different hai esliye errror show karega.)

***Early Binding***:  In this concept, its compiler duty to match the accurate function during the compilation.

![Alt text](image-53.png)

### Function Overloading:
For function overloading all the versions of function must lie on the same class, otherwise we cannot say it's function overloading.

### `Virtual Function`:

- If you have made a pointer of `parent` class then it can point to `child` class too, or you can say it can point to all the descendinmg classes.  But, viceversa is not true.
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
-  For late binding ----------> We take pointer's type as our choice.
-  In case of inheritance, If in any class that has at least one `virtual function`, the compiler will automatically declare a variable within that class as a member, named `*_vptr` (instance member).
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

      -  While performing early binding, the compiler replaces the placeholders, such as `x` with the data type observed in the argument.
      - If we need to perform function overloading only because the number of arguments is the same, and only the data type differs, in such a case, instead of creating different functions, you can create a single function that is generalized enough.
      -  If you pass values of different types, it will show results according to the type of values. This can be achieved using `function templates`.
      -  A `function template` is a generic function, and to create it, we use the template keyword before the function. Inside angular brackets, we use class, and then placeholders like X, so that X can be replaced with the data type.
      -  template<class type> type func_name(type arg1,...)

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
- We can represent the input & output streams by making  the objects of some pre-defined class.
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
- `off` is offset value, relative to the *way* value ios_base::beg, ios_base::cur and ios_base::end.
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
  -  The general form of the throw statement is: `throw exception;`
  -  Throw must be executed either within the try block proper or from any function that the code within the block calls.

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
- ***using*** keyword allows you to import an entire namespaceinto your program with a global scope.
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
    - 	at
    - 	[ ]operator
    - 	front()
    - 	back()
    - 	fill()
    - 	swap()
    - 	size()
    - 	begin()
    - 	end()

- **at()**:
  - This method returns value in the array at the given integer 



## **Points**:
- In object-oriented programming, an object is an instance of a class. A class is a blueprint or a template that defines the structure  and behavior of objects. The process of creating an object involves invoking a special member function known as a constructor. Therefore, it's accurate to say that a `constructor makes an object an object` 
- ***``OOP``*** 
  
  - Treats data as a critical element in the program development and does not allow it to flow freely around the system.
  - It ties the data more closely to the functions that operate on it, and protects it from accidental modification from outside functions.
  - OOP allows decomposition of a problem into a number of entities called ``objects`` and then builds data and functions around these objects.
- ***What is Object-oriented Programming***:
  - Approach that provides a way of modularizing programs by creating partitioned memory area for both data andfunctions that can be used as templates for creating copies of such modules on demand.
-  ``Encapsulation``: The wrapping up of data and functions into a single unit.
-  ``Abstraction``: It refers to the act of representing essential features without including the background details of explanations.
-  Since, the classes use of the data abstraction, they are known as Abstract Data Types (ADT).
-  ``Inheritance``: 
   -  Process by which objects of one class acquire the properties of objects of another class.
   -  In OOP, the concept of inheritance provides the idea of reusability. 
- ``Polymorphism``: 
    - Ability to take more  han one form.
    - Extensively used in implementing inheritance.
- ``Dynamic Building``: Means that the code associated with a given procedure call is not known until the time of the call at run-time. It is associated with polymorohism and inheritance. It is also known as ``late binding``. 
-   The process of making an operator to exhibit different behaviors in different instances is known as ``Operator Overloading`` and using a single function name to perform different types of tasks is known as ``Function Overloading``
-   ``Object Based Programming`` is the style of programming that primarly supports encapsulation and object identity.
    - Major features are:
      - Data encapsulation.
      - Data hinding and access mechanism.
      - Automatic initialisaion and clear-up of objects.
      - Operator overloading.
    - These aree thelanguagesthat suports programming with objects.
    - They donot support inheritance and dynamic building . ``Ada`` is an example.
- ``Generic Pointer:``
  - Pointer that points to any data-type.
  - Declared as normal pointer variable But uses void keywords as the pointer's data type.
  - Examples:
  ```cpp
  void* p = nullpointer;
  /*Declaration of Generic Pointer.*/

  int x = 10;
  p = &x;
  /*Assighning the address of x to the generic pointer.*/
  
  std::cout<< *p /*Prints the value of the integer value*/  
  ```
 - C++ allows the declaration of variable anywhere in the scope.Its disadvantage is we cannot see all the variables at a glance.  
- In C, the global version of a variable cannot be accessed from within the inner block. C++ resolves the problem by introducing a new operator called (``::``) the scope resolution operator.

### new and delete:
- Two unity operators ``new`` and ``delete`` that performed task of allocating and freeing of the memory in a better and easier way. They are also known as the free stored operators.
-  Object created inside a block with ``new`` will remain in existence until it explicitly destroyed by using ``delete`` thus the lifetime of an object is directly under our control and is under related to the block structure of the program.
```cpp
pointer variable = new data-type

delete[size] pointer-variable
```
- new can be used to create a memory space for any data type including user-defined types such as arrays, structures and classes.
- If sufficient memory is not available for allocation in that case new returns are null pointer.
- The new operator offers the following advantages over the function malloc():
  - It automatically computes the size of the data object we need use the operator size of.
  - It automatically returns the correct pointer type so that there is no need to use a typecast
  - It Is possible to initialise the object while creating the memory space
  - Like any other operator new and delete can be overloaded.
#### Manipulators:
-manipurators are operators that are used to format the data display.
- Most common are ``endl`` and ``setw``.
- The use of ``endl`` is same as ``\n``.

### Inline Function:
- An inline function is a function that is expanded in line when id id invoked. The compiler replaces the function call with the corresponding function code.
```cpp
inline function-header
{
  function body
}
```
- All inline function must be defined before they are called.
- Cases in which inline function not works:
  - In cases of loop, switch, goto.
  - If function contain static variable.
  - If the functions are recursive.
- Inline expansion makes a program run faster because the overhead of a function call and return is eliminated.
- It makes the program to take up more memory because the statements that define the inline function are reproduced at each at point where the function is called. So, a trade-off becomes necessary.  

***Default Argumrnt***:
- c++ allows us to call function without specifying all its arguments.
```cpp
float amount (float principal, int period, float rate=0.15);
value = amount (5000,7);  // one-argument missing
value = amount (5000,5,0.12);  // no-missing argument
```
- A function call first matches the prototype having the same number and type of arguments and then calls the appropriate function for execution:
  - Compiler first tries to find the exact match as that of actual argument.
  - In case of non-matching, the compiler uses the integral promotions to the actual arguments 
  As 
    char  ---->  int
    float ---->  double
  - gu  
