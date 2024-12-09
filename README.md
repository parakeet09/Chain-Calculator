# Chain Calculator

The Chain Calculator is a React-based web application that calculates mathematical outputs through a configurable chain of functions. Each function is interconnected, forming a chain, and the application's core functionality dynamically updates based on user inputs and function chaining

## Features

1. **Dynamic Function Chain**:
   - Supports 5 functions by default.
   - Each function has an input field for mathematical equations.
   - Equations support basic arithmetic operations (`+`, `-`, `*`, `/`) and exponents (`^`).

2. **Interactive Chain Editing**:
   - Toggle editing mode to allow users to modify the chaining order.
   - Ensures each function has one incoming and one outgoing connection.

3. **Real-Time Calculations**:
   - Automatically recalculates the final output as the user updates inputs, equations, or chaining logic.
   - Displays "Error" for invalid inputs, cyclic dependencies, or incomplete chains.

4. **ReactFlow Integration**:
   - Visual representation of the input, functions, and output.
   - Connected lines dynamically update to reflect the chaining order.

5. **Error Handling**:
   - Prevents cyclic dependencies during chaining.
   - Displays error messages for invalid inputs or equations.

---

## Installation and Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/parakeet09/Chain-Calculator.git
   cd Chain-Calculator
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

4. Open the application in your browser:
   ```
   http://localhost:3000
   ```

---

## Usage

### Input Value
- Enter a numeric value in the input box labeled "Input".

### Function Equations
- Each function has an editable text field for its mathematical equation.
- Examples:
  - `x + 2`: Adds 2 to the input value.
  - `x^2`: Squares the input value.
  - `x/2`: Divides the input value by 2.

### Editing Chain Order
- Click the "Enable Editing Chain" button.
- Modify the chaining logic using the dropdown menus.
- Ensure the chain ends with the output connected to `function3`.

### Example Scenario
1. Initial chain: `Input -> Function1 -> Function2 -> Function4 -> Function5 -> Function3 -> End`
2. Input value: `2`
3. Equations:
   - `Function1`: `x + 3`
   - `Function2`: `x / 2`
   - `Function4`: `2x + 1`
   - `Function5`: `x^2`
   - `Function3`: `x / 2`
4. Output calculation:
   - `Input -> Function1 (2 + 3 = 5)`
   - `Function1 -> Function2 (5 / 2 = 2.5)`
   - `Function2 -> Function4 (2.5 * 2 + 1 = 6)`
   - `Function4 -> Function5 (6^2 = 36)`
   - `Function5 -> Function3 (36 / 2 = 18)`
   - Final Output: `18`

---

## Files and Structure

### Components
1. **FunctionChainCalculator.tsx**:
   - Main component handling state, ReactFlow integration, and overall logic.
2. **NodeGenerator.tsx**:
   - Generates nodes for ReactFlow.
3. **EdgeGenerator.ts**:
   - Dynamically generates edges based on the chaining logic.

### Utilities
1. **calculations.ts**:
   - Handles mathematical evaluations and chain result calculations.

---

## Known Issues
- Ensure that all functions have valid equations; otherwise, "Error" will be displayed.
- Avoid cyclic dependencies during chain editing.

---

## Future Improvements
- Add support for drag-and-drop functionality for chaining.
- Increase the number of functions dynamically.
- Enhance error messages for better user feedback.

