# catalog_assignemt

Shamir's Secret Sharing Algorithm in Java
This project implements a simplified version of the Shamir's Secret Sharing algorithm in Java. The task involves reading a JSON input file containing roots of a polynomial, decoding values encoded in various number bases, and calculating the constant term (c) of the polynomial using Lagrange interpolation.

Table of Contents
Overview
Features
Technologies Used
Setup Instructions
Usage
Input Format
Output
Implementation Details
License
Overview
Shamir's Secret Sharing is a cryptographic algorithm that allows a secret to be divided into parts, called shares, and reconstructed only when a minimum number of shares (k) are combined. This project focuses on decoding the values from JSON input and solving for the constant term (c) of a polynomial using interpolation techniques.

Features
Reads polynomial roots from a JSON file.
Decodes y values encoded in various bases.
Uses Lagrange interpolation to compute the constant term of the polynomial.
Error-free and modular implementation for easy understanding and extensibility.
Technologies Used
Java: Core programming language.
File Handling: For reading the JSON input file.
Lagrange Interpolation: To compute the constant term (c).
Setup Instructions
Clone the Repository:

bash
Copy code
git clone https://github.com/<your-username>/<repository-name>.git
cd <repository-name>
Ensure Java is Installed:

Check Java version:
bash
Copy code
java -version
Install Java if not available.
Prepare the Input File:

Create a file named input.json in the project directory and paste the required JSON input. An example is provided in the Input Format section.
Compile and Run:

Compile the code:
bash
Copy code
javac ShamirSecretSharing.java
Execute the program:
bash
Copy code
java ShamirSecretSharing
Usage
Place the JSON input file (input.json) in the project directory.
Run the program, and it will compute and display the constant term (c) of the polynomial.
Input Format
The input file should follow the JSON structure below:

json
Copy code
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}
Explanation:
keys.n: Number of roots provided.
keys.k: Minimum number of roots required to solve the polynomial.
Each root is represented as a key-value pair, where:
key: Represents x.
base: Specifies the number system used for the y value.
value: Encoded y value in the given base.
Output
The program computes the constant term of the polynomial (c). For the example input, the output would be:

csharp
Copy code
The secret constant (c) is: 3
Implementation Details
File Reading:

The readFile method reads the content of the input.json file and returns it as a string.
JSON Parsing:

The parseJSON method extracts x and decoded y values from the JSON string.
Value Decoding:

The decodeValue method converts y values from their respective bases into decimal integers.
Constant Term Calculation:

The findConstantTerm method applies Lagrange interpolation to compute the constant term (c).
Example Walkthrough
Input:
json
Copy code
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}
Decoded Values:
(x=1, y=4)
(x=2, y=7) (decoded from base 2)
(x=3, y=12)
(x=6, y=39) (decoded from base 4)
Output:
csharp
Copy code
The secret constant (c) is: 3
License
This project is licensed under the MIT License. See the LICENSE file for more details.

Feel free to replace <your-username> and <repository-name> with the actual GitHub details. Let me know if you’d like further refinements!
