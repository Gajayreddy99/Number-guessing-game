import random
import math

lower_bound = int(input("Enter Lower bound: "))
upper_bound = int(input("Enter Upper bound: "))

random_number = random.randint(lower_bound, upper_bound)

max_attempts = round(math.log2(upper_bound - lower_bound + 1))
print("\nYou have only", max_attempts, "chances to guess the integer!\n")

attempts = 0

while attempts < max_attempts:
    attempts += 1
    guess = int(input("Guess a number: "))
    
    if guess == random_number:
        print("Congratulations! You guessed it in", attempts, "attempt(s).")
        break
    elif guess < random_number:
        print("You guessed too low!")
    else:
        print("You guessed too high!")

if attempts >= max_attempts:
    print("\nThe number was", random_number)
    print("\tBetter Luck Next time!")
