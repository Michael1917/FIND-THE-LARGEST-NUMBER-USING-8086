# FIND-THE-LARGEST-NUMBER-USING-8086

# 8086 Assembly Language Program for Largest Number

## AIM

To write and execute Assembly Language Program to perform largest number for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## Algorithm:
1. Start the program.
2. Load the total number of elements (N) from memory location 1000H.
3. Set the counter (CL = N – 1).
4. Set SI = 2000H (starting address of the numbers).
5. Compare each number with the next one.
6. If the next number is greater, keep it as it is;
7. if the current number is greater, exchange them.
8. Repeat the comparison until all numbers are checked.
9. After the loop, the largest number will be in AL register.
10. Stop the program.
## PROGRAM
```
code segment
assume cs:code
start:
     mov ax,0000h
     mov bl,al
     mov cl,bl
     mov si,1000h
     mov bl,[si]
     dec bl
     mov cl,bl
     mov si,2000h
   l2:mov al,[si]
     cmp al,[si+1]
     jle l1
     xchg al,[si+1]
     mov [si],al
   l1:inc si
     loop l2
     int 3
code ends
end
```
## OUTPUT
<img width="638" height="416" alt="Screenshot 2025-10-25 114716" src="https://github.com/user-attachments/assets/56920088-c689-470a-a379-064981d33db2" />


## RESULT
The program successfully compares all the numbers stored in memory and finds the largest one.
After execution, the largest number is stored in the AL register.
