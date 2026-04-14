FULL DETAILED STEPS (Git Bash + GitHub)
🔹 a) Clone repository (original repo)
👉 Step 1:

Open Git Bash

👉 Step 2:

Type:

git clone https://github.com/KalyanM45/AI-Project-Gallery.git
👉 Step 3:

Go inside folder:

cd AI-Project-Gallery

✔️ Now project is downloaded to your computer

🔹 b) Show branch creation is NOT allowed
👉 Step 1: Try to create branch
git checkout -b GIT-TEST

✔️ This works locally

👉 Step 2: Try to push
git push origin GIT-TEST

❌ You will get error like:

remote: Permission denied
fatal: unable to access
👉 Meaning:

👉 You cannot push changes
👉 So effectively you cannot create branch in original repo

✔️ This is what examiner wants

🔹 c) Fork the repository
👉 Step 1:

Open repo in browser on GitHub

👉 Step 2:

Click Fork (top-right)

👉 Step 3:

Select your account

✔️ Now repo is copied to your account

🔹 d) Clone YOUR fork (important step)
👉 Copy your fork link:
https://github.com/YOUR-USERNAME/AI-Project-Gallery.git
👉 In Git Bash:
git clone https://github.com/YOUR-USERNAME/AI-Project-Gallery.git
cd AI-Project-Gallery

✔️ Now you have your editable version

🔹 e) Create feature branch (GIT-EXAM)
git checkout -b GIT-EXAM

✔️ Now you are working in new branch

🔹 f) Add / Modify code
👉 Example:
touch test.py

Open file and write:

print("Feature added in GIT-EXAM branch")

✔️ Save file

🔹 g) Commit changes
git add .
git commit -m "Added new feature file"

✔️ Changes saved locally

🔹 h) Push branch to GitHub
git push origin GIT-EXAM

✔️ Branch uploaded to your GitHub

🔹 i) Create Pull Request (VERY IMPORTANT)
👉 Step 1:

Go to your fork on GitHub

👉 Step 2:

You’ll see button:
👉 Compare & Pull Request

👉 Step 3:

Click it

👉 Step 4: Fill details
Base repository → original repo
Base branch → main
Compare branch → GIT-EXAM
👉 Step 5:

Click:
👉 Create Pull Request

✔️ Your request is sent

🔹 j) Resolve merge conflicts (if any)
👉 Step 1: Pull latest changes
git pull origin main
👉 Step 2: Open conflicted file

You will see:

<<<<<<< HEAD
your code
=======
other code
>>>>>>> main
👉 Step 3: Fix manually

Keep correct code, remove symbols

👉 Step 4: Commit fix
git add .
git commit -m "Resolved conflict"
git push origin GIT-EXAM

✔️ PR gets updated automatically

🔹 k) After review
Reviewer checks your PR
May give suggestions
You update code if needed
Finally click:
👉 Merge Pull Request
✅ FINAL UNDERSTANDING (VERY IMPORTANT)

👉 You CANNOT directly push to original repo
👉 So workflow is:

Original Repo → Fork → Clone → Branch → Changes → Push → Pull Request → Merge
