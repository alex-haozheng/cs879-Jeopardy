# rlo-jeopardy

Reusable Learning Object for CS 879

forked from [Brian Yu](https://github.com/brianyu28/jeopardy)

### **Step 1: Prerequisites**

- [Node](https://nodejs.org/en/)
- [NPM](https://www.npmjs.com/)
- [VSCode](https://code.visualstudio.com/)
    - Install the appropriate language support for each language used in the project.

### **Step 2: Clone the Repository**

- Navigate to the desired project directory on your computer.

- Clone the repository from [GitHub](https://github.com/alex-haozheng/cs879-Jeopardy.git) using the `git clone` command.

    ```
    $ git clone https://github.com/alex-haozheng/cs879-Jeopardy.git
    ```

- Navigate to the cloned repository directory.

    ```
    $ cd rlo-jeopardy
    ```

### **Step 3: Install Dependencies**

- Check that the terminal is in the correct directory.

    ```
    $ pwd
    ```
    or 
    ```
    $ ls
    ```

- Install the dependencies using the `npm install` command.

    ```
    $ npm install
    ```

### **Step 4: Run the Application**

    ```
    $ npm start
    ```
    - This will host the server on `http://localhost:3000/`.

### `game.json` specification

`game.json` must have the following keys.

- A `game` key that contains an object with:
  - A `single` key that contains an array of categories, where each category is an object containing:
    - A `category` key that contains the name of the category
    - A `clues` key that contains an array of clues, where each clue is an object containing:
      - A `value` key that contains the integer dollar value of the clue
      - A `clue` key that contains the clue
      - A `solution` key that contains the solution
      - An optional `dailyDouble` key, set to `true` if the clue is a daily double
      - An optional `html` tag to treat the clue and solution text as HTML
      - An optional `chosen` key, set to `true` if the clue has already been chosen (should be omitted if starting game from the beginning)
  - An optional `double` key that contains an array of categories, structured like the `single` round.
  - A `final` key that contains an object with:
    - A `category` key that contains the Final Jeopardy category
    - A `clue` key that contains the Final Jeopardy clue
    - A `solution` key that contains the Final Jeopardy solution
- An optional `players` key that contains an array of players, where each player is an object containing:
  - A `name` key with the player's name
  - A `score` key with the player's score (should initially be 0)
  - A `correct` key with the player's number of correct responses so far (should initially be 0)
  - An `incorrect` key with the player's number of incorrect responses so far (should initially be 0)
- An optional `round` key indicating which round to begin with (should initially be "single")