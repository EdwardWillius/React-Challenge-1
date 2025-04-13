# React-Challenge-1

// App.jsx
import React, { useState } from 'react';

const App = () => {
  const [value1, setValue1] = useState('');
  const [value2, setValue2] = useState('');
  const [result, setResult] = useState(null);

  const handleMultiply = () => {
    const num1 = parseFloat(value1);
    const num2 = parseFloat(value2);
    if (!isNaN(num1) && !isNaN(num2)) {
      setResult(num1 * num2);
    } else {
      setResult('Masukkan angka yang valid');
    }
  };

  return (
    <div>
      <h1>Kalkulator Perkalian</h1>
      <input
        type="number"
        value={value1}
        onChange={(e) => setValue1(e.target.value)}
        placeholder="Masukkan angka pertama"
      />
      <input
        type="number"
        value={value2}
        onChange={(e) => setValue2(e.target.value)}
        placeholder="Masukkan angka kedua"
      />
      <button onClick={handleMultiply}>Kalikan</button>
      {result !== null && <h2>Hasil: {result}</h2>}
    </div>
  );
};

export default App;
