
# Serial Transfer of Single Byte / Character using 8051 (Keil)

## AIM
To write and execute an Embedded C Program for Serial Transfer of Single Byte / Character using 8051 in Keil.

## APPARATUS REQUIRED
- Personal Computer  
- Keil µVision Software  

## PROGRAM

### (i) Serial Port Transfer a Single Character

```
ORG 00H 
MOV TMOD, #20H 
MOV TH1, #0FCH 
MOV SCON, #40H 
SETB TR1 
MOV SBUF, #'B'
WAIT:JNB TI, WAIT
CLR TI 
END

```
### (ii) Serial Port to Transfer a Message

```
ORG 00H
MOV TMOD,#20H
MOV TH1,#0FCH
MOV SCON,#40H
SETB TR1
MOV B,30H
MOV DPTR,#4500H
AGAIN:MOVX A,@DPTR
MOV SBUF,A
WAIT:JNB TI,WAIT
CLR TI
INC DPTR
DJNZ  B,AGAIN
END


```

### OUTPUT:
<img width="1920" height="1200" alt="Screenshot (45)" src="https://github.com/user-attachments/assets/e9001d89-6d01-48ae-b896-62e7f2356cd4" />
<img width="1920" height="1200" alt="Screenshot (46)" src="https://github.com/user-attachments/assets/9d84c568-c09b-42c8-af23-fdef22521557" />

### RESULT:
Thus the Serial transfer of Single Byte / Character using 8051 KEIL was done and shown the output.
