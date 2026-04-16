FIBONACCI
WORK FLOW
1.	Start
2.	Input number of terms n
3.	If n == 0
Display error message → End 
4.	Initialize first two terms
a = 0, b = 1
5.	Create an empty list to store sequence
6.	Repeat loop from 1 to n
Add a to the sequence
Compute next term: next = a + b
Update values:
•	a = b
•	b = next
7.	Display the full Fibonacci sequence
8.	End


PSEUDO CODE
BEGIN
    INPUT n

    IF n <= 0 THEN
        PRINT "Please enter a number greater than 0"
    ELSE
        SET a = 0
        SET b = 1
        CREATE empty list sequence

        FOR i = 1 TO n DO
            ADD a TO sequence

            SET next = a + b
            SET a = b
            SET b = next
        END FOR

        PRINT "Fibonacci Sequence:", sequence
    END IF
END



PYTHON CODE
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
