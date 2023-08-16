import random

def play_guessing_game():
    lower_range = 1
    upper_range = 100
    max_attempts = 10
    current_round = 1
    score = 0

    while True:
        target_number = random.randint(lower_range, upper_range)
        print(f"Round {current_round}")
        print(f"Guess a number between {lower_range} and {upper_range}.")

        for attempt in range(max_attempts):
            user_guess = int(input(f"Attempt {attempt + 1}/{max_attempts}: Enter your guess: "))

            if user_guess == target_number:
                print(f"Congratulations! You guessed the number {target_number} in {attempt + 1} attempts.")
                score += max_attempts - attempt
                break
            elif user_guess < target_number:
                print("Too low. Try again.")
            else:
                print("Too high. Try again.")

        play_again = input("Do you want to play again? (yes/no): ")
        if play_again.lower() != "yes":
            break

        current_round += 1

    print(f"Your total score: {score}")

if __name__ == "__main__":
    play_guessing_game()
