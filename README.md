# Fibonacci
def fibonacci_with_steps(n):
    if n <= 0:
        return None
    sequence = []
    steps = []
    a, b = 0, 1
    for i in range(n):
        sequence.append(a)
        if i == 0:
            steps.append("0")
        elif i == 1:
            steps.append("1")
        else:
            steps.append(f"{a} = {sequence[i-2]} + {sequence[i-1]}")
        a, b = b, a + b
    return sequence, steps
while True:
    print("\nFibonacci Calculator")
    user_input = input("Enter how many terms (or type 'exit' to quit): ")
    if user_input.lower() == 'exit':
        print("Goodbye!")
        break
    if not user_input.isdigit():
        print("Invalid input. Please enter a positive integer.")
        continue
    num = int(user_input)
    result = fibonacci_with_steps(num)
    if result is None:
        print("Please enter a number greater than 0.")
    else:
        sequence, steps = result
        print("\nFibonacci Sequence:")
        print(sequence)
        print("\nWorking (Steps):")
        for step in steps:
            print(step)
