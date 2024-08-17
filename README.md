# employee-polls

This repository contains the starter code for the final assessment project of Udacity's React & Redux course. The project involves building a React/Redux-based frontend application that allows users to participate in and create polls.

## Project Overview

The application simulates a simple polling platform where users can create questions with two voting options, vote on questions, and view the results. The project is bootstrapped with [Create React App](https://github.com/facebook/create-react-app) and incorporates Redux for state management.

## Setup and Installation

To set up the project locally, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/employee-polls.git
   cd employee-polls
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```
   This will run the app in development mode. Open [http://localhost:3000](http://localhost:3000) in your browser to view it.

## Data Structure

The project uses a mock database represented by the `_DATA.js` file. This file contains two types of objects: `Users` and `Questions`.

### Users

Each user object includes the following properties:

| Attribute  | Type   | Description                                             |
|------------|--------|---------------------------------------------------------|
| `id`       | String | Unique identifier for the user                          |
| `password` | String | The user's password for logging into the application    |
| `name`     | String | The user's first and last name                          |
| `avatarURL`| String | Path to the user's avatar image                         |
| `questions`| Array  | List of question IDs created by the user                |
| `answers`  | Object | A mapping of question IDs to the user's selected answer |

### Questions

Each question object includes the following properties:

| Attribute   | Type   | Description                                            |
|-------------|--------|--------------------------------------------------------|
| `id`        | String | Unique identifier for the question                     |
| `author`    | String | ID of the user who created the question                |
| `timestamp` | String | Timestamp indicating when the question was created     |
| `optionOne` | Object | First voting option, including text and votes          |
| `optionTwo` | Object | Second voting option, including text and votes         |

### Voting Options

Each voting option is an object with the following properties:

| Attribute  | Type   | Description                                             |
|------------|--------|---------------------------------------------------------|
| `votes`    | Array  | List of user IDs who voted for this option              |
| `text`     | String | Text of the voting option                               |

## API Methods

The mock database provides the following methods to interact with the data:

### `_getUsers()`

- **Description**: Retrieves all users from the database.
- **Returns**: An object where each key is a user ID, and each value is a user object.

### `_getQuestions()`

- **Description**: Retrieves all questions from the database.
- **Returns**: An object where each key is a question ID, and each value is a question object.

### `_saveQuestion(question)`

- **Description**: Saves a new question to the database. Throws an error if required parameters are missing.
- **Parameters**: An object containing:
  - `author`: String (ID of the user who created the question)
  - `optionOneText`: String (Text for the first voting option)
  - `optionTwoText`: String (Text for the second voting option)
- **Returns**: An object representing the newly created question.

### `_saveQuestionAnswer(object)`

- **Description**: Saves a user's answer to a specific question. Throws an error if required parameters are missing.
- **Parameters**: An object containing:
  - `authedUser`: String (ID of the user who answered the question)
  - `qid`: String (ID of the question being answered)
  - `answer`: String (The selected option, either `"optionOne"` or `"optionTwo"`)

## Available Scripts

In the project directory, you can run the following scripts:

- **`npm start`**: Runs the app in development mode. The page will reload if you make edits, and you will see any lint errors in the console.
- **`npm test`**: Launches the test runner in interactive watch mode.
- **`npm run build`**: Builds the app for production to the `build` folder. The build is optimized for the best performance.

## Learn More

For more information about using Create React App, visit the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn more about React, visit the [React documentation](https://reactjs.org/).
