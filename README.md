### **Job Shadowing Guide for future Software Engineering**  

This guide is designed to help a future Software Engineering understand how software development works in a large enterprise. The steps will introduce you to programming, tools, and workflows used by professional software engineers.

---

## **Step 1: Introduction to Software Development (30 min)**
**Goal:** Understand what software engineers do.  

### **What to Cover:**
- Explain what software is (examples: mobile apps, websites, games, AI).
- Discuss how software engineers work in teams to build and maintain software.
- Explain the Software Development Life Cycle (SDLC):
  - **Planning** – Understanding the problem.
  - **Design** – Thinking about how to solve the problem.
  - **Implementation** – Writing the code.
  - **Testing** – Making sure the code works.
  - **Deployment** – Releasing the software.
  - **Maintenance** – Fixing bugs and improving the software.

---

## **Step 2: Setting Up the Development Environment (45 min)**
**Goal:** Get hands-on experience setting up a software development workspace.  

### **Tools to Install:**
1. **Python (Programming Language)**  
   - Download & Install Python: [https://www.python.org/downloads/](https://www.python.org/downloads/)  
   - Open a terminal (Mac/Linux) or command prompt (Windows) and type:  
     ```
     python --version
     ```
     to check if Python is installed.

2. **Visual Studio Code (Code Editor)**  
   - Download & Install VS Code: [https://code.visualstudio.com/](https://code.visualstudio.com/)  
   - Open VS Code and create a new file: `hello.py`
   - Write this code:
     ```python
     print("Hello, world!")
     ```
   - Run the script by opening a terminal in VS Code and typing:
     ```
     python hello.py
     ```

3. **Git and GitHub (Version Control & Collaboration)**  
   - Create a **GitHub Account**: [https://github.com/](https://github.com/)  
   - Install **Git**: [https://git-scm.com/downloads](https://git-scm.com/downloads)  
   - Open terminal and configure Git:
     ```
     git config --global user.name "Your Name"
     git config --global user.email "your-email@example.com"
     ```

---

## **Step 3: Writing and Running Simple Code (1 Hour)**
**Goal:** Learn the basics of coding by writing simple Python programs.  

### **Beginner Exercises:**
1. **Variables & Printing**
   ```python
   name = input("Enter your name: ")
   print("Hello, " + name + "!")
   ```
   - Run the script and enter their name.

2. **If Statements & Loops**
   ```python
   age = int(input("Enter your age: "))
   if age < 18:
       print("You're a minor!")
   else:
       print("You're an adult!")
   ```

3. **Using Functions**
   ```python
   def greet(name):
       return "Hello, " + name + "!"
   
   print(greet("Alice"))
   ```

---

## **Step 4: Introduction to GitHub & Collaboration (45 min)**
**Goal:** Learn how to use GitHub for version control.  

### **Steps to Follow:**
1. **Create a GitHub Repository**
   - Go to GitHub and click **"New Repository"**.
   - Name it **"learning-python"**, select **public**, and click **"Create"**.

2. **Clone the Repository Locally**
   - Open the terminal and run:
     ```
     git clone https://github.com/YOUR_USERNAME/learning-python.git
     cd learning-python
     ```

3. **Add a Python File to Git**
   - Inside the repo folder, create a new file `program.py`.
   - Write a Python script:
     ```python
     print("This is my first GitHub project!")
     ```
   - Add and commit:
     ```
     git add program.py
     git commit -m "Added first Python file"
     git push origin main
     ```

4. **View the File on GitHub**
   - Open GitHub and refresh the repository page to see `program.py`.

---

## **Step 5: Exploring Enterprise Software Engineering (1 Hour)**
**Goal:** Understand how engineers work in a real-world software company.  

### **Key Concepts to Introduce:**
- **Code Reviews**: Engineers review each other’s code before merging changes.
- **Issue Tracking**: Teams use GitHub Issues, Jira, or Trello to manage tasks.
- **Continuous Integration (CI/CD)**: Automation tools test and deploy software automatically.

### **Hands-on Activity:**
- Create a **new branch**:
  ```
  git checkout -b new-feature
  ```
- Modify `program.py` to print an additional message:
  ```python
  print("Hello from a new feature!")
  ```
- Add, commit, and push:
  ```
  git add program.py
  git commit -m "Added a new feature"
  git push origin new-feature
  ```
- Open GitHub and create a **Pull Request** (PR).

---

## **Step 6: Testing & Debugging (45 min)**
**Goal:** Learn how to debug and test code.  

### **Debugging a Python Script:**
- Introduce `print()` debugging:
  ```python
  def divide(a, b):
      print("Dividing", a, "by", b)
      return a / b

  print(divide(10, 0))
  ```
  - Run the script to see the **ZeroDivisionError**.
  - Fix it using an **if statement**:
    ```python
    def divide(a, b):
        if b == 0:
            return "Cannot divide by zero!"
        return a / b

    print(divide(10, 0))
    ```

### **Writing a Simple Test**
- Create `test_program.py`:
  ```python
  import unittest
  from program import divide

  class TestMathFunctions(unittest.TestCase):
      def test_divide(self):
          self.assertEqual(divide(10, 2), 5)
          self.assertEqual(divide(10, 0), "Cannot divide by zero!")

  if __name__ == "__main__":
      unittest.main()
  ```
- Run the test:
  ```
  python -m unittest test_program.py
  ```

---

## **Step 7: Building a Simple Web App (Optional, 1.5 Hours)**
**Goal:** Introduce web development with Flask.  

### **Install Flask:**
```
pip install flask
```

### **Create `app.py`:**
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(debug=True)
```

### **Run the App:**
```
python app.py
```
- Open a browser and go to `http://127.0.0.1:5000/`.

---

## **Step 8: Q&A and Career Path Discussion (30 min)**
**Goal:** Discuss what it's like being a software engineer.  

### **Topics to Cover:**
- Career paths in software engineering.
- The importance of problem-solving skills.
- Encouragement to explore coding beyond this session (YouTube, freeCodeCamp, CS50).

---

## **Keep Learning**

- **Practicing on LeetCode or CodeWars**  
  - [LeetCode](https://leetcode.com/) – A platform for coding challenges and algorithm practice.  
  - [CodeWars](https://www.codewars.com/) – A gamified coding challenge platform with different difficulty levels.

- **Exploring [CS50 (Harvard’s free coding course)](https://pll.harvard.edu/course/cs50-introduction-computer-science)** – A highly recommended introductory course on computer science.

- **Watching YouTube tutorials on Python & web development**  
  - [freeCodeCamp - Python for Beginners](https://www.youtube.com/watch?v=rfscVS0vtbw)  
  - [Traversy Media - Python Crash Course](https://www.youtube.com/watch?v=JJmcL1N2KQs)  
  - [The Net Ninja - Python Django for Web Development](https://www.youtube.com/playlist?list=PL4cUxeGkcC9hIUIeqcIgHq2bI9qaZ4l8I)  

These resources will help them continue learning beyond the job shadowing experience. 🚀
