# Square-Cube-of-a-number-using-8051
# 8051 Square  Program

## AIM
To write and execute an Assembly language program for finding the square of a given data using 8051 microcontroller in Keil software.

## APPARATUS REQUIRED
- Personal computer
- Keil μVision IDE

## ALGORITHM
1. Enter the Assembly language program.
2. Provide the input value to Port 0 (P0).
3. Execute the program.
4. The output square value is stored in Port 2 (P2).

## PROGRAM
```
ORG 0000H
MOV DPTR, #8100H
MOVX A, @DPTR
MOV B,A
MUL AB
MOV DPTR, #8102H
MOVX @DPTR,A
INC DPTR
MOV A,B
MOVX @DPTR,A
END
```

## OUTPUT
<img width="1422" height="720" alt="Screenshot 2026-10-24 141223" src="https://github.com/user-attachments/assets/571edf39-46b1-4d1b-9da7-5c0b1c983a7a" />


## RESULT
Thus, the square of the given data is calculated using 8051 Keil.

# 8051 Cube  Program

## AIM
To write and execute an Assembly language program for finding the cube of a given data using 8051 microcontroller in Keil software.

## APPARATUS REQUIRED
- Personal computer
- Keil μVision IDE

## ALGORITHM
1. Enter the Assembly language program.
2. Provide the input value.
3. Execute the program.
4. The output cube value is stored in a memory location.

## PROGRAM
```
ORG 0000H

        MOV R4,#04H

AGAIN:  MOV R3,#04H
        MOV R0,#30H

LOOP1:  MOV A,@R0
        MOV B,A
        INC R0
        MOV A,@R0
        CJNE A,B,CONTINUE

CONTINUE:
        JC SKIP
        MOV @R0,B
        DEC R0
        MOV @R0,A
        INC R0

SKIP:   DJNZ R3,LOOP1
        DJNZ R4,AGAIN

STOP:   SJMP STOP

END

```


## OUTPUT
<img width="1917" height="1075" alt="image" src="https://github.com/user-attachments/assets/28c1c477-669a-4d80-9ef3-7c1187885808" />


## RESULT
Thus, the cube of the given data is calculated using 8051 Keil.
