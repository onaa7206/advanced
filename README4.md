✅ Perform the following tasks using git-bash
🔹 1) Initialize Git repository
mkdir ds-project
cd ds-project

Open Git Bash:

git config --global user.name "Aarya7206g"
git config --global user.email "aarya.gaikwad.aids.2023@vpkbiet.org"

git init
🔹 2) Create GitHub repo & connect
Create repo: ds-project on GitHub
Copy repo link
git remote add origin https://github.com/Aarya7206g/ds-project.git
🔹 3) Create branch GIT-EXAM-1
git checkout -b GIT-EXAM-1
🔹 4) Create program2.py (Palindrome)
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
🔹 6) Commit & push
git add .
git commit -m "Added palindrome and squares program"
git branch -M main
git push -u origin main

👉 Check GitHub → files visible ✔️

🔹 7) Create IGNORE directory and files
mkdir IGNORE
cd IGNORE
touch test1.txt test2.txt
cd ..
🔹 8) Create .gitignore file
touch .gitignore
code .gitignore

Add this line:

IGNORE/

Save file

🔹 9) Check status (important step)
git status

👉 You will see:

.gitignore file
❌ IGNORE/ folder will NOT appear (ignored)
🔹 10) Commit & push
git add .gitignore
git commit -m "Added gitignore to ignore IGNORE folder"
git push
🔹 11) Verify on GitHub

👉 Open your GitHub repo
You will see:

✅ program1.py
✅ program2.py
✅ .gitignore
❌ IGNORE folder NOT present
