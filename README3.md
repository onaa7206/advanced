🔹 1) Initialize Git repository
mkdir ds-project
cd ds-project

Open Git Bash:

git config --global user.name "Aarya7206g"
git config --global user.email "aarya.gaikwad.aids.2023@vpkbiet.org"

git init
🔹 2) Create GitHub repo & connect
Create repo: ds-project on GitHub
Copy link
git remote add origin https://github.com/Aarya7206g/ds-project.git
🔹 3) Create branch GIT-EXAM-1
git checkout -b GIT-EXAM-1
🔹 4) Create program2.py (Palindrome check)
touch program2.py
code program2.py

Write code:

text = input("Enter a string: ")

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not a palindrome")
🔹 5) Create program1.py (Squares 1–10)
touch program1.py
code program1.py

Write code:

for i in range(1, 11):
    print(i, "square is", i * i)
🔹 6) Commit & push to GitHub
git add .
git commit -m "Added palindrome and squares program"
git branch -M main
git push -u origin main

👉 Check GitHub → both files visible

🔹 7) Create new branch GIT-EXAM-2
git checkout -b GIT-EXAM-2
🔹 8) Pull changes from GIT-EXAM-1
git pull origin GIT-EXAM-1
🔹 9) Create program2.py again (Palindrome)
touch program2.py
code program2.py

Write (same or slightly modified):

text = input("Enter string: ")

rev = "".join(reversed(text))

if text == rev:
    print("Palindrome")
else:
    print("Not palindrome")
🔹 10) Modify program1.py (to create conflict)

Open file:

code program1.py

Modify code like this:

for i in range(1, 11):
    print("Square of", i, "is", i ** 2)
🔹 11) Commit & push changes
git add .
git commit -m "Modified program1 and updated palindrome"
git push origin GIT-EXAM-2
🔹 12) Demonstrate conflict (important step)

Now try merging:

git checkout GIT-EXAM-1
git merge GIT-EXAM-2
git diff GIT-EXAM-1 GIT-EXAM-2
