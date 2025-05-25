# Ex04 Simple Calculator - React Project
## Date:

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
### Calculator.js
```
import React, { useState } from 'react';
import './Calculator.css';

export default function Calculator() {
  const [display, setDisplay] = useState('');

  const handleClick = (value) => {
    switch (value) {
      case 'C':
        setDisplay('');
        break;
      case '⬅️': // Backspace
        setDisplay((prev) => prev.slice(0, -1));
        break;
      case '🟰': // Equals
        try {
          // eslint-disable-next-line no-eval
          const result = eval(display);
          setDisplay(String(result));
        } catch {
          setDisplay('Error');
        }
        break;
      default:
        // Map symbols to JS operators
        const mapping = {
          '➗': '/',
          '✖️': '*',
          '➖': '-',
          '➕': '+',
          '%': '%'
        };
        const toAppend = mapping[value] ?? value;
        setDisplay((prev) => prev + toAppend);
    }
  };

  const buttons = [
    'C', '%', '⬅️', '➗',
    '7', '8', '9', '✖️',
    '4', '5', '6', '➖',
    '1', '2', '3', '➕',
    '00', '0', '.', '🟰'
  ];

  return (
    <div className="calculator">
      <h1 className="calculator-title">Calculator</h1>
      <div className="display" data-testid="display">
        {display || '0'}
      </div>
      <div className="buttons">
        {buttons.map((btn) => (
          <button
            key={btn}
            className={`btn ${btn === '🟰' ? 'equals' : ''}`}
            onClick={() => handleClick(btn)}
          >
            {btn}
          </button>
        ))}
      </div>
      <footer className="footer">
        <p>&copy; Developed by: VASUNDRA SRI R</p>
        <p>Register Number: 212222230168</p>
      </footer>
    </div>
  );
}
```
### Calculator.css
```
.calculator {
  max-width: 320px;
  margin: 40px auto;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  background: #c7c1c1;
  padding: 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.calculator-title {
  margin: 0 0 15px;
  font-weight: 700;
  font-size: 1.8rem;
  color: #333;
  text-align: center;
  user-select: none;
}

.display {
  background-color: #222;
  color: rgb(244, 241, 238);
  font-size: 2rem;
  padding: 15px;
  border-radius: 6px;
  text-align: right;
  min-height: 50px;
  margin-bottom: 20px;
  user-select: none;
  overflow-x: auto;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

.btn {
  background-color: #8bdfe9;
  color: rgb(28, 27, 27);
  border: none;
  padding: 18px;
  border-radius: 6px;
  font-size: 1.2rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
  user-select: none;
}

.btn:hover {
  background-color: #3b97a1;
}

.btn:active {
  background-color: #3b97a1;
}

/* Ensure equals button is one cell wide */
.equals {
  /* no grid-column span here! */
  background-color: #6bcb9e;
}

.equals:hover {
  background-color: #15a261;
}

.equals:active {
  background-color: #15a261;
}

.footer {
  margin-top: 20px;
  padding: 15px;
  text-align: center;
  font-size: 14px;
  color: #181717;
}
```

## OUTPUT
![Screenshot 2025-05-25 162424](https://github.com/user-attachments/assets/07a6d454-5e7e-4a30-8678-ba794dbf9369)

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
