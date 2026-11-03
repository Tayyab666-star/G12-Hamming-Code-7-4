# Hamming Code Tool

A browser based Hamming Code simulator designed to demonstrate how four bit binary data is converted into a seven-bit Hamming Code, how transmission errors are introduced, and how those errors are detected and corrected.

**Group:** G12  
**Course:** Computer Architecture  
**University:** Hitec University, Taxila  

**Submitted To:** Muhammad Hassan Butt

---

## Table of Contents

- [Introduction](#1-introduction)
- [Problem Statement](#2-problem-statement)
- [Project Objectives](#3-project-objectives)
- [Proposed Solution](#4-proposed-solution)
- [Main Features](#5-main-features)
- [Technologies and Tools](#6-technologies-and-tools)
- [Division of Responsibilities](#7-division-of-responsibilities)
- [Expected Outcomes](#8-expected-outcomes)
- [Project Sketch](#9-sketch)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## Group Members

| Member | Name | Roll Number | Responsibility |
|---|---|---|---|
| Member 1 | Amin Bin Rashid | 24-CS-157 | Front-End Development |
| Member 2 | Tayyab Nisar | 24-cs-152 | Back-End Development (Logic) |

---

## 1. Introduction

The fact of the matter is that in many cases, there is nothing straightforward about the movement of data. The bit of information that was supposed to be a zero may turn out to be a one, and vice versa, because of various disturbances within the network. It has been solved by Richard Hamming way back in 1950s, and his approach is still being discussed and practiced in schools since it is both simple enough to learn and efficient enough to correct mistakes in practice. That is why, for our semester project, we plan to design a small browser application that will put the theory into practice. Rather than just drawing parity check schemes, users would be able to input four bits, observe how the tool generates a scheme with seven bits, introduces the mistake, and then corrects it automatically.

## 2. Problem Statement

To be honest, we must admit that when our instructor was explaining Hamming Code to us in the class, it took us some time to really understand everything. Taking into account such elements as parity bits allocation, manual XOR calculation, syndrome calculation and understanding what syndrome means – this is not an easy task at all. One error and the whole work will be incorrect. We noticed that our peers have had the same issues. There are many videos and articles about this topic on the Internet, but they either move too quickly or do not provide any visual representation at all. We believe that it is essential to have some sort of simulator where one could manipulate bits and observe the process of their correction step-by-step.

## 3. Project Objectives

This is where we would like our tool to be capable of doing at the end of the day:

- Get four binary numbers from the user and create a correct 7-bit Hamming Code from them.
- Ensure that it is clearly visible which part is the parity bit and which part holds the data.
- Make the user click on anything he or she wants to corrupt it intentionally just as it is in the actual noise channel.
- Run parity check once again, identify the precise location of the error, and reverse the bit.
- Take the user through all the steps in clear English so that they never wonder what was just done.

## 4. Proposed Solution

The concept is quite easy to understand. We will develop a single web page that performs all of these tasks through nothing but HTML, CSS, and JavaScript. Nothing more than just three simple files that are opened directly from the browser.

Here is how it will work. The user will enter four bits, press a button and our tool will calculate the values of P1, P2, and P4 with even parity. Then all seven bits will be displayed one by one along with labels and colours.

Now, the user will have the ability to toggle any of those bits in order to simulate an error during the transmission. Our tool will perform the three parity checks, find the syndrome, determine the exact location of the error and fix it right away. There will be a little steps area under the main display area for that purpose.

## 5. Main Features

### Feature 1: Hamming Code Encoder

- The user enters four digits of binary numbers – no more, no less.
- This tool creates the full seven bit Hamming Code using these four numbers.
- P1, P2, and P4 are all computed internally following the principle of even parity.

### Feature 2: Bit Position Visualization

- Each individual piece gets its own personal space on the screen in a sequence from 1 to 7 positions.
- The parity bits and data bits are coloured differently so that one can easily distinguish between them.
- They have been marked well, and the user knows exactly what they are seeing.

### Feature 3: Error Simulation

- A click of a mouse toggles the value of the cell to either a 0 or 1 depending on its current state.
- It replicates what occurs whenever data is corrupted during its transfer.
- The revised code appears instantly allowing the user to know that the modification has been made.

### Feature 4: Error Detection and Correction

- The program performs all three types of parity checks on the encoded data.
- From there, the syndrome is determined and the precise wrong bit is identified.
- The wrong bit is corrected to whatever it was supposed to be in the first place.
- The original program and its corrections are both provided along with an explanation of what occurred.

## 6. Technologies and Tools

We are trying to keep the tech stack very minimal. There is really no need to use complex technology for such a specific task. This is all that we will be using:

- **HTML** – This will handle the structure of the page, including all the input fields, buttons, and output areas.
- **CSS** – this is what gives everything its presentable look and provides us with color code for parity and data bits.
- **JavaScript** – it is JavaScript that performs all the necessary computation including parity calculations, syndrome and correction.

### Technologies We Are Staying Away From

- There are no React/Angular/Vue-like structures; this would definitely be an overkill for a one-page solution.
- There’s no need for a database; it will all take place on the browser.
- No back-end code — everything is front end.
- No third-party libraries or CDNs – we want it to work offline, simply by double-clicking the file.

## 7. Division of Responsibilities

### Member 1 – Amin Bin Rashid (Front-End Development)

- Outlining how the page will look like before you write any code.
- Constructing the HTML in `index.html` — all the input boxes, buttons, and output display boxes.
- Making sure all of the coding in `style.css` is neat, legible, and correctly colored.
- Ensuring that the seven boxes of bits align well and can be easily clicked on.
- Checking the look of the page at various screen sizes.
- Connecting the buttons so that clicking on them will trigger the JavaScript code.

### Member 2 – Tayyab Nisar (Back-End Development)

- Coding the entire logic from scratch in `script.js`.
- Constructing an encoder to transform four binary bits into a seven-bit Hamming code.
- Accurate computation of the parities for P1, P2, and P4.
- Implementing the click to flip functionality correctly upon clicking a particular bit.
- Creating the syndrome algorithm for finding and correcting the error location.
- Including input validation to display a nice message in case of erroneous user inputs.
- Developing a suite of tests cases to ensure that all features work correctly.

## 8. Expected Outcomes

Assuming that all goes well and as planned, the following will be our situation by the end of the semester:

- An algorithm which is guaranteed to encode any four-bit sequence into a seven-bit Hamming code.
- A clear and color-coded screen where you can easily tell which bits are parity bits and which are data bits.
- An instant reaction to a user’s mistake through a smooth and fast-click flipping process.
- A perfect error detection and correction scheme that always identifies and corrects the wrong bits.
- Step-by-step simple explanations to ensure understanding by someone who is reading about Hamming Code for the first time.
- A portable tool that works in all browsers without requiring any Internet connection or installation.

## 9. Sketch

*Project sketch/reference will be included seperately.*

---

## Installation

This project uses HTML, CSS, and JavaScript and is designed to run directly in a web browser.

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Open the project folder.
3. Open `index.html` in your web browser.

No additional installation or third-party libraries are required according to the project proposal.

## Usage

1. Open the Hamming Code Tool in your browser.
2. Enter four binary digits.
3. Generate the seven-bit Hamming Code.
4. Observe the parity bits and data bits.
5. Click any bit to simulate a transmission error.
6. Run the parity checks.
7. Observe the syndrome calculation and error location.
8. View the corrected Hamming Code and step-by-step explanation.

## Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes while maintaining the project's original functionality.
4. Test your changes.
5. Submit a pull request with a clear description of your modifications.

## License

No license has been specified for this project.

---

**Project:** Hamming Code Tool  
**Group:** G12  
**Department:** Computer Science  
**University:** Hitec University, Taxila.
