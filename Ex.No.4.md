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
## index.js
```
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```
## APP.JS
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      calculateResult();
    } else if (value === 'AC') {
      setInput('');
    } else if (value === '⌫') {
      setInput((prevInput) => prevInput.slice(0, -1));
    } else {
      setInput((prevInput) => prevInput + value);
    }
  };

  const calculateResult = () => {
    try {
      setInput(eval(input).toString());
    } catch (error) {
      setInput('Error');
    }
  };

  return (
    <div className="calculator">
      <h1>Calculator</h1>
      <div className="display">
        <input type="text" value={input} readOnly />
        
      </div>
      <div className="buttons">
        {[ 'AC', '⌫', '%', '/', '7', '8', '9', '*', '4', '5', '6', '-', '1', '2', '3', '+', '0', '.', '=' ].map((button) => (
          <button
            key={button}
            onClick={() => handleClick(button)}
            className={`button-circle ${
              button === '=' ? 'equals' :
              button === 'AC' ? 'all-clear' :
              button === '⌫' ? 'backspace' :
              ['/','*','-','+','%'].includes(button) ? 'operator' : 'number'
            }`}
          >
            {button}
          </button>
        ))}
      </div>
      <footer className="footer">
      </footer>
    </div>
  );
}

export default App;
```
## AP.CSS:
```
body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(135deg, #3e1e68, #2d0b42);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.calculator {
  background: #8064b3;
  padding: 25px;
  border-radius: 20px;
  box-shadow: 0px 10px 30px rgba(180, 90, 255, 0.3);
  width: 350px;
  text-align: center;
}
.display {
  background: #8d7cb2;
  padding: 20px;
  border-radius: 12px;
  margin-bottom: 20px;
  box-shadow: inset 0px 0px 10px rgba(180, 90, 255, 0.4);
}

.display input {
  width: 100%;
  height: 50px;
  font-size: 28px;
  text-align: right;
  padding: 10px;
  border: none;
  background: transparent;
  color: #e2d5e2;
  outline: none;
}
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 12px;
}

button {
  width: 65px;
  height: 65px;
  font-size: 22px;
  cursor: pointer;
  border: none;
  background: #4a2c6e;
  color: #ffffff;
  border-radius: 50%;
  transition: background 0.3s ease, transform 0.1s ease;
  box-shadow: 0 5px 15px rgba(180, 90, 255, 0.3);
}

button:hover {
  background: #5b3b80;
}

button:active {
  background: #714dab;
  transform: scale(0.9);
}

.equals {
  background: #ff5722;
  color: #fff;
}

.equals:hover {
  background: #e64a19;
}

.all-clear {
  background: #ff3333;
}

.all-clear:hover {
  background: #cc0000;
}

.backspace {
  background: #3399ff;
}

.backspace:hover {
  background: #007acc;
}


.operator {
  background: #009688;
}

.operator:hover {
  background: #00796b;
}
.footer {
  margin-top: 20px;
  padding: 15px;
  text-align: center;
  font-size: 14px;
  color: #efeaea;
}
```

## OUTPUT

![image](https://github.com/user-attachments/assets/837df023-ab4f-411f-a626-6d713b380ce0)

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
