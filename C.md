# Table of Contents
* [Data Types](#data-types)
* [Placeholders](#placeholders)
* [Arrays](#arrays)
* [Strings](#strings)
* [Qualifiers](#qualifiers)
* [Storage Classes](#storage-classes)
* [Typecasting](#typecasting)
* [Compilation Make](#compilation-make)

## Data Types
***

```c
typedef unsigned char      uint8_t;  
typedef signed char        int8_t;

unsigned short             uint16_t;
signed short               int16_t;

typedef unsigned int       uint32_t;
typedef signed int         int32_t;

typedef unsigned long long uint64_t;
typedef signed long long   int64_t;

typedef float              float32_t;
typedef double             float64_t;
```

## Placeholders
***
* %c -> Single character
* %d -> Signed decimal integer (int)
* %i -> Signed decimal integer (int)
* %e -> Signed floating-point value in E notation
* %f -> Signed floating-point value (float)
* %o -> Unsigned octal (base 8) integer (int)
* %s -> String of character
* %u -> Unsigned decimal integer (int)
* %x -> Unsigned hexadecimal (base 16) integer (int)
* %g -> Signed value in %e or %f format, whichever is shorter

## Arrays
***
### Declaration
***
```c
int num[6] = {2, 4, 12, 5, 45, 5};
int n[] = {2, 4, 12, 5, 45, 5};
float press[] = {12.3, 34.2, -23.4, -11.3};
```

### Accessing Elements of an Array
***
```c
int valueOfThirdElement = marks[2];
```

## Strings
***
Strings in C are actually arrays of characters.

```c
/* Inmutable string (only for reading) */
char *name = "John Smith";
```

```c
/* This string can be manipulated: */
char name[] = "John Smith";
/* Is equivalent to: */
char name[] = {'J', 'o', 'h', 'n', ' ', 'S', 'm', 'i', 't', 'h'};
/* It is defined as an array of characters */
```

The empty brackets notation [] tells the compiler to calculate the size of the array automatically. This is the same as allocating it explicitly, adding one to the length of the string.

```c
char name[] = "John Smith";
/* is the same as */
char name[11] = "John Smith";
```

The string termination is a special character (equal to 0 -> '\0') which indicates the end of the string.

### String formatting with printf
***
```c
char *name = "John Smith";
int age = 27;

printf("%s is %d years old.\n", name, age);
```

### String length
***
```c
char *name = "Nikhil";
printf("%d\n", strlen(name));
```

### String comparison
***
```c
char *name = "John";

if(strcmp(name, "John", 4) == 0)
{
    printf("Hello, John!\n");
}
else
{
    printf("You are not John. Go away!\n");
}
```

### String concatenation
***
```c
char dest[20] = "Hello";
char src[20] = "World";

strncat(dest, src, 3);
printf("%s\n", dest);
strncat(dest, src, 20);
printf("%s\n", dest);
```

### String as function arguments
* It is possible to use strlen function to get the length of a string passed as a function argument. This is due to the '\0' termination of strings.

```c
void function_name(char *my_string);
// OR
void function_name(char my_string[]);
```

### Example
***
```c
#include <stdio.h>
#include <string.h>

int main() {
    char *first_name = "John";
    char last_name[] = "Doe";
    char name[100];

    last_name[0] = 'B';
    sprintf(name, "%s %s", first_name, last_name);
    if (strncmp(name, "John Boe", 100) == 0) {
        printf("Done!\n");
    }
    name[0]='\0';
    
    strncat(name,first_name,4);
    strncat(name,last_name,20);
    printf("%s\n",name);

    return 0;
}
```
> Output:
```
$ Done
$ JohnBoe
```

## Qualifiers
***
* ***const*** -> Flags variable as read-only (compiler can optimise).
* ***volatile*** -> Flags variable as unpredictable (compiler cannot optimise).

## Storage Classes
***

* **register** -> Quick access required. May be stored in RAM or a register. Maximum size is register size.

* **static** -> Retained when out of scope. Static global variables are confined to the scope of the compiled object file they were declared in.

* **extern** -> Variable is declared by another file.

## Typecasting
***
(type)a -> Returns 'a' as data 'type'.

```c
char x = 1, y = 2;
float z = (float) x / y;
```

## Compilation Make
***
```bash
$ make CC=gcc test
```
