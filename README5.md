✅ Perform the following tasks using GitHub Desktop
🔹 1) Initialize Git repository
Open GitHub Desktop
Click “File → New Repository”
Fill details:
Name: ds-project
Local Path: choose folder
Click Create Repository

✔️ Repository initialized

🔹 2) Publish (Push) to GitHub
Click “Publish repository” (top right)
Keep name: ds-project
Click Publish Repository

✔️ Now repo is available on GitHub

🔹 3) Create new branch GIT-EXAM-1
Click “Current Branch”
Click “New Branch”
Enter name: GIT-EXAM-1
Click Create Branch

✔️ Switched to new branch

🔹 4) Create program2.py (Palindrome)
Click “Show in Explorer”
Create file: program2.py

Write code:

text = input("Enter a string: ")

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not a palindrome")

Save file

🔹 5) Create program1.py (Squares 1–10)

Create file: program1.py

for i in range(1, 11):
    print(i, "square is", i * i)

Save file

🔹 6) Commit & Push changes

Back to GitHub Desktop:

You’ll see changed files listed

Write commit message:

Added palindrome and squares program
Click Commit to GIT-EXAM-1
Click Push origin

✔️ Files uploaded → check on GitHub

🔹 7) Create IGNORE directory & files
Click “Show in Explorer”
Create folder: IGNORE
Inside it create:
test1.txt
test2.txt
🔹 8) Create .gitignore file
In main folder create file: .gitignore
Open it and write:
IGNORE/

Save file

🔹 9) Verify ignore (important)

Go back to GitHub Desktop:

👉 You will see:

.gitignore file
❌ IGNORE folder NOT shown (ignored)
🔹 10) Commit & Push .gitignore

Add commit message:

Added gitignore to ignore IGNORE folder
Click Commit to GIT-EXAM-1
Click Push origin
🔹 11) Verify on GitHub

Open your repo on GitHub

👉 You will see:

✅ program1.py
✅ program2.py
✅ .gitignore
❌ IGNORE folder NOT present
⚠️ Important (Exam/Viva point)

👉 .gitignore tells Git:

“Do NOT track this folder/file”

👉 If already tracked earlier → remove using Git Bash:

git rm -r --cached IGNORE
✅ Final Output
Repository created ✔️
Code pushed ✔️
Branch used ✔️
IGNORE folder successfully hidden ✔️

