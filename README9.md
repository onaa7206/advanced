
1. Install Docker & sign in docker (Windows)
🔹 Where to do this:
Use your browser (Chrome/Edge)
🔹 Steps:
Go to: Docker Desktop official website
Download Docker Desktop for Windows
Run installer → keep default settings
Restart system (important)
🔹 Start Docker:
Open Start Menu
Search → Docker Desktop
Wait until it shows: “Docker is running”
🔹 Verify installation
🔹 Where:

👉 Open Git Bash (recommended) OR Command Prompt

🔹 Command:
docker --version

✔️ Output example:

Docker version 25.x.x
📁 2. Create Project Directory
🔹 Where:

👉 Open Git Bash

🔹 Commands:
mkdir ai-docker-project
cd ai-docker-project

✔️ This creates folder inside your current location (usually C:\Users\YourName)

📄 3. Create Required Files
🔹 Where:

👉 Inside Git Bash (same folder)

🔹 Command:
touch app.py requirements.txt Dockerfile
🔹 If touch doesn’t work (Windows issue):

Use:

type nul > app.py
type nul > requirements.txt
type nul > Dockerfile
🧠 4. Write Application Code
🔹 Where:

👉 Open file using Notepad

🔹 Command:
notepad app.py
🔹 Paste this code:
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "AI Model Running Successfully!"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)

👉 Save and close Notepad

📦 5. Create Requirements File
🔹 Where:

👉 Git Bash

🔹 Command:
notepad requirements.txt
🔹 Add:
flask

👉 Save and close

🐳 6. Create Dockerfile
🔹 Where:

👉 Git Bash

🔹 Command:
notepad Dockerfile
🔹 Add:
FROM python:3.10
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]

👉 Save and close

🏗️ 7. Build Docker Image
🔹 Where:

👉 Git Bash
👉 Make sure you are inside:

ai-docker-project
🔹 Command:
docker build -t ai-model-app .
🔹 What happens:
Docker reads Dockerfile
Installs Python + Flask
Creates image

✔️ Successful message:

Successfully built
Successfully tagged ai-model-app
▶️ 8. Run Docker Container
🔹 Where:

👉 Git Bash

🔹 Command:
docker run -d -p 5000:5000 ai-model-app
🔹 What this does:
Runs your app
Maps port 5000 → localhost
✅ 9. Verify Running Container
🔹 Where:

👉 Git Bash

🔹 Command:
docker ps
🔹 Output example:
CONTAINER ID   IMAGE           PORTS
abcd1234       ai-model-app    0.0.0.0:5000->5000

✔️ Means container is running

🌐 10. Test Application
🔹 Where:

👉 Open browser (Chrome/Edge)

🔹 URL:
http://localhost:5000
🔹 Output:
AI Model Running Successfully!
🛑 11. Stop Container
🔹 Where:

👉 Git Bash

🔹 Step 1: Get container ID
docker ps
🔹 Step 2: Stop container
docker stop CONTAINER_ID
🧹 12. (Optional) Remove Container
🔹 Where:

👉 Git Bash

🔹 Command:
docker rm CONTAINER_ID

##############################################################################################################################################################################
🎯 FINAL FLOW (VERY IMPORTANT FOR EXAM)


Install Docker
Create project folder
Add app.py + requirements.txt + Dockerfile
Build image → docker build
Run container → docker run
Check → docker ps
Test → browser
Stop → docker stop
