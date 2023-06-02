# Decentralized Student Information System - Server

The Decentralized Student Information System (DSIS) server repository is the backend component of DSIS. DSIS Server provides functionalities such as enrollment, term management, course evaluation, and attendance tracking. Built using Node.js, the server component acts as the bridge between the blockchain network and client applications, enabling seamless interactions with the decentralized student information system.

## Server Operations

- Smart Contract deployment :  The server deploys a student contract on the blockchain network using the provided parameters.
- Enrollment: : The server enrolls a student in the system. A new user is created in the Firebase Authentication system with the provided email and password. A smart contract gets deployed for the enrolling student and the contract address gets stored in the Firebase Firestore database along with other relevant information such as the student's name and email. The address of the smart contract is later retrieved from the Firebase Firestore database based on the student's ID. This address is used for further interactions with the blockchain.
- Adding a new term: The server adds a new term for a student. It interacts with the student's contract on the blockchain network and adds the term details.
- Adding a new course: The server adds a new course to a student's term. It interacts with the student's contract on the blockchain network and adds the course details along with evaluation weights and names.
- Setting course grades: The server sets the evaluation grade for a specific evaluation criterion of a course for a student. It interacts with the student's contract on the blockchain network and updates the evaluation grade. If all of the grades is set for a course's evaluation, the server sets the overall grade and letter grade for this course of a student.
- Attendance: The server increases the attendance count for a specific course of a student. It updates the attendance value in the student's contract on the blockchain network.

## API Endpoints

The server exposes the following API endpoints:

- **POST /signup**: Enroll a new student in the DSIS by providing their information.
- **POST /add-term**: Add a new term for a student.
- **POST /course-eval-grade**: Set the grade for a specific evaluation in a course for a student.
- **POST /add-course**: Add a new course for a student in a specific term.
- **POST /attendance**: Increase the attendance count for a student in a specific term and course.

## Smart Contracts

This repository contains a set of smart contracts for managing student information, courses, and evaluations on the Ethereum blockchain. The contracts are written in Solidity and can be deployed on an Ethereum network.

### Student.sol

The `Student.sol` contract represents a student and includes functions to retrieve student information such as name, faculty, department, registration year, and ID. It also provides methods to add terms, courses, and set grades for the courses.

### Term.sol

The `Term.sol` contract represents an academic term or semester. It allows the addition of courses to the term and provides a method to retrieve the list of courses associated with the term.

### Course.sol

The `Course.sol` contract represents a specific course. It includes functions to set attendance, overall grades, evaluation grades, and retrieve various details about the course such as the course name, code, instructor, and evaluation criteria.

### Usage

To use these smart contracts, you need to compile and deploy them on an Ethereum network. You can make use of Solidity development tools like Remix, Truffle, or Hardhat to compile and deploy the contracts.

1. Compile the contracts using a Solidity development tool of your choice.
2. Deploy the contracts on an Ethereum network. This can be done through a local development network or a public testnet like Sepolia.
3. Once the contracts are deployed, you can interact with them using a web interface or by calling their functions directly through Ethereum transactions.

## License

The Decentralized Student Information System project is open-source and released under the MIT License. You are free to use, modify, and distribute the project in accordance with the terms of the license.

