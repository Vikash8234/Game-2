import random

def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"])

def get_user_choice():
    while True:
        user_input = input("Enter rock, paper, or scissors: ").lower()
        if user_input in ["rock", "paper", "scissors"]:
            return user_input
        print("Invalid choice. Try again.")

def determine_winner(user, computer):
    if user == computer:
        return "It's a tie!"
    elif (user == "rock" and computer == "scissors") or \
         (user == "paper" and computer == "rock") or \
         (user == "scissors" and computer == "paper"):
        return "You win!"
    else:
        return "Computer wins!"

def play_game():
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    print(f"User chose: {user_choice}")
    print(f"Computer chose: {computer_choice}")
    print(determine_winner(user_choice, computer_choice))

if __name__ == "__main__":
    play_game()
