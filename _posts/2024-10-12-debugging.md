# Daring Debugging: Tackling Python Code Errors One Bug at a Time

Let’s face it—debugging code is rarely a walk in the park. If you’ve just started with Python, you probably know how frustrating it can be to figure out why something doesn’t work. But when the light bulb finally flicks on and you realize what’s broken, it’s one of those sweet moments that makes the struggle worth it.

For this project, I had to debug several Python snippets, find the issues, and fix them. Some were sneaky little bugs, but I managed to track them down and squash them. Let’s dive into the details!

---

## 1. **Temperature Check Gone Wrong**

The task was to classify temperatures as "hot," "temperate," or "cold." Simple, right? Well, not when the code ignores an entire range of temperatures.

### **Original Code**:
```python
temperature = 75

if temperature > 80:
    print("It's hot")
elif temperature > 50:
    print("It's temperate")
elif temperature < 0:
    print("It's cold")
The Issue:
This code completely ignores temperatures between 0 and 50. What are those, then? A glitch in the matrix?

The Fix:
I swapped out the last elif for an else, so that any temperature below 50 would be classified as cold. Here’s the fixed version:

python
Copy code
if temperature > 80:
    print("It's hot")
elif temperature > 50:
    print("It's temperate")
else:
    print("It's cold")
2. Space Counting: Close, But No Cigar
Next up, the goal was to count how many spaces are in a given string. The original code had the right idea, but instead of checking for spaces, it was checking for empty strings, which is not the same thing.

Original Code:
python
Copy code
text = "Hello, world, my name is"
count = 0

for char in text:
    if char == "":
       count += 1
   
print(count)
The Issue:
The condition was looking for "" instead of " ", which means it wasn't counting spaces.

The Fix:
Changing "" to " " fixed the issue, so now the program counts spaces correctly.

python
Copy code
for char in text:
    if char == " ":
       count += 1
3. Even or Odd Checker (Almost)
The code was supposed to check if numbers between 1 and a user-defined input were even or odd. Sounds easy, but there were a few hiccups.

Original Code:
python
Copy code
print("give me a number")
n = input()

for num in range(1, n):
    if num % 2 < 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
The Issue:
n was treated as a string, so Python couldn’t use it as a number.
The condition for checking even numbers (num % 2 < 0) was completely wrong.
The Fix:
I added int() around n to convert the input into an integer. I also corrected the condition to check for even numbers properly using num % 2 == 0.

python
Copy code
n = int(input())

for num in range(1, n+1):  # Added +1 to include 'n' itself
    if num % 2 == 0:
        print(num, "is even.")
    else:
        print(num, "is odd.")
4. Factorial Mishap
This code was meant to calculate the factorial of a number, but instead of working, it kept crashing because it tried to combine strings and integers in one of the print statements.

Original Code:
python
Copy code
num = int(input("Enter an integer: "))

if num < -1:
  print("No negative numbers.")
else:
  result = 1
  for i in range(1, num):
    result *= i   

  print("Factorial of " + num + "is" + result)
The Issue:
The code tried to add a string ("Factorial of ") to a number (num), which Python doesn’t like. It also incorrectly calculated the factorial starting from 1.

The Fix:
I replaced the + in the print statement with a comma and adjusted the factorial calculation to work properly:

python
Copy code
if num < -1:
    print("No negative numbers.")
else:
    result = num
    for i in range(1, num):
        result *= i   

    print("Factorial of", num, "is", result)
5. Password Problems
This one was supposed to be a password guessing game that gave the user only three tries. But the original code had two main issues: it was checking for the wrong variable and it allowed more than three attempts.

Original Code:
python
Copy code
attempts = 0
correct_password = "secret"

while True:
    password = input("Enter your password: ")
    attempts += 1
    if password == "incorrect_password":
        print("Correct password!")
    else:
        print("Incorrect password")

    if attempts > 3:
        print("Too many attempts")
        break
The Issue:
The code was comparing password to "incorrect_password", a hardcoded string instead of the correct_password variable.
The condition for stopping attempts allowed more than three tries.
The Fix:
I changed "incorrect_password" to correct_password and made sure the attempts were limited to exactly three.

python
Copy code
while True:
    password = input("Enter your password: ")
    attempts += 1
    if password == correct_password:
        print("Correct password!")
        break
    else:
        print("Incorrect password")

    if attempts >= 3:
        print("Too many attempts")
        break
Final Thoughts
Debugging is like a puzzle — a frustrating one where the pieces don’t always fit the way you expect. But once you manage to work through the issues, it can be super satisfying. This project taught me that it’s all about paying attention to the details (and having the patience to run your code for the tenth time).

You can check out my commit here for the full code!
