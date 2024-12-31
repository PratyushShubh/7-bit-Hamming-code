# 7-bit-Hamming-code
The project demonstrates the use of Hamming codes for error detection and correction in digital communication. Specifically, it encodes a 4-bit message into a 7-bit codeword, allowing single-bit error correction.


---

### **1. Goal of the Project**
The project demonstrates the use of **Hamming codes** for **error detection and correction** in digital communication. Specifically, it encodes a 4-bit message into a 7-bit codeword, allowing single-bit error correction.

---

### **2. Hamming Code Basics**
- The Hamming (7,4) code transforms a 4-bit data message into a 7-bit codeword by adding 3 parity bits.
- The 7 bits are indexed as \(1, 2, 3, 4, 5, 6, 7\) (1-based indexing). Positions \(1, 2, 4\) are reserved for parity bits, while positions \(3, 5, 6, 7\) hold the data bits.

#### **Bit Layout:**
![image](https://github.com/user-attachments/assets/ba84bb37-e5f2-4dfa-b174-9c72aa287149)


Where:
- \(P1, P2, P3\): Parity bits
- \(D1, D2, D3, D4\): Data bits

---

### **3. Parity Bit Calculation**
Each parity bit ensures that the total number of 1's in certain bit positions is even (even parity). 

#### **Equations:**
![image](https://github.com/user-attachments/assets/13b45568-2692-4d9d-a285-46cd859315d9)

Here, 

⊕ is the XOR operation.

---

### **4. Codeword Example**
Suppose the 4-bit message is \(1011\) (\(D1=1, D2=0, D3=1, D4=1\)):

![image](https://github.com/user-attachments/assets/ab392c10-e889-40ed-88d3-aedcccde9710)


---

### **5. Error Detection and Correction**
If a single bit flips during transmission, the receiver uses the parity bits to detect and correct the error.

#### **Syndrome Calculation:**
Each parity bit is recalculated, and the results are compared with the received parity bits. The comparison forms a 3-bit **syndrome** that identifies the erroneous bit position.

For example, if bit 5 flips (from 0 to 1), the received codeword becomes \([0, 1, 1, 0, 1, 1, 1]\). The syndrome bits (\(S1, S2, S3\)) are calculated as:

![image](https://github.com/user-attachments/assets/097be0fc-5931-4df1-be8e-bc0efc3cc505)


Syndrome: \([S1, S2, S3] = [1, 0, 1] = 5\).

#### **Correction:**
The bit at position 5 is corrected by flipping it.

---

### **6. Implementation Details**
Ben Eater’s implementation likely involves:
1. **Breadboard Circuit:**
   - Using logic gates (XOR gates for parity calculation).
   - LEDs for visualizing errors and corrections.

2. **Manual Input:**
   - Toggle switches to input the 4-bit data and simulate bit errors.

3. **Error Correction:**
   - Logic gates to calculate syndrome and flip the erroneous bit.

---

### **7. Applications**
Hamming codes are used in memory systems (e.g., RAM), satellite communications, and data transmission systems for robust error detection and correction.

---
### 8. Snapshot 
![image_hammingcode](https://github.com/user-attachments/assets/601bbdce-1c0f-4ff2-abed-3a48e0aadcac)

