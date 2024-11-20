import random

def ask_math_question():
    # Randomly choose an arithmetic operation (addition, subtraction, multiplication)
    operations = ['+', '-', '*']
    operation = random.choice(operations)
    
    # Generate two random numbers for the math question
    num1 = random.randint(1, 10)
    num2 = random.randint(1, 10)
    
    # Create a math question based on the chosen operation
    question = f"What is {num1} {operation} {num2}?"
    
    # Calculate the correct answer
    if operation == '+':
        correct_answer = num1 + num2
    elif operation == '-':
        correct_answer = num1 - num2
    else:  # multiplication
        correct_answer = num1 * num2
    
    return question, correct_answer

def guessing_game():
    print("Welcome to the Number Guessing Game with a Math Theme!")
    
    # Ask the user a math question
    question, correct_answer = ask_math_question()
    
    print(question)
    
    # Allow the user to guess
    attempts = 0
    while True:
        try:
            user_guess = int(input("Your guess: "))
            attempts += 1
            
            if user_guess == correct_answer:
                print(f"Correct! You guessed the right answer in {attempts} attempts.")
                break
            elif user_guess < correct_answer:
                print("Too low, try again!")
            else:
                print("Too high, try again!")
        except ValueError:
            print("Please enter a valid number.")

# Start the game
guessing_game()
