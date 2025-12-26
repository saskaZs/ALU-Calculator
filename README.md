# 🔢 ALU Simulation in Excel

An educational simulation of an **Arithmetic Logic Unit (ALU)** in Excel, demonstrating binary operations like addition, subtraction, multiplication, and division at the gate level.

This project uses spreadsheet formulas to mimic digital logic gates (e.g., AND, OR, NOT) and components like full adders/subtractors, providing a step-by-step visualization of how basic arithmetic works in binary.

---

## 🚀 Features

- **Gate-Level Simulation:** Breaks down operations into individual logic gates and multiplexers.
- **Binary Representations:** Shows inputs, outputs, carries/borrows, and intermediate steps in binary (with decimal conversions).
- **Multiple Operations:** Separate sheets for Adder, Subtractor, Multiplier, and Divider.
- **Educational Focus:** Ideal for learning digital electronics, computer architecture, and binary arithmetic.
- **No Code Required:** Pure Excel – open and explore!

---

## 📂 Project Structure
`ALU.xlsx`     # The main Excel file with simulation sheets
`README.md`    # This file


---

## 📊 The Simulations

The Excel file (`ALU.xlsx`) contains four sheets, each simulating a different ALU operation using example inputs. Binary bits are represented in columns (e.g., BIT 7 to BIT 0), with rows showing inputs, gates, and outputs.

### Sheet: ADDER
- Simulates binary addition using a full adder.
- Example: 31 (00011111) + 61 (00111101) = 92 (01011100)

### Sheet: SUBSTRACTER
- Simulates binary subtraction using a full subtractor.
- Example: 31 (00011111) - 61 (00111101) = -30 (represented as 11100010 in two's complement)

### Sheet: MULTIPLIER
- Simulates binary multiplication with row-by-row shifts and additions.
- Example: 10 (00001010) × 189 (10111101) = 1890 (0000011101011010)

### Sheet: DIVIDER
- Simulates binary division using shifts, subtractors, and multiplexers.
- Example: 26 (00011010) ÷ 6 (00000110) = Quotient 4 (00000100), Remainder 2 (00000010)

Each sheet includes:
- Input rows (IN 1, IN 2)
- Gate outputs (e.g., Gate 1–7)
- Carry/Borrow bits
- Final output and decimal equivalents

---

## 🧠 Theoretical Background

An ALU is a fundamental component of a CPU that performs arithmetic and logic operations. This simulation focuses on arithmetic operations in binary.

### 1. Full Adder
Used for addition. For each bit position:
- Takes two input bits (A, B) and a carry-in (Cin).
- Outputs: Sum = A XOR B XOR Cin, Carry-out = (A AND B) OR (A AND Cin) OR (B AND Cin)

**Formula for Sum Bit:**
$$ S = A \oplus B \oplus C_{in} $$

**Formula for Carry-Out:**
$$ C_{out} = (A \cdot B) + (A \cdot C_{in}) + (B \cdot C_{in}) $$

### 2. Full Subtractor
Used for subtraction (A - B). Similar to adder but with borrow.
- Outputs: Difference = A XOR B XOR Bin, Borrow-out = (~A AND B) OR (~A AND Bin) OR (B AND Bin)

**Formula for Difference:**
$$ D = A \oplus B \oplus B_{in} $$

**Formula for Borrow-Out:**
$$ B_{out} = (\neg A \cdot B) + (\neg A \cdot B_{in}) + (B \cdot B_{in}) $$

### 3. Multiplier
Implements shift-and-add method:
- Multiply each bit of the multiplier with the multiplicand, shift left, and add results.

### 4. Divider
Uses restoring division algorithm:
- Repeatedly shift and subtract the divisor from the dividend, deciding quotient bits based on borrow.

The sheets use Excel cells to represent bits (0/1) and formulas to simulate gates, making it easy to trace the logic flow.

---

## 🛠️ How to Use

1. Download `ALU.xlsx`.
2. Open it in Microsoft Excel (or compatible software like Google Sheets/LibreOffice Calc).
3. Navigate between sheets (ADDER, SUBSTRACTER, MULTIPLIER, DIVIDER).
4. Modify input bits in the "IN 1" and "IN 2" rows to see real-time changes in gates, carries, and outputs.
   - Ensure inputs are 0 or 1 in binary columns.
   - Decimal values will update automatically if formulas are set.

**Note:** The simulation assumes 8-bit unsigned/signed binary (extendable). For negative numbers in subtraction, it uses two's complement.
