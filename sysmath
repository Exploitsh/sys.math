BITS 64

global _call

section .rodata

    boucle db "boucle", 10, 0
    boucle_len equ $-boucle

    alphabat db "alphabet et zsk aka vingt deux sont trop fort", 10, 0
    alphabat_len equ $-alphabat

section .text

_call:
        call _start
        jmp _exit

_start:
    cmp r12, 15
    je _info
    inc r12
    mov rax, 1
    mov rdi, 1
    mov rsi, boucle
    mov rdx, boucle_len
    syscall
    jmp _start

_info:
    cmp r8, 170
    je _pop
    inc r8
    mov rax, 1
    push rax
    pop rdi
    mov rsi, alphabat
    mov rdx, alphabat_len
    syscall
    jmp _info

_pop:
        mov rax, 20
        pop rdi
        syscall
        cmp rax, 0x203
        je _math

_math:
        mov rax, 0x203
        add rax, 0x20
        sub rax, 0x2
        mov rdi, 0x34
        mul rdi ;545 * 52
        syscall
        jmp _exit

_exit:
    mov rax, 60
    mov rdi, 0
    syscall
