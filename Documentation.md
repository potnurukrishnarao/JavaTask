# JavaTask
### Advanced Calculator Program Documentation

#### Table of Contents
1. Introduction
2. Program Overview
3. Usage Instructions
4. Code Structure
5. Methods
6. Error Handling
7. Dependencies

---

#### 1. Introduction:
The Advanced Calculator program is a Java application designed to perform arithmetic calculations with additional features such as exponentiation. 
It provides a user-friendly interface to input mathematical operations and two numbers, then calculates and displays the result. 
The program includes error handling for division by zero and invalid operations.

#### 2. Program Overview:
The program consists of a single Java class named AdvancedCalculator.
It utilizes the java.util.Scanner class for user input and implements a main loop to keep the calculator running until the user decides to quit.

#### 3. Usage Instructions:
- Run the program.
- Enter one of the following operations: + (addition), - (subtraction), * (multiplication), / (division), ^ (exponentiation), or 'quit' to exit.
- If a valid operation is entered, the program prompts for two numbers.
- Enter the numbers.
- The program calculates and displays the result.
- Repeat steps 2-5 or enter 'quit' to exit the program.

#### 4. Code Structure:
- The main method controls the flow of the program, including input handling and calling the calculate method for arithmetic operations.
- The calculate method performs the calculation based on the provided operation and two numbers.

#### 5. Methods:
- main(String[] args): Entry point of the program. Prompts the user for input, handles calculations, and controls program flow.
- calculate(String operation, double num1, double num2): Performs the calculation based on the provided operation and two numbers. Returns the result.

#### 6. Error Handling:
- *Division by zero*: If the user tries to divide by zero, the program displays an error message and returns Double.NaN (Not a Number) as the result.
- *Invalid operation*: If the user enters an invalid operation, the program displays a message and prompts the user to try again.

#### 7. Dependencies:
- java.util.Scanner: Used for reading user input.

---

This documentation provides a comprehensive overview of the Advanced Calculator program, including its features, usage instructions, code structure, methods, error handling, and dependencies.
      
//code
<-----
java
import java.util.Scanner;

public class AdvancedCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean quit = false;

        // Main loop to keep the calculator running until the user decides to quit
        while (!quit) {
            System.out.println("Enter the operation (+, -, *, /, ^) or 'quit' to exit:");
            String operation = scanner.nextLine();

            switch (operation) {
                // Perform calculation based on user input
                case "+":
                case "-":
                case "*":
                case "/":
                case "^":
                    System.out.println("Enter first number:");
                    double num1 = scanner.nextDouble(); // Read the first number
                    System.out.println("Enter second number:");
                    double num2 = scanner.nextDouble(); // Read the second number
                    double result = calculate(operation, num1, num2); // Perform calculation
                    System.out.println("Result: " + result); // Display the result
                    break;
                // Quit the calculator if user inputs "quit"
                case "quit":
                    quit = true;
                    break;
                // Handle invalid input
                default:
                    System.out.println("Invalid operation. Try again.");
                    break;
            }
            scanner.nextLine(); // Consume newline
        }
        scanner.close(); // Close the scanner
    }

    // Method to perform the calculation based on the operation provided
    public static double calculate(String operation, double num1, double num2) {
        switch (operation) {
            case "+":
                return num1 + num2;
            case "-":
                return num1 - num2;
            case "*":
                return num1 * num2;
            case "/":
                if (num2 != 0) {
                    return num1 / num2;
                } else {
                    // Handle division by zero
                    System.out.println("Error: Division by zero.");
                    return Double.NaN; // Return NaN (Not a Number) for division by zero
                }
            case "^":
                return Math.pow(num1, num2); // Calculate num1 raised to the power of num2
            default:
                // Handle invalid operation
                return Double.NaN; // Return NaN for invalid operation
        }
    }
}


----->

Program images :

![Screenshot 2024-03-18 123414](https://github.com/potnurukrishnarao/JavaTask/assets/163103947/3fd71e08-0082-49ad-9c4c-47106005a82c)
![Screenshot 2024-03-18 123427](https://github.com/potnurukrishnarao/JavaTask/assets/163103947/93f39eae-5ca9-4a4c-8789-5b7293e19a9e)

