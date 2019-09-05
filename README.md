# rockPaperScissors
refactoring a game into one block of code
Originally there were 3 objects housed outside of playGame(). This project is meant to refactor these objects into one block of code that is capable of doing the same thing as the original. Below you can find the original code that is being reworked.

const getUserChoice = userInput => {
    userInput = userInput.toLowerCase();
   if (userInput === 'rock' || userInput === 'paper' || userInput === 'scissors' || userInput === 'bomb') {
        return userInput;
  } else {
        console.log('Error!');
  }
  }
  
  
  
  const getComputerChoice = () =>{
    const randomNumber = 
          Math.floor(Math.random() * 3);
                switch(randomNumber) {
            case 0:
              return 'rock';
            case 1:
              return 'paper';
            case 2:
              return 'scissors';
                }
  }
  
  
  
  const determineWinner = (userChoice, computerChoice) =>{
    if (userChoice === computerChoice) {
        return 'It is a tie!';
    }
    if (userChoice === 'bomb'){
        return 'Wow, what a win!';
    }
    if (userChoice === 'rock'){
      if (computerChoice === 'paper') {
        return 'You lose!';
      } else {
        return 'You win!';
      }
    }
    if (userChoice === 'paper'){
      if (computerChoice === 'scissors') {
        return 'You lose!';
      } else {
        return 'You win!';
      }
    }
    if (userChoice === 'scissors'){
      if (computerChoice === 'rock') {
        return 'You lose!';
      } else {
        return 'You win!';
      }
    }
  }
   

    
  /* pulls the previous functions in order to create the game. Below, 'userChoice' would be input from an HTML page. so where it says 'rock' would be pulling info from the HTML and placing it into function getUserChoice*/
  const playGame = () => {
    const userChoice = 
  getUserChoice('paper'); /*This is where a call from the HTML would be linked, where the userInput is initially created*/
    const computerChoice = getComputerChoice();
    console.log('You threw: ' + userChoice);
    console.log('The computer threw: ' + computerChoice);
    
    console.log(determineWinner(userChoice, computerChoice));
  };
      
  playGame();
