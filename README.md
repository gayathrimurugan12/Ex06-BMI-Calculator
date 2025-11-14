# Ex06 BMI Calculator

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
## App.jsx
```
import React, { useState } from 'react';

function App() {
  const [height, setHeight] = useState('');
  const [weight, setWeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [category, setCategory] = useState('');

  const calculateBMI = () => {
    const h = parseFloat(height);
    const w = parseFloat(weight);

    if (h > 0 && w > 0) {
      const bmiValue = w / ((h / 100) ** 2);
      setBmi(bmiValue.toFixed(1));

      if (bmiValue < 18.5) setCategory('Underweight');
      else if (bmiValue < 24.9) setCategory('Normal');
      else if (bmiValue < 29.9) setCategory('Overweight');
      else setCategory('Obese');
    } else {
      setBmi(null);
      setCategory('');
    }
  };

  return (
    <div className="page">
      <h1>Body Mass Index Calculator</h1>
      <input
        type="number"
        placeholder="Height (cm)"
        value={height}
        onChange={(e) => setHeight(e.target.value)}
      />
      <input
        type="number"
        placeholder="Weight (kg)"
        value={weight}
        onChange={(e) => setWeight(e.target.value)}
      />
      <button onClick={calculateBMI}>Calculate BMI</button>

      {bmi && (
        <div className="result">
          <p><strong>Your BMI:</strong> {bmi}</p>
          <p><strong>Category:</strong> {category}</p>
        </div>
      )}
    </div>
  );
}

export default App;

```
## index.css
```
body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', sans-serif;
  background-color: #000000; /* Dark ninja background */
  color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.page {
  background: linear-gradient(to bottom right, #1a1a1a, #000000);
  border: 2px solid #ff0000;
  border-radius: 12px;
  box-shadow: 0 0 20px rgba(255, 0, 0, 0.6);
  padding: 30px;
  max-width: 400px;
  width: 100%;
  text-align: center;
}

h1 {
  color: #ff0000; /* Red ninja accent */
  margin-bottom: 20px;
  text-shadow: 0 0 10px #ff0000;
}

input {
  width: 90%;
  padding: 10px;
  margin: 10px 0;
  background-color: #111;
  border: 1px solid #ff0000;
  border-radius: 8px;
  color: #fff;
}

input::placeholder {
  color: #aaa;
}

button {
  background-color: #ff0000;
  color: white;
  border: none;
  border-radius: 8px;
  padding: 10px 20px;
  margin-top: 10px;
  cursor: pointer;
  transition: background-color 0.3s;
  font-weight: bold;
}

button:hover {
  background-color: #cc0000;
  box-shadow: 0 0 10px #ff0000;
}

.result {
  margin-top: 20px;
  font-size: 18px;
  color: #ffdddd;
  text-shadow: 0 0 5px #ff0000;
}


```

## OUTPUT
![image](https://github.com/user-attachments/assets/0c618fe6-8d4b-41e9-a0f3-48e9f6ddbc4e)


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
