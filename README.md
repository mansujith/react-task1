///////useMemo
import React, { useState, useMemo } from 'react';

function Usememo() {
  // State for the input number
  const [number, setNumber] = useState(0);

  // Memoizing the factorial calculation function directly inside useMemo()
  const factorial = useMemo(() => {
    // Function to calculate factorial
    const calculateFactorial = (n) => {
      console.log('Calculating factorial...');
      if (n <= 0) return 0;
      return n *n;
    };

    return calculateFactorial(number); // Use the function and return its result
  }, [number]); // Dependency array: re-run when number changes

  return (
    <div>
      <h1>Square Of A Number</h1>

      <div>
        <p>Current Number: {number}</p>
        <button onClick={() => setNumber(number + 1)}>Increment Number</button>
      </div>

    
      <div>
        <h2>Sauare of a {number}: {factorial}</h2>
      </div>
    </div>
  );
}

export default Usememo;



