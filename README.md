Overview
This dice game allows users to set an initial amount of money, place bets, and guess the outcome of dice rolls. The game provides feedback on the correctness of the guesses, updates the user's score, and adjusts the money based on the bets placed.

Components
1. Initialization
Variables:
score: Tracks the player's score.
dice1, dice2: Store the values of the rolled dice.
money: Represents the player's current balance.
bet: Represents the amount of money the player bets on each roll.
2. Widgets
message_label: Displays messages, such as instructions, results, and remaining money.
input_text: A text input widget where the user can enter the initial amount of money.
submit_button: A button that submits the initial amount of money.
input_text2: A text input widget where the user can enter their bet amount.
submit_button2: A button that submits the bet amount.
up_button: A button to guess that the total of the dice will be above 7.
down_button: A button to guess that the total of the dice will be below 7.
seven_button: A button to guess that the total of the dice will be exactly 7.
3. Functions
roll_dice()
Purpose: Simulates rolling two dice by generating two random integers between 1 and 6 (inclusive).
Global Variables Used: dice1, dice2
on_submit_money(button)
Purpose: Handles setting the initial amount of money.
Parameters: button (The button that triggered the function, submit_button)
Functionality:
Converts the input from input_text to an integer.
Updates the money variable with the entered amount.
Displays a confirmation message or an error message if the input is invalid.
on_place_bet(button)
Purpose: Handles placing the bet amount.
Parameters: button (The button that triggered the function, submit_button2)
Functionality:
Converts the input from input_text2 to an integer.
Checks if the bet is greater than the available money and updates the bet variable.
Displays a confirmation message or an error message if the input is invalid.
onclick(button)
Purpose: Handles the dice roll and evaluates the player's guess.
Parameters: button (The button that triggered the function: up_button, down_button, or seven_button)
Functionality:
Calls roll_dice() to roll the dice.
Checks if the total of the dice matches the player's guess.
Updates the score and money based on whether the guess was correct.
Displays the result of the roll and updates the message_label.
Disables game controls if the player runs out of money.
4. Event Handlers
submit_button.on_click(on_submit_money): Binds the on_submit_money function to the submit_button.
submit_button2.on_click(on_place_bet): Binds the on_place_bet function to the submit_button2.
up_button.on_click(onclick): Binds the onclick function to the up_button.
down_button.on_click(onclick): Binds the onclick function to the down_button.
seven_button.on_click(onclick): Binds the onclick function to the seven_button.
5. Display
Widgets Displayed:
message_label
input_text
submit_button
input_text2
submit_button2
up_button
down_button
seven_button
Usage
Set Initial Money:

Enter the amount of money you want to start with in the input_text widget.
Click the Submit Money button to set your initial balance.
Place a Bet:

Enter your desired bet amount in the input_text2 widget.
Click the Place Bet button to set your bet.
Make a Guess:

Click one of the following buttons to make a guess:
Above 7 to guess the total will be greater than 7.
Below 7 to guess the total will be less than 7.
Exactly 7 to guess the total will be exactly 7.
Review Results:

The message_label will display the result of the dice roll, whether your guess was correct, your score, and the remaining money.
Game Over:

The game will automatically end if you run out of money. All game controls will be disabled, and a "Game Over" message will be displayed.
Notes
Ensure that the bet amount does not exceed the current money available.
The game continues as long as there is money available. Once the money reaches zero, the game ends and all buttons are disabled.
