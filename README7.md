✅ Perform tasks using GitHub Desktop
🔹 a) Clone repository

Using GitHub Desktop

👉 Steps:
Open GitHub Desktop

Click:

File → Clone Repository
Go to URL tab

Paste:

https://github.com/KalyanM45/Spam-Email-Detection.git
Choose local path
Click Clone

✔️ Project downloaded to your system

🔹 b) Show branch creation is disallowed
👉 Step 1: Try to create branch
Click Current Branch
Click New Branch
Name: GIT-TEST
Click Create Branch

✔️ Branch created locally

👉 Step 2: Try to publish

Click:
👉 Publish branch / Push origin

❌ You will get error like:

“Permission denied”
“Cannot push to this repository”

✔️ This proves:
👉 You don’t have permission on original repo

🔹 c) Fork the repository
Open repo in browser on GitHub
Click Fork (top-right)
Select your account

✔️ Now you have your own copy

🔹 d) Clone YOUR fork (important)

Copy your fork link:

https://github.com/YOUR-USERNAME/Spam-Email-Detection.git

In GitHub Desktop:

File → Clone Repository → URL
Paste your fork link → Click Clone

✔️ Now this repo is fully editable

🔹 e) Create feature branch (GIT-EXAM)
Click Current Branch
Click New Branch
Name: GIT-EXAM
Click Create Branch

✔️ You are now working on feature branch

🔹 f) Add / Modify code

Click:

Repository → Show in Explorer

Create file:

test.py
Write code:
print("Spam Detection Feature Updated")

Save file

🔹 g) Commit changes

Back to GitHub Desktop:

You will see file in changes list

Write commit message:

Added new feature file
Click:
👉 Commit to GIT-EXAM
🔹 h) Push branch

Click:
👉 Push origin

✔️ Branch uploaded to GitHub

🔹 i) Create Pull Request
Click:
👉 Branch → Create Pull Request
Browser will open (GitHub)
Click:
👉 Create Pull Request

✔️ PR submitted

🔹 j) Resolve merge conflicts (if any)
👉 If GitHub shows conflict:
Click Resolve conflicts
You will see:
<<<<<<< HEAD
your code
=======
other code
>>>>>>> main
Edit → keep correct code
Click Mark as resolved
Commit changes
👉 OR using GitHub Desktop:

Pull latest changes:

Repository → Pull
Fix file manually

Commit:

Resolved conflict
Push again
🔹 k) Incorporate feedback

👉 Reviewer may comment:

Change code
Improve logic
Do this:
Edit file
Commit again
Push

✔️ PR auto-updates

🔹 l) Final merge
Open PR on GitHub
Click:
👉 Merge Pull Request

✔️ Changes merged successfully

✅ FINAL FLOW (VERY IMPORTANT)
Clone → (Fail to push) → Fork → Clone fork → Branch → Changes → Commit → Push → Pull Request → Merge
💡 Exam key explanation

👉 “Since we don’t have write access to original repository, we fork it, create a feature branch, make changes, and submit a pull request for merging.”
