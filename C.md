# Cheat Sheat : C Syntax

## Table of Contents
- [Variables](#Variables)
- [Data Types](#Data-Types)
- [Operators](#Operators)
- [Control Statements](#Control-Statements)
- [Functions](#Functions)
- [Pointers](#Pointers)
- [Arrays](#Arrays)
- [Strings](#Strings)
- [Structures](#Structures)
- [Unions](#Unions)
- [Enumerations](#Enumerations)
- [File Handling](#File-Handling)
- [Preprocessor Directives](#Preprocessor-Directives)
- [Memory Management](#Memory-Management)
- [Error Handling](#Error-Handling)
- [Miscellaneous](#Miscellaneous)

## Variables
- **Declaration**:
    ```c
    [type] [name];
    ```
    - Example:
        ```c
        int a;
        ```

- **Initialization**:
    ```c
    [type] [name] = [value];
    ```
    - Example:
        ```c
        int a;
        ```
- **Multiple Declaration**:
    ```c
    [type] [name1], [name2], [name3];
    ```
    - Example:
        ```c
        int a, b, c;
        ```
- **Multiple Initialization**:
    ```c
    [type] [name1] = [value1], [name2] = [value2], [name3] = [value3];
    ```
    - Example:
        ```c
        int a = 1, b = 2, c = 3;
        ```
- **Constant Declaration**:
    ```c
    const [type] [name] = [value];
    ```
    - Example:
        ```c
        const int a = 1;
        ```
- **Global Variable**:
    Same as local variable but declared outside of any function (at the top of the file and generally before the main function or in a header file).

## Data Types
- **Basic Data Types**:
    - **Description**:
        | Type | Description | Size | Range |
        | --- | --- | --- | --- |
        | char | Character | 1 byte | -128 to 127 |
        | unsigned char | Unsigned Character | 1 byte | 0 to 255 |
        | short int | Short Integer | 2 bytes | -32,768 to 32,767 |
        | unsigned short int | Unsigned Short Integer | 2 bytes | 0 to 65,535 |
        | int | Integer | 4 bytes | -2,147,483,648 to 2,147,483,647 |
        | unsigned int | Unsigned Integer | 4 bytes | 0 to 4,294,967,295 |
        | long int | Long Integer | 8 bytes | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
        | unsigned long int | Unsigned Long Integer | 8 bytes | 0 to 18,446,744,073,709,551,615 |
        | float | Single Precision Floating Point | 4 bytes | 1.2E-38 to 3.4E+38 |
        | double | Double Precision Floating Point | 8 bytes | 2.3E-308 to 1.7E+308 |
        | long double | Extended Precision Floating Point | 10 bytes | 3.4E-4932 to 1.1E+4932 |
        | void | Represents the absence of type | - | - |
    - **Use**:
        - **char**:
            The char data type is used to store a single character and also integer values between -128 and 127.
            ```c
            char a = 'A';
            char b = 65;
            ```
        - **unsigned char**:
            The unsigned char data type is used to store a single character, but it can store only positive values between 0 and 255. So, we use unsigned char when we know that the value will be positive like the ASCII value of a character.
            ```c
            unsigned char a = 'A'; // 65
            ```
        - **short int**:
            The short int data type is used to store integer values between -32,768 and 32,767.
            ```c
            short int a = 32767;
            ```
        - **unsigned short int**:
            The unsigned short int data type is used to store only positive integer values between 0 and 65,535.
            ```c
            unsigned short int a = 65535;
            ```
        - **int**:
            The int data type is used to store integer values between -2,147,483,648 and 2,147,483,647.
            ```c
            int a = 2147483647;
            ```
        - **unsigned int**:
            The unsigned int data type is used to store only positive integer values between 0 and 4,294,967,295.
            ```c
            unsigned int a = 4294967295;
            ```
        - **long int**:
            The long int data type is used to store integer values between -9,223,372,036,854,775,808 and 9,223,372,036,854,775,807.
            ```c
            long int a = 9223372036854775807;
            ```
        - **unsigned long int**:
            The unsigned long int data type is used to store only positive integer values between 0 and 18,446,744,073,709,551,615.
            ```c
            unsigned long int a = 18446744073709551615;
            ```
        - **float**:
            The float data type is used to store single-precision floating-point values. Give a precision of 6 or 9 decimal places.
            ```c
            float a = 3.14;
            ```
        - **double**:
            The double data type is used to store double-precision floating-point values. Give a precision of 15 or 17 decimal places.
            ```c
            double a = 3.14;
            ```
        - **long double**:
            The long double data type is used to store extended-precision floating-point values. Give a precision of 19 or 20 decimal places.
            ```c
            long double a = 3.14;
            ```
        - **void**:
            The void data type is generally used to specify the return type of a function that does not return any value. But it can also be used to declare generic pointers.
            ```c
            void function() {
                void *ptr;
                printf("Hello World");
            }
            ```

- **Derived Data Types**:
    - **Array**:
        ```c
        [type] [name][size];
        ```
        - Example:
            ```c
            int arr[5];
            ```
    - **Pointer**:
        - **Reference**:
            ```c
            [type] *[name];
            ```
            - Example:
                ```c
                int *ptr;
                ```
        - **Dereference**:
            ```c
            [type] *[name] = &[variable];
            ```
            - Example:
                ```c
                int a = 1;
                int *ptr = &a;
                ```
    - **Structure**:
        ```c
        struct [name] {
            [type1] [member1];
            [type2] [member2];
            ...
        };
        ```
        - Example:
            ```c
            struct Point {
                int x;
                int y;
            };
            ```
    - **Union**:
        ```c
        union [name] {
            [type1] [member1];
            [type2] [member2];
            ...
        };
        ```
        - Example:
            ```c
            union Data {
                int i;
                float f;
                char str[20];
            };
            ```
    - **Enumeration**:
        ```c
        enum [name] {
            [value1],
            [value2],
            ...
        };
        ```
        - Example:
            ```c
            enum Color {
                RED,
                GREEN,
                BLUE
            };
            ```
## Operators
- **Arithmetic Operators**
    - **+**:
        Addition
        - Example:
            ```c
            int a = 1 + 2; // 3
            ```
    - **-**:
        Subtraction
        - Example:
            ```c
            int a = 2 - 1; // 1
            ```
    - **\***:
        Multiplication
        - Example:
            ```c
            int a = 2 * 3; // 6
            ```
        If both operands are integers, the result will be an integer. If one of the operands is a float, the result will be a float.
    - **/**:
        Division
        - Example:
            ```c
            int a = 6 / 2; // 3
            ```
        If both operands are integers, the result will be an integer. If one of the operands is a float, the result will be a float.
    - **%**:
        Modulus
        - Example:
            ```c
            int a = 6 % 4; // 2
            ```
- **Relational Operators**
    The relational operators are used to compare two values. They are used in decision-making and loops.
    - **==**:
        Equal to
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a == b) {
                printf("Equal");
            }
            ```
    - **!=**:
        Not equal to
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a != b) {
                printf("Not Equal");
            }
            ```
    - **>**:
        Greater than
        - Example:
            ```c
            int a = 2;
            int b = 1;
            if (a > b) {
                printf("Greater");
            }
            ```
    - **<**:
        Less than
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a < b) {
                printf("Lesser");
            }
            ```
    - **>=**:
        Greater than or equal to
        - Example:
            ```c
            int a = 2;
            int b = 1;
            if (a >= b) {
                printf("Greater or Equal");
            }
            ```
    - **<=**:
        Less than or equal to
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a <= b) {
                printf("Lesser or Equal");
            }
            ```
- **Logical Operators**
    The logical operators are used to combine two or more conditions. They are used in decision-making and loops.
    - **&&**:
        Logical AND
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a == 1 && b == 2) {
                printf("Both are true");
            }
            ```
    - **||**:
        Logical OR
        - Example:
            ```c
            int a = 1;
            int b = 2;
            if (a == 1 || b == 3) {
                printf("At least one is true");
            }
            ```
    - **!**:
        Logical NOT
        - Example:
            ```c
            int a = 1;
            if (!(a == 2)) {
                printf("Not true");
            }
            ```
- **Assignment Operators**
    - **=**:
        Assign
        - Example:
            ```c
            int a = 1;
            ```
    - **+=**:
        Add and assign
        - Example:
            ```c
            int a = 1;
            a += 2; // a = a + 2
            ```
    - **-=**:
        Subtract and assign
        - Example:
            ```c
            int a = 2;
            a -= 1; // a = a - 1
            ```
    - **\*=**:
        Multiply and assign
        - Example:
            ```c
            int a = 2;
            a *= 3; // a = a * 3
            ```
    - **/=**:
        Divide and assign
        - Example:
            ```c
            int a = 6;
            a /= 2; // a = a / 2
            ```
    - **%=**:
        Modulus and assign
        - Example:
            ```c
            int a = 6;
            a %= 4; // a = a % 4
            ```
- **Bitwise Operators**
    The bitwise operators are used to perform bitwise operations on integers. They are used in low-level programming.
    - **&**:
        Bitwise AND
        - Example:
            ```c
            int a = 5 & 3; // 1
            ```
    - **|**:
        Bitwise OR
        - Example:
            ```c
            int a = 5 | 3; // 7
            ```
    - **^**:
        Bitwise XOR
        - Example:
            ```c
            int a = 5 ^ 3; // 6
            ```
    - **~**:
        Bitwise NOT
        - Example:
            ```c
            int a = ~5; // -6
            ```
    - **<<**:
        Left shift
        - Example:
            ```c
            int a = 5 << 1; // 10
            ```
    - **>>**:
        Right shift
        - Example:
            ```c
            int a = 5 >> 1; // 2
            ```
## Control Statements