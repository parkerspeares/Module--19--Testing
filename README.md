Challenge-19: Cypress Testing
Overview
This project demonstrates Cypress testing using TypeScript. It is licensed under the MIT License.

Watch a demo of the Cypress tests here!

Contents
Required Technologies
Installation
Usage
Code Snippets
Features
License
Technologies Used
Credits

Required Technologies
This project requires Node.js, which includes the npm package manager. Download Node.js here, and follow the installation instructions.

MongoDB is also required for this project. Visit MongoDB’s website for download and setup instructions.

Installation
After downloading the files, open the project folder and launch a terminal in the root directory.
Run npm install and npm run install to install dependencies.
Navigate to the server folder and remove the .EXAMPLE extension from the .env.EXAMPLE file, then save.
Run npm run seed to populate the database with quiz questions.
To start the application, run npm run build to build both server and client, followed by npm run start:dev to launch both.
Additional commands are listed in the package.json file.

Usage
On launch, the home page features a button to start the quiz. Each page will present a question with four answer choices. Clicking an answer moves to the next question. At the end, your score is displayed, with an option to restart the quiz.

For this assignment, Cypress tests were designed to verify the quiz’s functionality. After starting the server and page, you can open a separate terminal to run tests. Use:

npm run test for terminal-based tests
npm run cypress to run tests in the Cypress GUI (recommended for clarity)
Running userJourney.cy.js in the Cypress GUI will trigger the end-to-end tests.

The tests check:

Functionality of the start button
Display of new questions after an answer is clicked
Display of a completion message after all questions are answered
Display of the score on the results page
Restart functionality via the restart button
All tests should pass. If tests fail, confirm all dependencies are installed correctly.

Code Snippet
This code verifies that the quiz displays a completion message after all questions are answered:

javascript
Copy code
it("When all questions are answered then the quiz is over.", () => {
    cy.get("div button").click(); // Start quiz

    for (let x = 0; x < 10; x++) {
        cy.get("div button").eq(0).click(); // Select answer for each question
    }

    cy.get("div h2").invoke("text").should("equal", "Quiz Completed"); // Check completion message
});

Features
Quiz functionality: Start, answer questions, display score, restart
Cypress testing for functionality verification

License
This project is licensed under the MIT License.

Technologies Used
Node.js
Visual Studio Code
Stack Overflow
W3 Schools

Credits
Parker Speares
