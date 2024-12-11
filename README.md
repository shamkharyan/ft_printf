# 📜 About `ft_print`

The requirement of the ft_printf project is very straightforward - implementation of the `printf` function of the C standard library.

This project is very simple and very complex at the same time, because printf is an intuitive function, but the large number of customizations makes its implementation an interesting task.
In this project you will learn how to work with variadic arguments and become much more familiar with the printf function.

## 🧪 How to use
- Add `ft_printf` repository to the root directory of the project.
- Go to the `ft_printf` repository and use `make` command to build the project.
- Include the header file of the library in your .c files using `#include "ft_printf.h"`.
- `ft_printf` also contains `libft`, so you don't really need to include `libft` to your project.
- When compiling your project, add the path to ft_printf and the `libftprintf.a` library file. If you're using a Makefile, you can do this:
```Makefile
FT_PRINTF_PATH = path/to/ft/printf
FT_PRINTF = $(FT_PRINTF_PATH)/libftprintf.a

SRC = main.c  # Your source code files

all:
   gcc -o my_program $(SRC) $(FT_PRINTF)  # Add libft.a during compilation
```

## 🔍 How it works
`ft_printf` formatting is controlled by 'format identifiers' which, are shown below in their simplest form.
| Identifier |               Type              |
| ---------- | ------------------------------- |
| `%d %i`    | Decimal signed integer          |
| `%x`       | Hexademical integer (lowercase) |
| `%X`       | Hexademical integer (uppercase) |
| `%u`       | Unsigned integer                |
| `%c`       | Single character                |
| `%s`       | String                          |
| `%p`       | Pointer in hexademical format   |
| `%%`       | Percent sign                    |

These identifiers actually have upto 6 parts as shown in the table below. They MUST be used in the order shown.
|     %     |  Flags   | Minimum field width |  Period  | Precision. Maximum field width | Argument Type |
| --------- | -------- | ------------------- | -------- | ------------------------------ | ------------- |
| Required  | Optional | Optional            | Optional | Optional                       | Required      |

### %
The % marks the start and therfore is manatory.

### Flags
The format identifers can be altered from their default function by applying the following flags:

| Identifier |                Meaning                     |
| ---------- | ------------------------------------------ |
| `-`        | Left justify                               |
| `0`        | Field is padded with 0's instead of blanks |
| `+`        | Sign of number always O/P                  |
| `(space)`  | Positive values begin with a blank         |
| `#`        | 0x or 0X prefix added to non-zero values   |

### Minimum field width
By default the width of a field will be the minimum required to hold the data. If you want to increase the field width you can use your width.

### Period
If you wish to specify the precision of an argument, it MUST be prefixed with the period.

### Precision
The precision within a string format specifies the maximum field width.

### Function prototype
```C
ft_printf(const char *, ...);
```

### Example of work
```C
ft_printf("Hello, 42 Yerevan!\n");
// Output: Hello, 42 Yerevan!

ft_printf("Character: %c\n", 'A');
ft_printf("String: %s\n", "Welcome to ft_printf");
// Output:
// Character: A
// String: Welcome to ft_printf

ft_printf("Signed integer: %d\n", -42);
ft_printf("Unsigned integer: %u\n", 42);
// Output:
// Signed integer: -42
// Unsigned integer: 42

ft_printf("Hexadecimal (lowercase): %x\n", 255);
ft_printf("Hexadecimal (uppercase): %X\n", 255);
ft_printf("Pointer: %p\n", (void *)0x7ffe12345678);
// Output:
// Hexadecimal (lowercase): ff
// Hexadecimal (uppercase): FF
// Pointer: 0x7ffe12345678

ft_printf("This is 100%% success!\n");
// Output: This is 100% success!

ft_printf("Right-aligned: %10d\n", 42);
ft_printf("Left-aligned: %-10d\n", 42);
ft_printf("Zero-padded: %010d\n", 42);
// Output:
// Right-aligned:         42
// Left-aligned: 42        
// Zero-padded: 0000000042

ft_printf("String with precision: %.5s\n", "Hello, 42 Yerevan!");
// Output:
// String with precision: Hello

ft_printf("Student: %s, Age: %d, Score: %u, Hex: %x\n", "Pavel", 22, 100, 255);
// Output:
// Student: Pavel, Age: 22, Score: 100, Hex: ff
```
## 📂 Repository Structure
- [`Makefile`](Makefile) - Makefile of the project. Builds the project.
- [`ft_get_flags.c`](ft_get_flags.c) - Gets all format specifiers from formatted string of `ft_printf`.
- [`ft_printf.c`](ft_printf.c) - Core implementation of the function.
- [`ft_printf.h`](ft_printf.h) - Function prototypes and macros.
- [`ft_putcharf.c`](ft_putcharf.c) - Prints formatted characters.
- [`ft_putnbrf.c`](ft_putnbrf.c) - Prints formatted integers.
- [`ft_putnbrf_base.c`](ft_putnbrf_base.c) - Prints formatted unsigned integers with selected base.
- [`ft_putptrf.c`](ft_putptrf.c) - Prints formatted pointers.
- [`ft_putstrf.c`](ft_putstrf.c) - Prints formatted strings.

## 🤝 Contributing
Contributions, bug reports, and feature requests are welcome! Feel free to open an issue or submit a pull request.


