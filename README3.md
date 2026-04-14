1) Create folder & initialize Git repository

Create folder:

mkdir ds-project
cd ds-project

Open Git Bash inside folder and type:

git config --global user.name "Aarya7206g"
git config --global user.email "aarya.gaikwad.aids.2023@vpkbiet.org"

git init
2) Create repository on GitHub & connect
Go to GitHub → create repo: ds-project
Copy repo link

In Git Bash:

git remote add origin https://github.com/Aarya7206g/ds-project.git
3) Create program1.py (Even/Odd program)
touch program1.py
code program1.py

Write code:

num = int(input("Enter a number: "))

if num % 2 == 0:
    print("Even number")
else:
    print("Odd number")

Save file

4) Add, commit & push code
git add program1.py
git commit -m "Added even odd program"
git branch -M main
git push -u origin main

👉 Now check your GitHub repo → file will be visible

5) Create new branch GIT-EXAM
git checkout -b GIT-EXAM
6) Create program2.py (Reverse string)
touch program2.py
code program2.py

Write code:

text = input("Enter a string: ")

reverse = text[::-1]

print("Reversed string is:", reverse)

Save file

7) Add, commit & push to GIT-EXAM branch
git add program2.py
git commit -m "Added reverse string program"
git push origin GIT-EXAM
8) Check difference between branches

Switch branches:

git checkout main

👉 You will see:

Only program1.py

Now switch back:

git checkout GIT-EXAM

👉 You will see:

program1.py + program2.py

You can also use:

git diff main GIT-EXAM
9) Create Pull Request (Merge GIT-EXAM → main)

On GitHub:

Go to your repo
Click Compare & Pull Request
Select:
Base: main
Compare: GIT-EXAM
Click Create Pull Request
Click Merge Pull Request
