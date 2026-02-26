# FACTORIAL-OF-A-NUMBER
# FACTORIAL OF A NUMBER USING 8051 (Keil)

## AIM
To write and execute an Assembly language program to perform the factorial of a number using 8051 Keil.

---

## APPARATUS REQUIRED
- Personal computer with Keil software

---

## ALGORITHM
1. **Start**
2. **Input**: Read the number `n`.
3. **Initialize**:
   - Set factorial to `1`.
   - Set `i` to `1`.
4. **Loop**: While `i` is less than or equal to `n`:
   - Multiply factorial by `i`.
   - Increment `i` by `1`.
5. **Output**: Store or print the value of factorial.
6. **End**

---

## FLOWCHART
<img width="506" height="525" alt="image" src="https://github.com/user-attachments/assets/f3b47187-6f0f-490c-8704-f2973cb2b276" />


---

## PROGRAM
```asm
ORG 0000H

        MOV     DPTR, #4500H     ; Point DPTR to input address
        MOVX    A, @DPTR        ; Read number from external memory
        MOV     R0, A           ; Store number in R0

        INC     DPTR            ; Point to output location
        ACALL   FACTORIAL      ; Call factorial subroutine

        MOVX    @DPTR, A        ; Store result in external memory

THIN:   SJMP    THIN            ; Infinite loop
FACTORIAL:
        DEC     R0

        CJNE    R0, #01H, PRODUCT
        SJMP    THICK

PRODUCT:
        MOV     B, R0
        MUL     AB              ; A = A × B
        ACALL   FACTORIAL

THICK:
        RET

END

```
OUTPUT

<img width="1919" height="1199" alt="Screenshot 2026-02-12 103901" src="https://github.com/user-attachments/assets/b2f59fc7-fffd-40bd-abc6-d754ffdbe4c0" />

---
MANUAL CALCULATIONS

<img width="839" height="1280" alt="image" src="https://github.com/user-attachments/assets/4ae93b73-655f-4007-a5c3-db6a6ea71b4e" />

<img width="1280" height="1190" alt="image" src="https://github.com/user-attachments/assets/22112690-169b-406a-9862-6e8237d99853" />
---

RESULT

Thus, the factorial of a number was calculated and executed successfully using 8051 Keil.

---


