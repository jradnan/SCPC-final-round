**// >>>>>>>>>>>>>>>>// Task 1<<<<<<<<<<<<<<<<<<<<<<<<
// Create a function that takes a string as input and returns the reversed version of the string without using the built-in reverse() method.

function reverseString(inputString) {
  let reversedString = '';

  for (let i = inputString.length - 1; i >= 0; i--) {
    reversedString += inputString.charAt(i);
  }

  return reversedString;
}

const input = "Hello, world!";
const reversed = reverseString(input);
console.log(reversed); 

**// >>>>>>>>>>>>>>>>// Task 2<<<<<<<<<<<<<<<<<<<<<<<<
// Create a function that takes an array of numbers as input and returns the sum of all positive numbers in the array. 

function sumOfPositiveNumbers(numbers) {
  let sum = 0;

  for (let i = 0; i < numbers.length; i++) {
    if (numbers[i] > 0) {
      sum += numbers[i];
    }
  }

  return sum;
}

const numbers = [2, -5, 10, -3, 7];
const positiveSum = sumOfPositiveNumbers(numbers);
console.log(positiveSum);



**// >>>>>>>>>>>>>>>>// Task 3<<<<<<<<<<<<<<<<<<<<<<<<
// Write a JavaScript program to find the most frequent element in an array and return it.


function mostFrequentElement(arr) {
  const frequencyMap = {};

  for (let i = 0; i < arr.length; i++) {
    const element = arr[i];
    if (frequencyMap[element] === undefined) {
      frequencyMap[element] = 1;
    } else {
      frequencyMap[element]++;
    }
  }

  let mostFrequentElement = arr[0];
  let highestFrequency = 1;

  for (const element in frequencyMap) {
    if (frequencyMap[element] > highestFrequency) {
      mostFrequentElement = element;
      highestFrequency = frequencyMap[element];
    }
  }

  return mostFrequentElement;
}

const arr = [3, 5, 2, 5, 3, 3, 1, 4, 5];
const mostFrequent = mostFrequentElement(arr);
console.log("Most frequent element:", mostFrequent); 





**// >>>>>>>>>>>>>>>>// Task 4<<<<<<<<<<<<<<<<<<<<<<<<
// Create a function that takes a sorted array of numbers and a target value as input. The function should find two numbers in the array that add up to the target value. Return an array containing the indices of the two numbers.

function findTwoNumbersWithSum(sortedArray, target) {
  let left = 0;
  let right = sortedArray.length - 1;

  while (left < right) {
    const sum = sortedArray[left] + sortedArray[right];

    if (sum === target) {
      return [left, right];
    } else if (sum < target) {
      left++;
    } else {
      right--;
    }
  }

  return [];
}

const sortedArray = [1, 3, 5, 7, 9, 11];
const target = 12;

const indices = findTwoNumbersWithSum(sortedArray, target);
if (indices.length === 2) {
  console.log(`Indices of the two numbers: ${indices[0]}, ${indices[1]}`);
  console.log(`Numbers: ${sortedArray[indices[0]]}, ${sortedArray[indices[1]]}`);
} else {
  console.log("No pair found.");
}




**// >>>>>>>>>>>>>>>>// Task 5<<<<<<<<<<<<<<<<<<<<<<<<
// Create a program that generates a random password of a specified length. The password should include a mix of uppercase letters, lowercase letters, numbers, and special characters.

function generateRandomPassword(length) {
  const uppercaseChars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  const lowercaseChars = "abcdefghijklmnopqrstuvwxyz";
  const numberChars = "0123456789";
  const specialChars = "!@#$%^&*()-_=+[{]};:'\"<>,.?/";

  const allChars = uppercaseChars + lowercaseChars + numberChars + specialChars;
  let password = "";

  for (let i = 0; i < length; i++) {
    const randomIndex = Math.floor(Math.random() * allChars.length);
    password += allChars[randomIndex];
  }

  return password;
}

const passwordLength = 12;
const randomPassword = generateRandomPassword(passwordLength);
console.log(randomPassword);




**// >>>>>>>>>>>>>>>>// Task 6<<<<<<<<<<<<<<<<<<<<<<<<
// Implement a function that converts a Roman numeral to an integer. The function should take a Roman numeral string (e.g., "IX" or "XXI") as input and return the corresponding integer value.


function romanToInt(romanNumeral) {
  const romanNumeralsMap = {
    'I': 1,
    'V': 5,
    'X': 10,
    'L': 50,
    'C': 100,
    'D': 500,
    'M': 1000,
  };
  
  let result = 0;
  let prevValue = 0;
  
  for (let i = romanNumeral.length - 1; i >= 0; i--) {
    const currentChar = romanNumeral[i];
    const currentValue = romanNumeralsMap[currentChar];
    
    if (currentValue >= prevValue) {
      result += currentValue;
    } else {
      result -= currentValue;
    }
    
    prevValue = currentValue;
  }
  
  return result;
}

console.log(romanToInt("IX"));
console.log(romanToInt("XXI"));
console.log(romanToInt("IV"));
console.log(romanToInt("XC"));
console.log(romanToInt("CXLIV"));


**// >>>>>>>>>>>>>>>>// Task 7<<<<<<<<<<<<<<<<<<<<<<<<
// Implement a JavaScript function to find the second smallest element in an array of numbers. The function should return the second smallest number.

function findSecondSmallest(arr) {
  if (arr.length < 2) {
    throw new Error("Array must contain at least two elements.");
  }

  let smallest = Infinity;
  let secondSmallest = Infinity;

  for (let num of arr) {
    if (num < smallest) {
      secondSmallest = smallest;
      smallest = num;
    } else if (num < secondSmallest && num !== smallest) {
      secondSmallest = num;
    }
  }

  if (secondSmallest === Infinity) {
    throw new Error("No second smallest element found.");
  }

  return secondSmallest;
}

const numbers2 = [8, 3, 5, 1, 9, 2, 7];


console.log(findSecondSmallest(numbers2)); 








