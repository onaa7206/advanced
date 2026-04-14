📁 PROJECT STRUCTURE
ai-compose-project/
│
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── index.html
│   └── Dockerfile
│
└── docker-compose.yml
Install Docker + Compose
📍 Where:

👉 Browser

Install Docker Desktop

✔️ After install:

Open Docker Desktop
Wait until:
Docker is running
🔍 Verify installation
📍 Where:

👉 Git Bash

docker --version
docker compose version
2️⃣ Create Project Directory
📍 Where:

👉 Git Bash

mkdir ai-compose-project
cd ai-compose-project
3️⃣ Create Folder Structure
📍 Where:

👉 Git Bash

mkdir backend frontend
touch docker-compose.yml
4️⃣ Create Backend (AI Model)
📍 Go to backend folder:
cd backend
Create files:
touch app.py requirements.txt Dockerfile

🧠 backend/app.py
bash:- code app.py


from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "AI Model Running!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)

    
📦 backend/requirements.txt
code requirements.txt

flask


🐳 backend/Dockerfile
code Dockerfile

FROM python:3.10

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]

5️⃣ Create Frontend

📍 Go back:
bash:

cd ..
cd frontend

Create files:
touch index.html Dockerfile
🌐 frontend/index.html
bash:
code index.html

<h1>Frontend Connected to AI Backend</h1>

🐳 frontend/Dockerfile

code:

code Dockerfile

paste in file:

FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

6️⃣ Create docker-compose.yml
📍 Go to root:
cd ..
Open file:
code docker-compose.yml


⚙️ docker-compose.yml
version: '3'

services:
  backend:
    build: ./backend
    ports:
      - "5000:5000"

  frontend:
    build: ./frontend
    ports:
      - "8080:80"

  database:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: root


      
7️⃣ Build and Start Containers
📍 Where:

👉 Git Bash (inside project folder)

docker compose up --build


8️⃣ Verify Running Containers

bash:
docker ps

✔️ You will see:

backend
frontend
database
9️⃣ Test Application
🌐 Frontend:
crome:

http://localhost:8080

✔️ Output:

Frontend Connected to AI Backend
🌐 Backend:
crome:

http://localhost:5000

✔️ Output:

AI Model Running!
🔟 Stop All Containers
docker compose down
