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
; Define byte. Allocate a byte for <obj>
; Usage:
;   db 'X'
;
db <obj>

;
; Define word. Allocate two byte for <obj>
; Usage:
;   dw 0xaa55
;
dw <obj>

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
```
