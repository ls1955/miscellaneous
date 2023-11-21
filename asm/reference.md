```asm
;
; Usage:
;   [org 0x7c00]
; Set the starting (origin) address of THIS ENTIRE PROGRAM
; Usually appear at the beginning of the file
;
[org <addr>]

;
; Usage:
;   int 0x10 ; print a char via BIOS ISR
; Send an software interrupt
;
int <addr>

;
; Usage:
;   jmp $
; Jump to given address
;
jmp <addr>

;
; Usage:
;   mov ah, [0x0e]
;   mov al, 0x0e
; Copy <from> to <to>
;
mov to, from

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
db <obj>

;
; Define word.
; Usage:
;   dw 0xaa55
;   dw 'Tuna', 0 # ditto
;
dw <obj>

;
; Pop <obj> into <register>. Increment sp afterward.
; Usage:
;   pop bx
;
pop <register>

;
; Push <obj> onto stack. Decrement sp beforehand.
; Usage:
;   push 'X'
;
push <obj>

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
