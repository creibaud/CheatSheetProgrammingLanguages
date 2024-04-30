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
    Same as local variable but declared outside of any function (at the top of the file and generally before the main function or in a header file (.h)).

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
- **If Statement**:
    The if statement is used to execute a block of code only if a condition is true.
    ```c
    if (condition) {
        // code
    }
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 1) {
            printf("True");
        }
        ```
    You can also have the single line if statement. But it is recommended to use braces to avoid confusion. You can use it when you have only one statement to execute.
    ```c
    if (condition) statement;
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 1) printf("True");
        ```
- **If-Else Statement**:
    The if-else statement is used to execute a block of code if the condition is true and another block of code if the condition is false.
    ```c
    if (condition) {
        // code
    } else {
        // code
    }
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 2) {
            printf("True");
        } else {
            printf("False");
        }
        ```
    You can also have multiple else-if statements.
    ```c
    if (condition1) {
        // code
    } else if (condition2) {
        // code
    } else {
        // code
    }
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 2) {
            printf("True");
        } else if (a == 1) {
            printf("False");
        } else {
            printf("None");
        }
        ```
    You can also have the single line if-else statement. But it is recommended to use braces to avoid confusion. You can use it when you have only one statement to execute and that the statement and the condition are short.
    ```c
    if (condition) statement1; else statement2;
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 2) printf("True"); else printf("False");
        ```
    Or you can also use the ternary operator for the same purpose. That is better than the single line if-else statement.
    ```c
    condition ? statement1 : statement2;
    ```
    - Example:
        ```c
        int a = 1;
        a == 2 ? printf("True") : printf("False");
        ```
- **Switch Statement**:
    The switch statement is used to execute a block of code based on the value of a variable.
    ```c
    switch (variable) {
        case value1:
            // code
            break;
        case value2:
            // code
            break;
        ...
        default:
            // code
            break;
    }
    ```
    - Example:
        ```c
        int a = 1;
        switch (a) {
            case 1:
                printf("One");
                break;
            case 2:
                printf("Two");
                break;
            default:
                printf("None");
                break;
        }
        ```
    The break statement is used to exit the switch statement. If you don't use the break statement, all the cases after the matching case will be executed.

    If inside a case you don't have any code to execute, you can use the empty statement.
    ```c
    case value:
        ;
        break;
    ```

    You can also have multiple cases for the same code.
    ```c
    case value1:
    case value2:
        // code
        break;
    ```

    You can also have the switch statement without the variable. In this case, you have to use the goto statement to jump to the case. Goto is generally not recommended to use. Goto is used to jump to a specific line of code like in Assembly language.
    ```c
    switch (1) {
        case 1:
            printf("One");
            goto end;
        case 2:
            printf("Two");
            goto end;
        default:
            printf("None");
            goto end;
    }
    end:
    ```

    If inside a case you have multiple lines of code to execute, you can use the block of code. But it is recommended to use braces to avoid confusion.
    ```c
    case value: {
        // code
        // code
        break;
    }
    ```
- **Loops**
    - **While Loop**:
        The while loop is used to execute a block of code as long as the condition is true.
        ```c
        while (condition) {
            // code
        }
        ```
        - Example:
            ```c
            int a = 1;
            while (a < 5) {
                printf("%d\n", a);
                a++;
            }
            ```
    - **Do-While Loop**:
        The do-while loop is used to execute a block of code at least once and then as long as the condition is true.
        ```c
        do {
            // code
        } while (condition);
        ```
        - Example:
            ```c
            int a = 1;
            do {
                printf("%d\n", a);
                a++;
            } while (a < 5);
            ```
    - **For Loop**:
        The for loop is used to execute a block of code a specific number of times.
        ```c
        for (initialization; condition; increment/decrement) {
            // code
        }
        ```
        - Example:
            ```c
            for (int i = 1; i < 5; i++) {
                printf("%d\n", i);
            }
            ```
        You can also have multiple initializations and multiple increment/decrement statements.
        ```c
        for (initialization1, initialization2; condition; increment1, increment2) {
            // code
        }
        ```
        - Example:
            ```c
            for (int i = 1, j = 1; i < 5; i++, j++) {
                printf("%d %d\n", i, j);
            }
            ```
        You can also have the empty for loop. But it is recommended to use while loop for this purpose.
        ```c
        for (; condition;) {
            // code
        }
        ```
        - Example:
            ```c
            int i = 1;
            for (; i < 5;) {
                printf("%d\n", i);
                i++;
            }
            ```
        You can also have the infinite for loop. But it is recommended to use while loop for infinite loops.
        ```c
        for (;;) {
            // code
        }
        ```
        - Example:
            ```c
            for (;;) {
                printf("Infinite\n");
            }
            ```
- **Break Statement**:
    The break statement is used to exit the loop or switch statement.
    ```c
    break;
    ```
    - Example:
        ```c
        for (int i = 1; i < 5; i++) {
            if (i == 3) {
                break;
            }
            printf("%d\n", i);
        }
        ```
- **Continue Statement**:
    The continue statement is used to skip the current iteration of the loop and continue with the next iteration.
    ```c
    continue;
    ```
    - Example:
        ```c
        for (int i = 1; i < 5; i++) {
            if (i == 3) {
                continue;
            }
            printf("%d\n", i);
        }
        ```
- **Goto Statement**:
    The goto statement is used to jump to a specific line of code.
    ```c
    goto label;
    ...
    label:
    ```
    - Example:
        ```c
        int a = 1;
        if (a == 1) {
            goto end;
        }
        printf("Not true");
        end:
        printf("True");
        ```
        But in the above example, when a = 1 the code will jump to the end label and execute the code after the end label. So, the output will be "True". But when a = 2 the code will execute the code after the goto statement. So, the output will be "Not trueTrue", because the code after the end label will also be executed.
        That is why goto is generally not recommended to use.
    
## Functions
- **Declaration**:
    When you want to declare a function you have to declare it before the main function. The declaration of the function is the prototype of the function. The prototype of the function includes the return type, the name of the function, and the parameters of the function. It is why it is recommended to use the function declaration in a header file (.h).
    ```c
    [returnType] [name]([parameters]);
    ```
    - Example:
        ```c
        // Declaration in a header file (.h) like add.h
        int add(int a, int b);
        ```
- **Definition**:
    The definition of the function is the implementation of the function. It includes the return type, the name of the function, the parameters of the function, and the body of the function. The body of the function is the code that will be executed when the function is called. The definition of the function is generally written after the main function. So you can define the function in any order you want. This is why you have to declare the function before in a header file (.h) and include it in the file where you want to define the function.
    ```c
    #include "add.h" // Include the header file where the function is declared
    // Definition in the file where you want to define the function like add.c
    [returnType] [name]([parameters]) {
        // code
    }
    ```
    - Example:
        ```c
        int add(int a, int b) {
            return a + b;
        }
        ```
- **Call**:
    When you want to call a function you have to use the name of the function followed by the parameters of.
    ```c
    [name]([parameters]);
    ```
    - Example:
        ```c
        #include "add.h" // Include the header file where the function is declared
        int main() {
            int a = 1;
            int b = 2;
            int c = add(a, b); // Call the function
            printf("%d\n", c);
            return 0;
        }
        ```
        This example works because the function add is declared in the header file add.h and defined in the file add.c. The main function is in the file main.c. The main function includes the header file add.h where the function add is declared. So, the main function knows the prototype of the function add. When the main function is compiled, the compiler knows the prototype of the function add. When the main function is executed, the function add is called. The compiler knows the definition of the function add because it is defined in the file add.c. So, the compiler can execute the function add. When you want to compile a code with multiple files, you have to compile all the files (.c) together. This is why the code above works.
- **Return**:
    The return statement is used to return a value from the function. The return statement is generally used at the end of the function. When the return statement is executed, the function will be terminated and the control will be returned to the calling function.
    ```c
    return [value];
    ```
    - Example:
        ```c
        int add(int a, int b) {
            return a + b;
        }
        ```
    You can also return nothing from the function. In this case, you have to use the void return type.
    ```c
    void [name]([parameters]) {
        // code
        return;
    }
    ```
    - Example:
        ```c
        void print() {
            printf("Hello World\n");
            return;
        }
        ```
## Pointers
