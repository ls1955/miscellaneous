```asm
;
; Usage:
;   [org 0x7c00]
; Set the starting address of THIS ENTIRE PROGRAM
; Usually appear at the beginning of the file
;
[org <addr>]

;
; Usage:
;   mov ah, [0x0e]
;   mov al, 0x0e
; Copy <from> to <to>
;
mov to, from

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
;   times 510-($-$$) db 0
; Perform instruction <int> times
;
times <int> <instruction>

;
; Usage:
;   db 'X'
; Allocate a byte for <obj>
;
db <obj>

;
; Usage:
;   dw 0xaa55
; Allocate two byte for <obj>
;
dw <obj>

;
; More references
;

$ ; current addrress
$$ ; origin address

;
; Allocate a memory to store 'X' at $$ + i_am_a_label
;
i_am_a_label:
  db 'X'
```

