import random 
import time
from IPython.display import display , clear_output
import ipywidgets as widgets 



score = 0
dice1= 0
dice2= 0
money = 0
bet = 0
message_label = widgets.Label(value="Enter your money and place your bet.")
input_text = widgets.Text(description="Enter your Money:")
submit_button = widgets.Button(description="Submit Money")
input_text2 = widgets.Text(description="Your Bet:")
submit_button2 = widgets.Button(description="Place Bet")
up_button = widgets.Button(description="Above 7")
down_button = widgets.Button(description="Below 7")
seven_button = widgets.Button(description="seven")


def on_submit_money(button):
    global money
    try:
        money = int(input_text.value)
        message_label.value = f"Money set to ${money}."
        input_text.value = ""
    except ValueError:
        message_label.value = "Invalid money amount. Please enter a valid integer."

def on_place_bet(button):
    global bet
    try:
        bet = int(input_text2.value)
        if bet > money:
            message_label.value = "Bet cannot be greater than available money."
        else:
            message_label.value = f"Bet placed: ${bet}."
        input_text2.value = ""
    except ValueError:
        message_label.value = "Invalid bet amount. Please enter a valid integer."

def roll_dice():
  global dice1,dice2
  dice1= random.randint(1,6)
  dice2= random.randint(1,6)





def onclick(button):
  global score, input_text2,money,bet
  roll_dice()
  total= dice1 + dice2
  if (button.description== "above 7" and  total > 7) or (button.description == "below 7" and total <7) or (button.description== "seven" and total== 7):
    score = score + 1
    money+=bet
    message_label.value = f"Correct! Total: {total}. Score: {score}. Remaining money: {money}"
  else:
    score = score -1 
    money-=bet
    message_label.value = f"Incorrect! Total: {total}. Score: {score}. Remaining money: {money}"
    # Clear output before displaying new content
  if   money <= 0:
        message_label.value = "Game Over! You've run out of money."
        up_button.disabled = True
        down_button.disabled = True
        seven_button.disabled = True
        submit_button.disabled = True
        input_text.disabled = True
        submit_button2.disabled = True
        input_text2.disabled = True  
  



#clicking of button and connection to function
submit_button.on_click(on_submit_money)
submit_button2.on_click(on_place_bet)
up_button.on_click(onclick)
down_button.on_click(onclick)
seven_button.on_click(onclick)

display(input_text,submit_button,input_text2, submit_button2,message_label, up_button, down_button, seven_button)
