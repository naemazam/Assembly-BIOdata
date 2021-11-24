# Assembly-BIOdata
A Simple Source Code in 8086 Assembly Language that Displays BIODATA of a Certain Profile. 


# Asm ver
Assembler 64bit (nasm 2.14)

```asm
section .text
; Export the entry point to the ELF linker or loader.  The conventional
; entry point is "_start". Use "ld -e foo" to override the default.
    global _start

section .data
msg db  'Hello, I am Naem azam, Im Self-taught Python Programmer And an open-source enthusiast and maintainer.!',0xa ;our dear string
len equ $ - msg         ;length of our dear string

section .text

; linker puts the entry point here:
_start:

; Write the string to stdout:

    mov edx,len ;message length
    mov ecx,msg ;message to write
    mov ebx,1   ;file descriptor (stdout)
    mov eax,4   ;system call number (sys_write)
    int 0x80    ;call kernel

; Exit via the kernel:

    mov ebx,0   ;process' exit code
    mov eax,1   ;system call number (sys_exit)
    int 0x80    ;call kernel - this interrupt won't return
```

# Online Compile
[Online Compile](https://ideone.com/)

# Linux 
to build an executable
```bash
nasm -f elf azam.asm
```
```bash
ld -s -o azam azam.o
```

# Output
Hello, I am Naem azam, Im Self-taught Python Programmer And an open-source enthusiast and maintainer.!
