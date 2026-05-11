# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS:CODE, DS:CODE
ORG 1000H
MOV CL,00H
MOV AX,1234H
MOV BX,1234H
ADD AX,BX
JNC L1
INC CL
L1:MOV SI,1200H
MOV [SI],AX
MOV [SI+2],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   :   12     |     1204     :        24 |
|       1201   :   34     |     1205     :        68 |
|       1202   :   12     |                          |
|       1203   :   34     |                          |

#### Manual Calculations


<img width="2301" height="3750" alt="ARITHMETIC OPERATIONS USING 8086_1" src="https://github.com/user-attachments/assets/3cf7c84b-7843-45e8-a2a9-d1b14af2ec44" />


---

## OUTPUT IMAGE FROM MASM SOFTWARE


<img width="640" height="232" alt="Screenshot 2026-05-02 092314" src="https://github.com/user-attachments/assets/46d86b67-6148-4fda-a0a4-653d95f1e9a5" />

## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   :   12     |     1204     :        00 |
|       1201   :   34     |     1205     :        00 |
|       1202   :   12     |                          |
|       1203   :   34     |                          |

#### Manual Calculations


<img width="2199" height="3618" alt="ARITHMETIC OPERATIONS USING 8086_1(1)" src="https://github.com/user-attachments/assets/d53f214c-4d37-45ef-b6e2-d40581dc3c11" />



## OUTPUT SCREEN FROM MASM SOFTWARE


<img width="645" height="220" alt="Screenshot 2026-05-02 091816" src="https://github.com/user-attachments/assets/58f16eaa-e476-44f6-83d3-fbf5f05c7355" />


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   :   12     |     1204     :        44 |
|       1201   :   34     |     1205     :        51 |
|       1202   :   12     |     1206     :        97 |
|       1203   :   34     |     1207     :        0A |

#### Manual Calculations


<img width="2540" height="3844" alt="ARITHMETIC OPERATIONS USING 8086_1(2)" src="https://github.com/user-attachments/assets/7b438352-38de-4cd2-8550-056569976f65" />

---

## OUTPUT SCREEN FROM MASM SOFTWARE

<img width="637" height="242" alt="Screenshot 2026-05-02 091936" src="https://github.com/user-attachments/assets/cd26a744-3bf6-480b-a5bb-7b92d33e3082" />



## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table
| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200   :   12     |     1204     :        01 |
|       1201   :   34     |     1205     :        00 |
|       1202   :   12     |     1206     :        00 |
|       1203   :   34     |                          |

#### Manual Calculations



<img width="2341" height="3861" alt="ARITHMETIC OPERATIONS USING 8086_1(3)" src="https://github.com/user-attachments/assets/1162f0a0-fac7-4e40-b408-0e74b052dd44" />

---
## OUTPUT FROM MASM SOFTWARE

<img width="646" height="238" alt="Screenshot 2026-05-02 092024" src="https://github.com/user-attachments/assets/b6d8ef7d-35bd-4a90-9a3a-68661dac982e" />

## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

