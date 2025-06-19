# ROCK-PAPER-SCISSORS-GAME

## Table of Contents
- [Project Description](#Project-Description)
- [How to Play](#How-to-Play)
- [Running the Game](#Running-the-Game)
- [Code Explanation](#Code-Explanation)
- [Full Code](#Full-Code)
- [Line-by-Line Explanation](#Line-by-Line-Explanation)
- [Tools and Technologies](#Tools-and-Technologies)
- [Example Usage](#Example-Usage)

### Project Description
This is a simple command-line Rock-Paper-Scissors game written in Python. The game pits the user against a computer opponent, with the computer's choice generated randomly. Players can continue playing rounds until they choose to quit, at which point the game displays the final scores and declares an overall winner based on the number of rounds won.

### How to Play
1. Start the Game: Run the Python script in a terminal or command-line interface.
2. Make a Choice: When prompted, type 'Rock', 'Paper', or 'Scissors'. The input is case-insensitive, so 'rock' or 'ROCK' works too.
3. Quit the Game: Type 'Q' (case-insensitive) to exit the game at any time.
4. Round Results: After each round, the computer’s choice and the result (win, lose, or tie) are displayed.
5. Final Results: Upon quitting, the total wins for both the user and computer are shown, along with the overall winner.

### Running the Game
To play the game, you need Python installed on your system. Save the code in a file named rock_paper_scissors.py and run it using the following command:
  - python rock_paper_scissors.py
  - 
### Code Explanation
Full Code
Here is the complete Python script for the Rock-Paper-Scissors game:
            import random

            def get_user_choice():
                while True:
                    user = input("Enter Rock/Paper/Scissors or Q to Quit: ").capitalize()
                    if user == 'Q':
                        return 'quit'
                    elif user in ["Rock", "Paper", "Scissors"]:
                        return user
                    else:
                        print("Invalid choice. Please enter Rock, Paper, Scissors, or Q.")
            
            def get_computer_choice():
                return random.choice(["Rock", "Paper", "Scissors"])
            
            def determine_winner(user, computer):
                if user == computer:
                    return 'tie'
                elif (user == "Rock" and computer == "Scissors") or \
                     (user == "Paper" and computer == "Rock") or \
                     (user == "Scissors" and computer == "Paper"):
                    return 'user'
                else:
                    return 'computer'
            
            user_score = 0
            computer_score = 0
            while True:
                user = get_user_choice()
                if user == 'quit':
                    break
                computer = get_computer_choice()
                print(f"Computer chose {computer}")
                result = determine_winner(user, computer)
                if result == 'user':
                    print("You win")
                    user_score += 1
                elif result == 'computer':
                    print("Computer wins")
                    computer_score += 1
                else:
                    print("It's a tie")
            
            print(f"user won {user_score} time(s)")
            print(f"computer won {computer_score} time(s)")
            if user_score > computer_score:
                print("The overall winner is user")
            elif computer_score > user_score:
                print("The overall winner is computer")
            else:
                print("No winner")
