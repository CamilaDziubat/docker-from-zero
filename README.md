# docker-from-zero
🐳 Docker from Zero — Hands-on Learning

This repository documents my hands-on learning journey with Docker, using WSL 2 + Ubuntu on Windows.

The goal is to understand Docker the right way, focusing on real-world concepts such as containers, images, ports, volumes, and basic infrastructure.

🖥️ Environment

Windows 10

WSL 2

Ubuntu (WSL)

Docker Desktop

📌 What I’ve learned so far

What Docker is and why it is used

Difference between images and containers

Running containers interactively

Listing and removing containers

Exposing ports

Persistent data using volumes

Running services like Nginx and MySQL

🧪 Lesson 1 — Containers and Images
🔹 Running the first container
docker run hello-world

<img width="800" height="393" alt="image" src="https://github.com/user-attachments/assets/1b5ac0be-a328-4788-af39-40eccfe34fa1" />


🔹 Running an interactive Ubuntu container
docker run -it ubuntu bash

<img width="682" height="230" alt="image" src="https://github.com/user-attachments/assets/e181f84f-9adf-47d1-8755-7190192aed29" />


Inside the container:

ls
cat /etc/os-release
exit


<img width="1007" height="316" alt="image" src="https://github.com/user-attachments/assets/e77e338b-9c86-4674-b8a8-8639bc5d068d" />


Print inside the Ubuntu container showing system files

🔹 Listing containers
docker ps -a


📸 Screenshot suggestion:

Print showing stopped containers

🌐 Lesson 2 — Ports and Networking
🔹 Running Nginx and exposing a port
docker run -d -p 8080:80 nginx


Access in the browser:

http://localhost:8080


📸 Screenshot suggestion:

Print of the browser showing “Welcome to nginx!”

🔹 Checking running containers
docker ps

💾 Lesson 3 — Volumes and Persistence
🔹 Running MySQL with a volume
docker run -d \
  --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -p 3306:3306 \
  -v mysql_data:/var/lib/mysql \
  mysql:8.0

🔹 Listing volumes
docker volume ls


📸 Screenshot suggestion:

Print showing mysql_data volume

🔹 Removing container without losing data
docker stop mysql-db
docker rm mysql-db


Recreating:

docker run -d \
  --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -p 3306:3306 \
  -v mysql_data:/var/lib/mysql \
  mysql:8.0


✅ Data persists thanks to volumes.

🚀 Next steps

Dockerfile

docker-compose

Backend with:

Python

.NET

Java

Database integration

✨ Author

Camila Dziubat
Junior Software Engineer | Backend Developer
Learning Docker, Linux, and Backend technologies 🚀






