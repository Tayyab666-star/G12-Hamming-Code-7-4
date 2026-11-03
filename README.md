# G12-Hamming-Code-7-4
# G12 – Hamming Code (7,4) Tool

**Course:** Computer Architecture  
**Project Group:** G12

## Group Members

| Member Name | Registration Number | Responsibility |
|---|---|---|
| Tayyab Nisar | FA-2024/BS CS/152 | Frontend Development |
| Amin Bin Rashid | FA-2024/BS CS/157 | Backend Logic and Calculations |

---

# 1. Project Overview

The Hamming Code (7,4) Tool is a web-based application designed to demonstrate error detection and correction in digital communication.

It converts four input data bits into a seven-bit Hamming codeword by adding three parity bits. Users can introduce an error by clicking any bit in the generated codeword. The application then identifies the incorrect bit position using syndrome calculation and corrects the error automatically.

The project provides an interactive way for students to understand how Hamming Code works in Computer Architecture.

## 2. Abstract

The Hamming Code (7,4) Tool is a web-based application designed to demonstrate error detection and correction in digital communication. It converts four data bits into a seven-bit codeword by adding three parity bits using the even parity method. The application allows users to introduce an error by clicking any bit in the generated codeword. It then identifies the incorrect bit position using syndrome calculation and corrects the error automatically. The tool also displays parity bits and data bits in different colours to make the encoding and correction process easier to understand. This project provides a simple and interactive way to learn how Hamming Code improves data reliability.

---

# 3. Introduction

In digital communication and computer systems, data is transferred and stored in the form of binary digits (0s and 1s). During data transmission or storage, errors can sometimes occur due to noise, interference, or hardware problems. These errors can change the original values of bits and affect the accuracy of information.

Error detection and correction techniques are used to identify and handle such errors. One commonly used technique is Hamming Code, which adds extra bits to the original data to detect and correct errors.

The Hamming Code (7,4) Tool is developed to demonstrate this technique in a simple and interactive way. It takes four input data bits and converts them into a seven-bit codeword by adding three parity bits. The application then allows users to introduce an error, detect its position, and correct it automatically.

## 3.1 Purpose of the Application

The main purpose of this application is to help students understand how error detection and correction work in computer systems.

Instead of only studying theoretical concepts, users can interact with the application and observe how data is encoded, how errors occur, and how incorrect bits are identified and corrected.

The application uses the even parity method to calculate three parity bits. These bits help the system check the received codeword and determine whether an error has occurred.

## 3.2 Project Objectives

- Understand the basic concept of Hamming Code (7,4).
- Convert four data bits into a seven-bit codeword.
- Calculate parity bits using the XOR operation.
- Simulate single-bit errors.
- Identify incorrect bit positions using syndrome calculation.
- Correct single-bit errors automatically.
- Provide an interactive learning experience.

---

# 4. Main Features

The application includes four main features.

## Feature 1: Hamming Code Encoding

The application accepts four binary digits (0s and 1s) as input. It calculates three parity bits using the even parity method and combines them with the original data bits to generate a seven-bit Hamming codeword.

## Feature 2: Different Colours for Parity and Data Bits

The application displays parity bits and data bits in different colours. This makes it easier for users to identify the position and purpose of each bit in the seven-bit codeword.

## Feature 3: Error Simulation by Clicking a Bit

Users can click any bit in the generated seven-bit codeword to simulate a transmission error. The selected bit changes from 0 to 1 or from 1 to 0.

## Feature 4: Error Detection and Correction

After an error is introduced, the application performs parity checks and calculates the syndrome to identify the incorrect bit position. It then automatically flips the incorrect bit to restore the original codeword.

The application also displays the correction process step by step.

---

# 5. Background Research: Hamming Code (7,4)

## 5.1 What is Hamming Code?

Hamming Code is an error-correcting technique developed by Richard W. Hamming. It adds extra bits, called parity bits, to the original binary data.

These additional bits help identify and correct a single incorrect bit in a received codeword.

## 5.2 Understanding Hamming (7,4)

The name Hamming (7,4) represents:

- 7: Total number of bits after encoding.
- 4: Original data bits.
- 3: Additional parity bits.

The three parity bits are placed at positions 1, 2 and 4. The remaining positions contain the original data bits.

### Bit Position Arrangement

| Position | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| Type | P1 | P2 | D1 | P4 | D2 | D3 | D4 |

P1, P2 and P4 are parity bits, while D1, D2, D3 and D4 are data bits.

**Note:** This project uses bit positions numbered from left to right, starting at position 1.

## 5.3 Even Parity

Even parity means that the total number of 1s in each checked group must be even.

The application uses the XOR operation to calculate parity bits.

Basic XOR rules:

| A | B | A XOR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## 5.4 Parity Bit Calculation

Each parity bit checks a specific group of positions.

| Parity Bit | Positions Checked |
|---|---|
| P1 | 1, 3, 5, 7 |
| P2 | 2, 3, 6, 7 |
| P4 | 4, 5, 6, 7 |

The parity equations are:

P1 = D1 XOR D2 XOR D4

P2 = D1 XOR D3 XOR D4

P4 = D2 XOR D3 XOR D4

## 5.5 Encoding Example

Suppose the input data is:

**Data = 1011**

Therefore:

- D1 = 1
- D2 = 0
- D3 = 1
- D4 = 1

Calculate the parity bits:

P1 = 1 XOR 0 XOR 1 = 0

P2 = 1 XOR 1 XOR 1 = 1

P4 = 0 XOR 1 XOR 1 = 0

Place the bits in their respective positions:

| Position | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| Bit | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| Type | P1 | P2 | D1 | P4 | D2 | D3 | D4 |

**Final Hamming Codeword: 0110011**

## 5.6 Error Detection Using Syndrome

A syndrome is a binary value calculated by performing parity checks on the received codeword.

The application calculates three syndrome bits:

- S1 checks positions 1, 3, 5 and 7.
- S2 checks positions 2, 3, 6 and 7.
- S4 checks positions 4, 5, 6 and 7.

The syndrome is arranged in the order S4 S2 S1.

If the syndrome is 000, no single-bit error is detected.

If the syndrome is non-zero, its binary value identifies the incorrect bit position, assuming a single-bit error.

## 5.7 Error Correction Example

Original codeword:

0110011

Suppose bit position 5 changes from 0 to 1.

Received codeword:

0110111

The parity checks produce:

| Syndrome Bit | Result |
|---|---|
| S1 | 1 |
| S2 | 0 |
| S4 | 1 |

Syndrome = S4 S2 S1 = 101

Binary 101 = Decimal 5.

Therefore, the incorrect bit is at position 5.

The application flips position 5 from 1 to 0.

Corrected codeword:

**0110011**

The original codeword has been restored.

**Limitation:** Standard Hamming (7,4) is designed to correct one-bit errors. It does not guarantee correct recovery when multiple bits are changed.

---

# 6. Technologies Used

The application will be developed using basic web technologies.

| Technology | Purpose |
|---|---|
| HTML | Creates the application structure and input fields. |
| CSS | Designs the interface, colours and bit boxes. |
| JavaScript | Performs encoding, parity calculation, error detection and correction. |

No database or backend server is required for the planned functionality. All calculations can be performed directly in the browser using JavaScript.

---

# 7. System Workflow

The application follows these steps:

1. User enters four binary data bits.
2. User clicks the Encode button.
3. JavaScript calculates three parity bits.
4. The application generates and displays the seven-bit codeword.
5. Parity bits and data bits are displayed in different colours.
6. User clicks any bit to simulate an error.
7. User selects Detect and Correct.
8. The application calculates the syndrome.
9. The incorrect bit position is identified.
10. The incorrect bit is flipped to restore the original codeword.
11. The application displays the correction steps.

---

# 8. Proposed User Interface

The application will contain the following sections:

1. Project heading: Hamming Code (7,4) Tool.
2. Four-bit input field.
3. Encode button.
4. Seven-bit codeword display.
5. Different colours for parity and data bits.
6. Error simulation instruction.
7. Detect and Correct button.
8. Result section displaying the syndrome and error position.
9. Step-by-step correction explanation.

### Proposed Screen Layout

```text
+-------------------------------------------+
|          HAMMING CODE (7,4) TOOL          |
+-------------------------------------------+
|                                           |
|             Enter 4 Data Bits             |
|                                           |
|               [1] [0] [1] [1]             |
|                                           |
|                  [ENCODE]                 |
|                                           |
+-------------------------------------------+
|             Generated Codeword            |
|                                           |
|          [0] [1] [1] [0] [0] [1] [1]     |
|                                           |
|          Parity Bits | Data Bits          |
|                                           |
|       Click any bit to introduce error    |
|                                           |
|              [DETECT & CORRECT]           |
|                                           |
+-------------------------------------------+
|              Correction Steps             |
|                                           |
|       Syndrome: 000                       |
|       Error Position: No Error            |
|       Corrected Codeword: 0110011         |
|                                           |
+-------------------------------------------+
```

The final interface will be designed using HTML and CSS.

---

# 9. Group Members and Responsibilities

The project work is divided between two members.

## Member 1: Tayyab Nisar

**Registration Number:** FA-2024/BS CS/152

**Role:** Frontend Development

Responsibilities:

- Design the application page.
- Create the seven-bit boxes.
- Apply different colours to parity and data bits.
- Implement bit-click interactions.
- Design the correction steps and result section.
- Connect the interface with the JavaScript logic.

## Member 2: Amin Bin Rashid

**Registration Number:** FA-2024/BS CS/157

**Role:** Logic and Calculations

Responsibilities:

- Implement parity bit calculations.
- Generate the seven-bit Hamming codeword.
- Calculate syndrome values.
- Identify the incorrect bit position.
- Implement single-bit error correction.
- Test the encoding and correction logic.

Both members will work together to integrate and test the complete application.

---

# 10. Project File Structure

The project will use the following file structure:

```text
G12-Hamming-Code-7-4/
│
├── index.html
├── style.css
├── script.js
├── README.md
│
└── screenshots/
```

### File Descriptions

| File | Description |
|---|---|
| index.html | Main structure of the application. |
| style.css | Styling, layout and colours. |
| script.js | Hamming Code calculations and interactions. |
| README.md | Project documentation and instructions. |
| screenshots/ | Application screenshots for documentation. |

---

# 11. Testing Plan

The following test cases will be used to verify the application.

| Test | Input Data | Expected Result |
|---|---|---|
| 1 | 0000 | 0000000 |
| 2 | 1011 | 0110011 |
| 3 | 0110 | 1100110 |
| 4 | 1011, flip position 3 | Error detected at position 3 |
| 5 | 1011, flip position 5 | Error detected at position 5 |
| 6 | 1011, flip position 7 | Error detected at position 7 |
| 7 | 1011, no error | Syndrome 000; no correction |

The application will be considered successful when it correctly encodes four-bit data, detects single-bit errors, identifies their positions and restores the original codeword.

---

# 12. Expected Outcome

The expected outcome is a functional and interactive web application that demonstrates the working of Hamming Code (7,4).

Users will be able to enter four data bits, generate a seven-bit codeword, introduce an error, identify its position and correct it automatically.

The project will provide practical knowledge of parity bits, XOR operations, binary calculations and error correction techniques used in Computer Architecture.

---

# 13. GitHub Repository

The project source code and documentation will be maintained in a shared GitHub repository.

**Repository Name:** G12-Hamming-Code-7-4

**Repository Description:** A web-based Hamming Code (7,4) tool for encoding four data bits, simulating single-bit errors, detecting incorrect bit positions and correcting errors.

### Repository 

**Repository URL:** https://github.com/Tayyab666-star/G12-Hamming-Code-7-4/
---

# 14. Research References

The following educational and university resources were consulted to understand Hamming Code, parity calculations, syndrome generation and single-bit error correction.

1. **University of New Brunswick (UNB)**  
   Error Correction and the Hamming Code.  
   https://www.ece.unb.ca/tervo/ee4253/hamming.shtml

2. **Stanford University**  
   Lecture 18: Error Detection and Correction.  
   https://web.stanford.edu/class/ee179/lectures/notes18.pdf

3. **Massachusetts Institute of Technology (MIT)**  
   6.02 Notes, Chapter 5: Coping with Bit Errors using Error Correction Codes.  
   https://ocw.mit.edu/courses/6-02-introduction-to-eecs-ii-digital-communication-systems-fall-2012/1cc286051b660feded4d17650bd21d61_MIT6_02F12_chap05.pdf

4. **Rice University / Engineering LibreTexts**  
   Error-Correcting Codes – Hamming Codes.  
   https://eng.libretexts.org/Bookshelves/Electrical_Engineering/Introductory_Electrical_Engineering/Electrical_Engineering_(Johnson)/06%3A_Information_Communication/6.29%3A_Error-Correcting_Codes_-_Hamming_Codes

5. **Rensselaer Polytechnic Institute (RPI)**  
   EE4253: Hamming Code.  
   https://cs.rpi.edu/academics/courses/fall04/os/c16/hamming.htm

---

# 15. Conclusion

The G12 Hamming Code (7,4) Tool is designed to provide a simple and practical demonstration of error detection and correction in digital communication. By combining HTML, CSS and JavaScript, the application will allow users to encode binary data, simulate errors, identify incorrect bits and correct single-bit errors. This project will improve understanding of Hamming Code and its importance in Computer Architecture.
