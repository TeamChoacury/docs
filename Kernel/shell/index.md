---
title: Shell
layout: home
nav_order: 1
parent: "Kernel"
---

# Shell documentation

Limits of the shell:

| Name           | Limit          |
| :------------- | :------------- |
| Command length | 256 characters |
| Arguments      | 128 characters |
| Directory path | 256 characters |

## How the shell works

## `shell.c`

### Includes
Headers included in `shell.c`

- `../drivers/debug.h`
- `../drivers/filesystem/fat.h`
- `../drivers/pit.h`
- `../drivers/ps2_keyboard.h`
- `../drivers/sound.h`
- `../drivers/storage/device.h`
- `../drivers/utils.h`
- `../drivers/vga.h`
- `../drivers/vbe.h`
- `../gui/desktop.h`
- `../kernel/panic.h`
- `../memory/kmalloc.h`
- `../memory/pmm.h`
- `shell.h`
- `terminal.h`
- `<stdint.h>`

### Definitions
Definitions declared in `shell.c`

```c
#define MAX_COMMAND_LENGTH 256
#define MAX_ARGUMENTS 128
```

### Variables
Variables declared in `shell.c`
```c
FAT_filesystem_t* s_fat_fs = NULL;
char currentDir[256] = "root";
```

### Type declarations
Types declated in `shell.c`

```c
typedef int (*math_op_t)(int, int);
```

### Functions
Functions declared in `shell.c`

List:
- `add`
- `subtract`
- `divide`
- `multiply`
- `find_last_slash`
- `starts_with`
- `cpuid`
- `get_cpu_info`
- `handle_return_code`
- `handle_command`
- `parse_command`
- `shell_start`

Definitions:
```c
int add(int a, int b);
int subtract(int a, int b);
int divide(int a, int b);
int multiply(int a, int b);

char* find_last_slash(char* str);
int starts_with(const char *str, const char *prefix);
void cpuid(uint32_t eax_in, uint32_t* eax, uint32_t* ebx, uint32_t* ecx, uint32_t* edx);
void get_cpu_info(char* vendor, char* brand);
static handle_return_code(int return_code, int argc, char** argv);
static void handle_command(int argc, const char** argv);
static void parse_command(char* command, unsigned length);

void shell_start();
```

## `shell.h`

### Includes
Headers included in `shell.h`
- `../drivers/filesystem/fat.h`

### Variables
Variables declared in `shell.h`

List:
```c
extern FAT_filesystem_t* s_fat_fs;
extern char currentDir[256];
```