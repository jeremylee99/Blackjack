import random
logo = """
.------.            _     _            _    _            _    
|A_  _ |.          | |   | |          | |  (_)          | |   
|( \/ ).-----.     | |__ | | __ _  ___| | ___  __ _  ___| | __
| \  /|K /\  |     | '_ \| |/ _` |/ __| |/ / |/ _` |/ __| |/ /
|  \/ | /  \ |     | |_) | | (_| | (__|   <| | (_| | (__|   < 
`-----| \  / |     |_.__/|_|\__,_|\___|_|\_\ |\__,_|\___|_|\_\\
      |  \/ K|                            _/ |                
      `------'                           |__/           
"""
cards = [11 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 , 10 , 10 , 10]
def deal_hand():
  return random.choice(cards)

play = input("Welcome to the blackjack table, do you want to play a game? 'y' or 'n'\n").lower()
should_cont = 'y'
while should_cont == 'y':
  user_hand = []
  comp_hand = []
  if play == "y":
    print(logo)
    user_hand.append(deal_hand())
    user_hand.append(deal_hand())
    comp_hand.append(deal_hand())
    comp_hand.append(deal_hand())
    
    print(f"Your hand is {user_hand}, and have a total score of {sum(user_hand)}.")
    print(f"The computer's first card is {comp_hand[0]}.")
    hit = input("Do you want to add another card to your total? 'y' or 'n'").lower()
    while hit == "y":
      user_hand.append(deal_hand())
      print(user_hand)
      print(f"You have a total of {sum(user_hand)}")
      if sum(user_hand) > 21 and (11 in user_hand):
        position = -1
        for num in user_hand:
          position += 1
          if num == 11:
            user_hand[position] = 1
        print(f"Your hand is {user_hand}")
      elif sum(user_hand) > 21 and (11 not in user_hand):
        break
      else:
        hit = input("Do you want to add another card to your total? 'y' or 'n'").lower()
    while sum(comp_hand) < 16:
      comp_hand.append(deal_hand())
    if sum(user_hand) > 21 and sum(comp_hand) > 21:
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, You both bust! It's a tie!")
    elif sum(user_hand) == sum(comp_hand):
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, Its a tie!")
    elif sum(user_hand) > 21 and sum(comp_hand) <= 21:
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, You Bust! You Lose!")
    elif sum(user_hand) <= 21 and sum(comp_hand) > 21:
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, The computer Busts! YOU WIN!!")
    elif sum(user_hand) > sum(comp_hand):
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, YOU WIN!")
    else:
      print(f"Your total was {sum(user_hand)}, the computer's total was {sum(comp_hand)}, You Lose!")
  should_cont = input("Do you want to play again? 'y or 'n'").lower()
