# libft

`libft` is a custom C library project from 42.
The goal is to rebuild a set of standard C library functions and add useful extra utilities, then compile everything into a static library (`libft.a`) that can be reused in other projects.

## Project Goals

- Reimplement core libc-style functions.
- Practice memory handling, string manipulation, and pointer safety.
- Build and use a static library with a Makefile.
- Provide extra helper functions often reused in future projects.

## What The Subject Requires

This section summarizes the usual `libft` subject expectations.

### Mandatory Part

Recreate selected libc-style functions, typically including:

- `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`
- `ft_strlen`, `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`
- `ft_strlcpy`, `ft_strlcat`, `ft_toupper`, `ft_tolower`
- `ft_strchr`, `ft_strrchr`, `ft_strncmp`, `ft_memchr`, `ft_memcmp`
- `ft_strnstr`, `ft_atoi`, `ft_calloc`, `ft_strdup`

Then implement additional utility functions:

- `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`
- `ft_itoa`, `ft_strmapi`, `ft_striteri`
- `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`

### Bonus Part

Implement linked list utilities (bonus), usually:

- `ft_lstnew`, `ft_lstadd_front`, `ft_lstsize`, `ft_lstlast`
- `ft_lstadd_back`, `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`

### General Rules (Subject)

- Code must compile with `-Wall -Wextra -Werror`.
- Create a static library named `libft.a`.
- Provide all prototypes in `libft.h`.
- Use a Makefile with at least: `all`, `clean`, `fclean`, `re` (and usually `bonus` when required).
- If helper functions are used internally only, keep them `static`.
- No memory leaks in allocation-based functions.
- Function behavior should match libc when applicable.

Note: exact wording can vary slightly by campus/version, but the checklist above matches the standard `libft` subject structure.

## Repository Structure

```text
libft/
	ft_atoi.c
	ft_bzero.c
	ft_calloc.c
	...
	ft_printf.c
	...
	libft.h
	Makefile
```

- `libft/*.c`: function implementations.
- `libft/libft.h`: public header with function prototypes and types.
- `libft/Makefile`: build rules for the static library.

## Build

From the project root:

```bash
cd libft
make
```

This creates:

- `libft.a`: static library archive
- object files (`*.o`) for each source file

Common Makefile targets:

```bash
make        # build libft.a
make clean  # remove object files
make fclean # remove object files + libft.a
make re     # rebuild from scratch
```

## How to Use in Another C Project

1. Include the header in your source code:

```c
#include "libft.h"
```

2. Compile your program and link with `libft.a`:

```bash
cc main.c -L./libft -lft -I./libft -o my_program
```

Or directly:

```bash
cc main.c ./libft/libft.a -I./libft -o my_program
```

## Function Categories

This repository currently contains functions across these groups:

- Character checks and conversions
	- `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`
	- `ft_tolower`, `ft_toupper`

- String utilities
	- `ft_strlen`, `ft_strdup`, `ft_strchr`, `ft_strrchr`, `ft_strncmp`
	- `ft_strlcpy`, `ft_strlcat`, `ft_strnstr`
	- `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`
	- `ft_strmapi`, `ft_striteri`

- Memory utilities
	- `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`
	- `ft_memchr`, `ft_memcmp`, `ft_calloc`

- Conversion and output helpers
	- `ft_atoi`, `ft_itoa`
	- `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`
	- `ft_putstr`, `ft_printf`

- Linked list utilities
	- `ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`
	- `ft_lstlast`, `ft_lstsize`
	- `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`

## Notes

- This is a learning project focused on reimplementation and fundamentals.
- Behavior is intended to follow standard C library expectations where applicable.
- This repo also contains extra functions (like `ft_printf`) that may be outside the base `libft` mandatory scope, depending on your subject version.
