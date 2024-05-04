# Cheat Sheat : C++ Syntax

## Table of Contents
1. [Hello World](#hello-world)
2. [Variables](#variables)
3. [Data Types](#data-types)
4. [Operators](#operators)
5. [Control Structures](#control-structures)
6. [Functions](#functions)
7. [Classes](#classes)
8. [Input/Output](#inputoutput)
9. [Pointers](#pointers)
10. [Memory Management](#memory-management)
11. [Preprocessor Directives](#preprocessor-directives)
12. [Standard Template Library (STL)](#standard-template-library-stl)
13. [Miscellaneous](#miscellaneous)

## Hello World
You can write a simple Hello World program in C++ like this:
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```
But you can also write the same program like in C:
```cpp
#include <iostream>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

## Variables
This is the same as in C. But in C++ you can initialize variables like in C or like this:
```cpp
    [type] [name]([value]);
```
- Example:
    ```cpp
        int a = 5; // like in C
        float b(3.14); // typical C++ initialization b = 3.14
        char c('a'); // typical C++ initialization c = 'a'
    ```

## Data Types
- **Basic Data Types**:
    Same as in C. But in C++ you can use `bool` for boolean values.
    | Type | Description | Size | Range |
    | --- | --- | --- | --- |
    | bool | Boolean value | 1 byte | true = 1, false = 0 |

- **Derived Data Types**:
    Same as in C. But in C++ you can use `string` for strings and you have also `class`.
    - **String**:
        ```cpp
            std::string [name] = "[value]";
        ```
        - Example:
            ```cpp
                std::string myString = "Hello";
            ```
        or
        ```cpp
            using namespace std;
            string [name] = "[value]";
        ```
        - Example:
            ```cpp
                using namespace std;
                string myString = "Hello";
            ```
    - **Class**:
        ```cpp
            class [name] {
                [members]
            };
        ```
        - Example:
            ```cpp
                class MyClass {
                    public:
                        int myNum;
                        string myString;
                };
            ```
## Operators
All operators are the same as in C.

## Control Structures
All control structures are the same as in C.

## Functions
Functions are the same as in C. But in C++ you can use default arguments and function overloading.
- **Default Arguments**:
    ```cpp
        [return type] [name]([type] [name] = [value]) {
            [code]
        }
    ```
    - Example:
        ```cpp
            int myFunction(int x = 5) {
                return x;
            }
        ```
- **Function Overloading**:
    ```cpp
        [return type] [name]([type] [name]) {
            [code]
        }
        [return type] [name]([type] [name], [type] [name]) {
            [code]
        }
    ```
    - Example:
        ```cpp
            int myFunction(int x) {
                return x;
            }
            int myFunction(int x, int y) {
                return x + y;
            }
        ```
## Classes
Classes are like structures in C. But you have more features like `public`, `private` and `protected` that you can use to protect your data, not like in C where everything is public.
- **Class Declaration
    ```cpp
        class [name] {
            public:
                [members]
            private:
                [members]
            protected:
                [members]
        };
    ```
    - Example:
        ```cpp
            class MyClass {
                public:
                    int myNum;
                    string myString;
                private:
                    int myPrivateNum;
            };
        ```
- **Class Definition**
    ```cpp
        [return type] [name]::[member] {
            [code]
        }
    ```
    - Example:
        ```cpp
            int MyClass::myFunction() {
                return myNum;
            }
        ```
- **Constructor**
    ```cpp
        [name]([parameters]) {
            [code]
        }
    ```
    - Example:
        ```cpp
            MyClass::MyClass(int x, string y) {
                myNum = x;
                myString = y;
            }
        ```
    The constructor has always the same name as the class.
- **Destructor**
    ```cpp
        ~[name]() {
            [code]
        }
    ```
    - Example:
        ```cpp
            MyClass::~MyClass() {
                std::cout << "Destructor called" << std::endl;
            }
        ```
    The destructor has always the same name as the class but with a `~` in front of it.
    You can also use destructors to free memory, close files, etc.
    This is important when you use dynamic memory allocation in your class.
- **Inheritance**
    ```cpp
        class [name] : [visibility] [base class] {
            [members]
        };
    ```
    - Example:
        ```cpp
            class MyOtherClass : public MyClass {
                public:
                    int myOtherNum;
            };
        ```
    All the members of the base class are inherited by the derived class but the derived class can also have its own members. If you want to access directly the members of the base class you need to use `protected` or `public` inheritance.
    `private` inheritance is also possible but you can't access the members of the base class.
- **Polymorphism**
    Polymorphism is the ability to have many methods with the same name but with different implementations.
    If you want to use polymorphism you need to use virtual functions in the base class.

    - Example:
        ```cpp
            class MyClass {
                public:
                    virtual void myFunction();
            };

            class MyOtherClass : public MyClass {
                public:
                    void myFunction() override;
            };

            void MyClass::myFunction() {
                std::cout << "MyClass" << std::endl;
            }

            void MyOtherClass::myFunction() {
                std::cout << "MyOtherClass" << std::endl;
            }
        ``` 
    In this example, the `myFunction` method is a virtual function in the base class. The `override` keyword is used to tell the compiler that the function is supposed to override a function in the base class. If the function does not exist in the base class, the compiler will give you an error.

## Input/Output
Input and output are the same as in C. But in C++ you can use `cin` and `cout` for input and output.
- **Input**
    ```cpp
        std::cin >> [variable];
    ```
    - Example:
        ```cpp
            int x;
            std::cin >> x;
    ```
- **Output**
    ```cpp
        std::cout << [value];
    ```
    - Example:
        ```cpp
            int x = 5;
            std::cout << x;
        ```

## Pointers
Pointers are the same as in C. But in C++ you can use `nullptr` instead of `NULL`.
And you can also use `this` to refer to the current object, like in classes.
- **this**
    ```cpp
        [return type] [name]([parameters]) {
            this->[member] = [value];
        }
    ```
    - Example:
        ```cpp
            void MyClass::myFunction(int x) {
                this->myNum = x;
            }
        ```
- **nullptr**
    ```cpp
        [type] *[name] = nullptr;
    ```
    - Example:
        ```cpp
            int *ptr = nullptr;
        ```
## Memory Management
Memory management is the same as in C. But in C++ you can use `new` and `delete` to allocate and deallocate memory.
- **new**
    ```cpp
        [type] *[name] = new [type];
    ```
    - Example:
        ```cpp
            int *ptr = new int;
        ```
    `new` is like `malloc` in C but it also calls the constructor of the object if it exists.
- **delete**
    ```cpp
        delete [name];
    ```
    - Example:
        ```cpp
            delete ptr;
        ```
    `delete` is like `free` in C but it also calls the destructor of the object if it exists.
## Preprocessor Directives
Preprocessor directives are the same as in C. But in C++ you can use `#include <iostream>` to include the input/output library.
## Standard Template Library (STL)
The Standard Template Library (STL) is a library that provides you with a lot of useful functions and classes.
- **Vector**
    - **include**
        ```cpp
            #include <vector>
        ```
    - **Declaration**
        ```cpp
            std::vector<[type]> [name];
        ```
        - Example:
            ```cpp
                std::vector<int> myVector;
            ```
    - **Initialization**
        ```cpp
            std::vector<[type]> [name] = {[values]};
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
            ```
    - **Add Element**
        ```cpp
            [name].push_back([value]);
        ```
        - Example:
            ```cpp
                myVector.push_back(6);
            ```
    - **Remove Element**
        ```cpp
            [name].pop_back();
        ```
        - Example:
            ```cpp
                myVector.pop_back();
            ```
    - **Access Element**
        ```cpp
            [name][index];
        ```
        - Example:
            ```cpp
                std::cout << myVector[0];
            ```
        or you can use the `at` method:
        ```cpp
            [name].at([index]);
        ```
        - Example:
            ```cpp
                std::cout << myVector.at(0);
            ```
        This method is safer because it checks if the index is in the range of the vector and if you store pointers in the vector it will obligate you to use this method.
    - **Size**
        ```cpp
            [name].size();
        ```
        - Example:
            ```cpp
                std::cout << myVector.size();
            ```
    - **Iterate**
        ```cpp
            for ([type] [name] : [name]) {
                [code]
            }
        ```
        - Example:
            ```cpp
                for (int i : myVector) {
                    std::cout << i << std::endl;
                }
            ```
        or you can use the `begin` and `end` methods:
        ```cpp
            for (std::vector<int>::iterator it = myVector.begin(); it != myVector.end(); ++it) {
                std::cout << *it << std::endl;
            }
        ```
        or you can use the `rbegin` and `rend` methods to iterate in reverse:
        ```cpp
            for (std::vector<int>::reverse_iterator it = myVector.rbegin(); it != myVector.rend(); ++it) {
                std::cout << *it << std::endl;
            }
        ```
- **Map**
This is like a dictionary in Python.
    - **include**
        ```cpp
            #include <map>
        ```
    - **Declaration**
        ```cpp
            std::map<[key type], [value type]> [name];
        ```
        - Example:
            ```cpp
                std::map<int, std::string> myMap;
            ```
    - **Initialization**
        ```cpp
            std::map<[key type], [value type]> [name] = {[{key, value}]};
        ```
        - Example:
            ```cpp
                std::map<int, std::string> myMap = {{1, "one"}, {2, "two"}, {3, "three"}};
            ```
    - **Add Element**
        ```cpp
            [name][key] = [value];
        ```
        - Example:
            ```cpp
                myMap[4] = "four";
            ```
    - **Remove Element**
        ```cpp
            [name].erase([key]);
        ```
        - Example:
            ```cpp
                myMap.erase(4);
            ```
    - **Access Element**
        ```cpp
            [name][key];
        ```
        - Example:
            ```cpp
                std::cout << myMap[1];
            ```
    - **Size**
        ```cpp
            [name].size();
        ```
        - Example:
            ```cpp
                std::cout << myMap.size();
            ```
    - **Iterate**
        ```cpp
            for (std::pair<[key type], [value type]> [name] : [name]) {
                [code]
            }
        ```
        - Example:
            ```cpp
                for (std::pair<int, std::string> i : myMap) {
                    std::cout << i.first << " => " << i.second << std::endl;
                }
            ```
- **Set**
This is like a list in Python. But it doesn't allow duplicates.
    - **include**
        ```cpp
            #include <set>
        ```
    - **Declaration**
        ```cpp
            std::set<[type]> [name];
        ```
        - Example:
            ```cpp
                std::set<int> mySet;
            ```
    - **Initialization**
        ```cpp
            std::set<[type]> [name] = {[values]};
        ```
        - Example:
            ```cpp
                std::set<int> mySet = {1, 2, 3, 4, 5};
            ```
    - **Add Element**
        ```cpp
            [name].insert([value]);
        ```
        - Example:
            ```cpp
                mySet.insert(6);
            ```
    - **Remove Element**
        ```cpp
            [name].erase([value]);
        ```
        - Example:
            ```cpp
                mySet.erase(6);
            ```
    - **Size**
        ```cpp
            [name].size();
        ```
        - Example:
            ```cpp
                std::cout << mySet.size();
            ```
    - **Iterate**
        ```cpp
            for ([type] [name] : [name]) {
                [code]
            }
        ```
        - Example:
            ```cpp
                for (int i : mySet) {
                    std::cout << i << std::endl;
                }
            ```
- **Queue**
This is a queue data structure. It is like a list but you can only add elements at the end and remove elements from the beginning. So it is a FIFO (First In First Out) data structure.
    - **include**
        ```cpp
            #include <queue>
        ```
    - **Declaration**
        ```cpp
            std::queue<[type]> [name];
        ```
        - Example:
            ```cpp
                std::queue<int> myQueue;
            ```
    - **Initialization**
        ```cpp
            std::queue<[type]> [name];
        ```
        - Example:
            ```cpp
                std::queue<int> myQueue;
            ```
    - **Add Element**
        ```cpp
            [name].push([value]);
        ```
        - Example:
            ```cpp
                myQueue.push(1);
            ```
    - **Remove Element**
        ```cpp
            [name].pop();
        ```
        - Example:
            ```cpp
                myQueue.pop();
            ```
    - **Access Element**
        ```cpp
            [name].front();
        ```
        - Example:
            ```cpp
                std::cout << myQueue.front();
            ```
    - **Size**
        ```cpp
            [name].size();
        ```
        - Example:
            ```cpp
                std::cout << myQueue.size();
            ```
- **Stack**
This is a stack data structure. It is like a list but you can only add elements at the end and remove elements from the end. So it is a LIFO (Last In First Out) data structure.
    - **include**
        ```cpp
            #include <stack>
        ```
    - **Declaration**
        ```cpp
            std::stack<[type]> [name];
        ```
        - Example:
            ```cpp
                std::stack<int> myStack;
            ```
    - **Initialization**
        ```cpp
            std::stack<[type]> [name];
        ```
        - Example:
            ```cpp
                std::stack<int> myStack;
            ```
    - **Add Element**
        ```cpp
            [name].push([value]);
        ```
        - Example:
            ```cpp
                myStack.push(1);
            ```
    - **Remove Element**
        ```cpp
            [name].pop();
        ```
        - Example:
            ```cpp
                myStack.pop();
            ```
    - **Access Element**
        ```cpp
            [name].top();
        ```
        - Example:
            ```cpp
                std::cout << myStack.top();
            ```
    - **Size**
        ```cpp
            [name].size();
        ```
        - Example:
            ```cpp
                std::cout << myStack.size();
            ```
- **Algorithm**
This is a library that provides you with a lot of useful functions.
    - **include**
        ```cpp
            #include <algorithm>
        ```
    - **Sort**
        ```cpp
            std::sort([begin], [end]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {5, 2, 3, 1, 4};
                std::sort(myVector.begin(), myVector.end());
            ```
    - **Reverse**
        ```cpp
            std::reverse([begin], [end]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                std::reverse(myVector.begin(), myVector.end());
            ```
    - **Find**
        ```cpp
            std::find([begin], [end], [value]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                std::vector<int>::iterator it = std::find(myVector.begin(), myVector.end(), 3);
                if (it != myVector.end()) {
                    std::cout << "Element found in myVector: " << *it << std::endl;
                } else {
                    std::cout << "Element not found in myVector" << std::endl;
                }
            ```
    - **Binary Search**
        ```cpp
            std::binary_search([begin], [end], [value]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                if (std::binary_search(myVector.begin(), myVector.end(), 3)) {
                    std::cout << "Element found in myVector" << std::endl;
                } else {
                    std::cout << "Element not found in myVector" << std::endl;
                }
            ```
    - **Copy**
        ```cpp
            std::copy([begin], [end], [destination]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                std::vector<int> myVectorCopy(5);
                std::copy(myVector.begin(), myVector.end(), myVectorCopy.begin());
            ```
    - **Max Element**
        ```cpp
            std::max_element([begin], [end]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                std::vector<int>::iterator it = std::max_element(myVector.begin(), myVector.end());
                std::cout << "Max element in myVector: " << *it << std::endl;
            ```
    - **Min Element**
        ```cpp
            std::min_element([begin], [end]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                std::vector<int>::iterator it = std::min_element(myVector.begin(), myVector.end());
                std::cout << "Min element in myVector: " << *it << std::endl;
            ```
    - **Count**
        ```cpp
            std::count([begin], [end], [value]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                int count = std::count(myVector.begin(), myVector.end(), 3);
                std::cout << "Number of 3 in myVector: " << count << std::endl;
            ```
    - **Sum**
        ```cpp
            std::accumulate([begin], [end], [initial value]);
        ```
        - Example:
            ```cpp
                std::vector<int> myVector = {1, 2, 3, 4, 5};
                int sum = std::accumulate(myVector.begin(), myVector.end(), 0);
                std::cout << "Sum of myVector: " << sum << std::endl;
            ```
## Miscellaneous
- **Namespaces**
    Namespaces are used to avoid name conflicts. You can use the `using` keyword to avoid writing the namespace every time.
    - **Declaration**
        ```cpp
            namespace [name] {
                [code]
            }
        ```
        - Example:
            ```cpp
                namespace myNamespace {
                    int myNum = 5;
                }
            ```
    - **Access**
        ```cpp
            [namespace]::[member];
        ```
        - Example:
            ```cpp
                std::cout << myNamespace::myNum;
            ```
    - **Using**
        ```cpp
            using namespace [namespace];
        ```
        - Example:
            ```cpp
                using namespace myNamespace;
                std::cout << myNum;
            ```
- **Enums**
Like in C, enums are used to define a set of named integer constants. But in C++ you can use `enum class` to avoid name conflicts.
    - **Declaration**
        ```cpp
            enum class [name] {
                [members]
            };
        ```
        - Example:
            ```cpp
                enum class Color {
                    RED,
                    GREEN,
                    BLUE
                };
            ```
    - **Access**
        ```cpp
            [name] [variable] = [name]::[member];
        ```
        - Example:
            ```cpp
                Color myColor = Color::RED;
            ```