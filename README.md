# Prefix Expression Evaluation using Stack

## 📌 Aim
To write a Python program that evaluates a given **prefix expression** using a stack. The program will handle valid prefix expressions consisting of single-digit numbers and binary operators (`+`, `-`, `*`).

---

## 🛠 Procedure
1. Define the set of valid operators: `+`, `-`, `*`.
2. Initialize an empty stack to store operands.
3. Traverse the expression from right to left (reverse order).
4. If the token is a number, push it onto the stack.
5. If the token is an operator, pop two numbers from the stack, apply the operator, and push the result back onto the stack.
6. After processing all tokens, the final result will be the only element remaining in the stack.

---

## 💻 Program

```python
OPERATORS = set(['+', '-', '*'])

def evaluate_prefix(expression):
    stack = []
    
    for token in reversed(expression):
        if token.isdigit():  
            stack.append(int(token))
        elif token in OPERATORS:
            a = stack.pop()
            b = stack.pop()
            if token == '+':
                stack.append(a + b)
            elif token == '-':
                stack.append(a - b)
            elif token == '*':
                stack.append(a * b)
    
    return stack[0]  

expression = input("")
print("Prefix Expression :", expression)
print("Evaluation result :", evaluate_prefix(expression))

```
## Output

![image](https://github.com/user-attachments/assets/4e6000c6-f576-4153-ae92-30cd49aaf6f5)

## Result

Thus, the program was successfully created and executed to evaluate a prefix expression.
