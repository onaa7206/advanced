vsec8(jenkins)


🟢 STEP 0: Install Required Software
✅ 0.1 Install Java

👉 Download and install Java (JDK 17)

WHERE TO RUN COMMAND:

Open Command Prompt

java -version

✅ You should see version
❌ Error:

'java' is not recognized

👉 Fix:

Restart PC
OR reinstall Java with PATH enabled
✅ 0.2 Install Git

Install Git

IMPORTANT during install:

✔ Tick:

Add Git to PATH
CHECK (Command Prompt):
git --version
✅ 0.3 Install Jenkins

Install Jenkins

After install:

👉 Open browser:

http://localhost:8080
🔓 STEP 1: Unlock Jenkins

Screen shows:

Unlock Jenkins
DO THIS:
Open File Explorer
Go to:
C:\Program Files\Jenkins\secrets\
Open:
initialAdminPassword
Copy text
Paste in browser

Click:
👉 Continue

Install Plugins

Click:
👉 Install Suggested Plugins

WAIT until complete

Create Admin User
Username: admin
Password: (remember it)

Click:
👉 Save and Continue
##############################################################################################################################################################################
🌐 STEP 2: Create GitHub Repository

Go to:
👉 GitHub

Steps:
Click + (top right)
Click New repository

Fill:

Name → jenkins-demo
Select → Public
Tick → Add README

Click:
👉 Create repository

📄 STEP 3: Add Jenkinsfile (MOST IMPORTANT)

Inside your repo:

Click Add file → Create new file
File name 
Jenkinsfile:
(EXACT code ):Paste this in file:
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}

Click:
👉 Commit new file

❌ ERRORS HERE (VERY COMMON)
❌ Wrong name → jenkinsfile.txt
❌ File inside folder

👉 MUST be:

repo root → Jenkinsfile
🏗 STEP 4: Create Pipeline Job in Jenkins

Go to Jenkins dashboard

Click:
👉 New Item

Enter:

my-pipeline

Select:
👉 Pipeline

Click:
👉 OK

🔗 STEP 5: Connect GitHub to Jenkins

Scroll to Pipeline section

Change:

Definition → Pipeline script from SCM
Fill Details:
SCM:
Git
Repository URL:

Paste:

https://github.com/your-username/jenkins-demo.git
If repo is PRIVATE:

Click:
👉 Add credentials

Use:

Username
GitHub Token (NOT password)
Branch:
*/main

❌ If repo uses master, change to:

*/master

Click:
👉 Save

▶️ STEP 6: Run First Build

Click:
👉 Build Now

Then:

Click build number
Click Console Output
EXPECT OUTPUT:
Building...
Testing...
Deploying...
❌ ERRORS
Jenkinsfile not found

👉 File missing or wrong location

Git error

👉 Wrong repo URL OR no Git installed

🔁 STEP 7: Enable Auto Build

Click:
👉 Configure

Scroll to:
👉 Build Triggers

Tick:

Poll SCM

Paste:

* * * * *

👉 Means every 1 minute check for changes

Click:
👉 Save

🔄 STEP 8: Test Auto Trigger

Go to GitHub repo

Open README
Click Edit
Add:
test change
Click Commit

⏳ Wait 1 minute

Go to Jenkins → Build History

✅ New build appears automatically
