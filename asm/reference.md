```asm
%include "tuna.asm" ; simply replace this line with tuna.asm content

; Set the starting (origin) address of THIS ENTIRE PROGRAM
; Usually appear at the beginning of the file
; Usage:
;   [org 0x7c00]
[org <addr>]

; Identify <sym> as external symbol in other file
[extern <sym>]

and <op1> <op2> ; See also: or, xor

; Like jmp, but store the address beforehand
; Pair with ret to return to same address afterward
call <label>

; Jump to the latest stored address
; See also: call
ret

add <register>, <val> ; Add <val> to <register>

sub <register>, <val> ; Subtract <val> from <register>

; Clear interrupt. CPU will ignore interrupts until ther are enable again
cli

; Compare two <val> and set the flags
; Usually pair with other conditional instructions like je afterward
cmp <val>, <val>

; Define byte.
; Usage:
;   db 'X'
;   db 'Tuna', 0 # Define a string follow with null character
db <val>

dw <val> ; Define word. (2 bytes)

ddw <val> ; Define double word (4 bytes)

; Send an software interrupt
; Usage:
;   int 0x10 ; print a char via BIOS ISR
int <addr>

jc <label> ; Jump if carry flag set

je <label> ; Jump if equal

jne <label> ; Jump if not equal

jl <label> ; Jump if lower

jle <label> ; Jump if lower or equal

jg <label> ; Jump if greater

jge <label> ; Jump if greater or equal

jmp <addr>

; Load global descriptor table
; Usage:
;   lgdt [gdt]
lgdt [table_addr]

; Copy <from> to <to>
; Usage:
;   mov ah, [0x0e]
;   mov al, 0x0e
mov to, from

; Push all registers values to the stack
; Usually pair with popa
; Usage:
;   pusha
;   # safe to mutate registers
;   popa
pusha

popa ; Pop and load all registers values from stack, usually use after pusha

; Perform instruction <int> times
; Usage:
;   times 510-($-$$) db 0
times <int> <instruction>

; Pop <val> into <register>. Increment sp afterward.
; Usage:
;   pop bx
pop <register>

; Push <val> onto stack. Decrement sp beforehand.
; Usage:
;   push 'X'
push <val>

shl <operand> <count> ; Shift <operand> left by <count>

shr <operand> <count> ; Shift <operand> right by <count>

; Chars

; Below two chars could pair together (order interchangable)
; before terminate the string to print newline
0xa # newline
0xd # carriage return


; Others
$ ; current addrress
$$ ; origin address
bp ; stack base ptr. The address of stack base
sp ; stack ptr. Decrement when push, increment when pop
ebp ; extended bp
esp ; extended sp

; Registers
ax, cx, dx
bx ; This is the ONLY index register. I.e. the register that could write to addr
eax, ebx, ecx, edc ; Extended registers (4 bytes)
cr0 ; Control register

; Segment Registers
; Note:
;   Their value could not be set directly, instead have to be copy from other register
;   mov ds, 0x7c0 ; Invalid operation
;   mov ds, ax ; Valid operation
; physicalAddress = segmentRegisterVal * 16 + addr
cs ; code segment
ds ; data segment
ss ; stack segment
es ; extra segment (determine by programmer)
fs, gs ; General segment registers (32-bit protected mode)
; Explicit tell CPU to use es val as base to find physical address
mov al, [es:stuff]

; Allocate a memory to store 'X' at address $$ + tuna
; Same as:
; tuna db 'X'
; Could think about it (in JavaScript) as:
;   let tuna = 'X'
tuna:
  db 'X'

; Interrupts

; Print a char on screen via BIOS
; ah -> print mode
; al -> char to be print
; Usage:
;   mov ah, 0x0e # tele-type printing mode
;   move al, 'c'
;   int 0x10
```
