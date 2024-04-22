import random
import math

lower_bound = int(input("Enter Lower bound:- "))
upper_bound = int(input("Enter Upper bound:- "))
random_number = random.randint(lower_bound, upper_bound)
print("\nYou have only", round(math.log(upper_bound - lower_bound + 1, 2)), "chances to guess the integer!\n")

count = 0
while count < math.log(upper_bound - lower_bound + 1, 2):
    count += 1
    guess = int(input("Guess a number:- "))
    if random_number == guess:
        print("Congratulations! You guessed it in", count, "attempt(s).")
        break
    elif random_number > guess:
        print("You guessed too small!")
    elif random_number < guess:
        print("You guessed too high!")

if count >= math.log(upper_bound - lower_bound + 1, 2):
    print("\nThe number was", random_number)
    print("\tBetter Luck Next time!")
