```asm
%include "tuna.asm" ; simply replace this line with tuna.asm content

;
; Set the starting (origin) address of THIS ENTIRE PROGRAM
; Usually appear at the beginning of the file
; Usage:
;   [org 0x7c00]
;
[org <addr>]

;
; Like jmp, but store the address beforehand
; Pair with ret to return to same address afterward
;
call <label>

;
; Jump to the latest stored address
; See also: call
;
ret

; Compare two <val> and set the flags
; Usually pair with other conditional instructions like je afterward
;
cmp <val>, <val>

;
; Send an software interrupt
; Usage:
;   int 0x10 ; print a char via BIOS ISR
;
int <addr>

;
; Jump if equal
; See also: cmp
;
je <label>

;
; Jump if not equal
; See also: cmp
;
jne <label>

;
; Jump if lower
; See also: cmp
;
jl <label>

;
; Jump if lower or equal
; See also: cmp
;
jle <label>

;
; Jump if greater
; See also: cmp
;
jg <label>

;
; Jump if greater or equal
; See also: cmp
;
jge <label>


;
; Jump to given address
; Usage:
;   jmp $
;
jmp <addr>

;
; Copy <from> to <to>
; Usage:
;   mov ah, [0x0e]
;   mov al, 0x0e
;
mov to, from

;
; Push all registers values to the stack
; Usually pair with popa
; Usage:
;   pusha
;   # safe to mutate registers
;   popa
pusha

;
; Pop and load all registers values from stack
; Usually use after pusha
;
popa

;
; Perform instruction <int> times
; Usage:
;   times 510-($-$$) db 0
;
times <int> <instruction>

;
; Define byte.
; Usage:
;   db 'X'
;   db 'Tuna', 0 # Define a string follow with null character
;
db <val>

;
; Define word.
; Usage:
;   dw 0xaa55
;   dw 'Tuna', 0 # ditto
;
dw <val>

;
; Pop <val> into <register>. Increment sp afterward.
; Usage:
;   pop bx
;
pop <register>

;
; Push <val> onto stack. Decrement sp beforehand.
; Usage:
;   push 'X'
;
push <val>

;
;
; Other stuff
;
;

$ ; current addrress
$$ ; origin address
bp ; stack base ptr. The address of stack base
sp ; stack ptr. Decrement when push, increment when pop

;
; Allocate a memory to store 'X' at address $$ + i_am_a_label
; Same as:
; i_am_a_label db 'X'
; Could think about it (in JavaScript) as:
; let i_am_a_label = 'X'
;
i_am_a_label:
  db 'X'

;
;
; Interrupts
;
;

;
; Print a char on screen
; ah -> print mode
; al -> char to be print
; Usage:
;   mov ah, 0x0e # tele-type printing mode
;   move al, 'c'
;   int 0x10
;

0x10

```
