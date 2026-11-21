# Square-Cube-of-a-number-using-8051
Mpmc exp3
# Square-Cube-of-a-number-using-8051
# 8051 Square  Program

## AIM
To write and execute an Assembly language program for finding the square of a given data using 8051 microcontroller in Keil software.

## APPARATUS REQUIRED
- Personal computer
- Keil μVision IDE

## ALGORITHM
1.Start the program.

2.Initialize DPTR with memory address 8100H.

3.Read the 8-bit number from external memory location 8100H into accumulator A using MOVX A, @DPTR.

4.Copy the contents of accumulator A into register B using MOV B, A.

5.Multiply A and B using MUL AB to calculate the square of the number.

6.Store the lower 8 bits of the result in accumulator A and the higher 8 bits in register B.

7.Initialize DPTR with memory address 8102H.

8.Store the lower byte of the squared result at external memory location 8102H using MOVX @DPTR, A.

9.Increment DPTR to point to memory location 8103H using INC DPTR.

10.Transfer the higher byte of the result from register B to accumulator A using MOV A, B.

11.Store the higher byte at external memory location 8103H using MOVX @DPTR, A.

12.End the program.

Result:
- 8100H: Input 8-bit number
- 8102H: Lower byte of the square
- 8103H: Higher byte of the square


## FLOW CHART
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/5daf644f-13a6-423c-b222-4d8e29224564" />


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
<img width="1920" height="1017" alt="image" src="https://github.com/user-attachments/assets/cc031451-6be7-4472-b8cb-8a53c86efa8d" />




## RESULT
Thus, the square of the given data is calculated using 8051 Keil.

# 8051 Cube  Program

## AIM
To write and execute an Assembly language program for finding the cube of a given data using 8051 microcontroller in Keil software.

## APPARATUS REQUIRED
- Personal computer
- Keil μVision IDE

## ALGORITHM

1.Start the program.

2.Initialize the Data Pointer (DPTR) with address 9000H.

3.Read the 8-bit number from external memory location 9000H into accumulator A.

4.Copy A into registers B and R1.

5.Execute `MUL AB` to calculate the square of the number (N²).

6.Store the higher byte of the squared result in R2.

7.Copy R1 into B and execute `MUL AB` to calculate the lower partial product of N³.

8.Initialize DPTR with 9003H and store the lower byte of the cube at memory location 9003H.

9.Store the higher byte of the partial product in R3.

10.Copy R2 into B and R1 into A.

11.Execute `MUL AB` to calculate the remaining partial product.

12.Add R3 to accumulator A using `ADD A, R3`.

13.Decrement DPL and store the middle byte at memory location 9002H.

14.Clear accumulator A using `MOV A, #00H`.

15.Add register B and the carry using `ADDC A, B`.

16.Decrement DPL and store the higher byte at memory location 9001H.

17.Execute `SJMP HERE` to stop program progression using an infinite loop.

18.End.

Result: The 24-bit cube of the 8-bit number is stored in external memory locations:
- 9001H: Higher byte
- 9002H: Middle byte
- 9003H: Lower byte



## FLOW CHART
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/429aaf26-fa6e-4562-8d28-ec7695312109" />

## PROGRAM
```
ORG 0000H
MOV DPTR, #9000H
MOVX A, @DPTR
MOV B,A
MOV R1,A
MUL AB
MOV R2,B
MOV B,R1
MUL AB
MOV DPTR, #9003H
MOVX @DPTR,A
MOV R3,B
MOV B,R2
MOV A,R1
MUL AB
ADD A,R3
DEC DPL
MOVX @DPTR,A
MOV A,#00H
ADDC A,B
DEC DPL
MOVX @DPTR,A
HERE: SJMP HERE
END
```



## OUTPUT
<img width="1920" height="1017" alt="image" src="https://github.com/user-attachments/assets/5abf4e5a-f394-4504-8a6c-afc1b3a9ea47" />



## RESULT
Thus, the cube of the given data is calculated using 8051 Keil.
