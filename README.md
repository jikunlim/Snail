# Snail
  snail = function snail(array) {    // Define a function named "snail" that takes an array as input
    const result = [];              // Create an empty array called "result" to store the snail traversal

    let startRow = 0, endRow = array.length - 1;     // Initialize start and end indices for the rows
    let startCol = 0, endCol = array[0].length - 1;  // Initialize start and end indices for the columns

    while (startRow <= endRow && startCol <= endCol) {   // Loop until all elements have been traversed
      // Traverse the top row from left to right
      for (let i = startCol; i <= endCol; i++) { 
        result.push(array[startRow][i]);    // Add the current element to the result array
      }
      startRow++;   // Move the start index to the next row

      // Traverse the right column from top to bottom
      for (let i = startRow; i <= endRow; i++) {
        result.push(array[i][endCol]);      // Add the current element to the result array
      }
      endCol--;     // Move the end index to the previous column

      // Traverse the bottom row from right to left
      if (startRow <= endRow) {            // Check if there are still rows left to traverse
        for (let i = endCol; i >= startCol; i--) {
          result.push(array[endRow][i]);   // Add the current element to the result array
        }
        endRow--;   // Move the end index to the previous row
      }

      // Traverse the left column from bottom to top
      if (startCol <= endCol) {            // Check if there are still columns left to traverse
        for (let i = endRow; i >= startRow; i--) {
          result.push(array[i][startCol]); // Add the current element to the result array
        }
        startCol++;  // Move the start index to the next column
      }
    }

    return result;   // Return the snail traversal of the input array
  }
