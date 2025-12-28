# docker-from-zero
🐳 Docker from Zero — Hands-on Learning

This repository documents my hands-on learning journey with Docker, using WSL 2 + Ubuntu on Windows.

The goal is to understand Docker the right way, focusing on real-world concepts such as containers, images, ports, volumes, and basic infrastructure.

🖥️ Environment

- Windows 10

- WSL 2

- Ubuntu (WSL)

- Docker Desktop
---
# 📌 What I’ve learned so far

What Docker is and why it is used

Difference between images and containers

Running containers interactively

Listing and removing containers

Exposing ports

Persistent data using volumes

Running services like Nginx and MySQL
---
🧪 Lesson 1 — Containers and Images
🔹 Running the first container
docker run hello-world

<img width="800" height="393" alt="image" src="https://github.com/user-attachments/assets/1b5ac0be-a328-4788-af39-40eccfe34fa1" />

---

🔹 Running an interactive Ubuntu container
```bash

docker run -it ubuntu bash
```
<img width="682" height="230" alt="image" src="https://github.com/user-attachments/assets/e181f84f-9adf-47d1-8755-7190192aed29" />

---
Inside the container:

```bash
ls
cat /etc/os-release
exit
```

<img width="1007" height="316" alt="image" src="https://github.com/user-attachments/assets/e77e338b-9c86-4674-b8a8-8639bc5d068d" />

---
Print inside the Ubuntu container showing system files

🔹 Listing containers
```bash
docker ps -a
```

<img width="1356" height="144" alt="image" src="https://github.com/user-attachments/assets/16ae8fc9-53fa-47c9-a9f1-1436b5c0c320" />



---

### 🌐 Lesson 2 — Ports and Networking
🔹 Running Nginx and exposing a port
```bash
docker run -d -p 8080:80 nginx
```

<img width="1350" height="171" alt="image" src="https://github.com/user-attachments/assets/ebd8595e-3f99-414d-a188-5065ad84125b" />

Access in the browser:

http://localhost:8080


<img width="1302" height="643" alt="image" src="https://github.com/user-attachments/assets/f20ed867-04e5-4a72-b25e-c32b870a7674" />



---

🔹 Checking running containers

```bash
docker ps
```

<img width="1188" height="111" alt="image" src="https://github.com/user-attachments/assets/7216548b-5f29-4172-8cf4-7752a1b706da" />

---

### 💾 Lesson 3 — Volumes and Persistence
🔹 Running MySQL with a volume
```bash
docker run -d \
  --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -p 3306:3306 \
  -v mysql_data:/var/lib/mysql \
  mysql:8.0
```
  <img width="903" height="188" alt="image" src="https://github.com/user-attachments/assets/30f63e19-1624-4b9b-8b49-636eaaf7bdce" />

---

🔹 Listing volumes
```bash
docker volume ls
```

<img width="1176" height="84" alt="image" src="https://github.com/user-attachments/assets/953bcd1b-1519-477e-a123-ad0f85f960ae" />

---

🔹 Removing container without losing data

```bash

docker stop mysql-db
docker rm mysql-db
```
---

Recreating:

```bash

docker run -d \
  --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -p 3306:3306 \
  -v mysql_data:/var/lib/mysql \
  mysql:8.0
```
---

✅ Data persists thanks to volumes.

🚀 Next steps

- Dockerfile

- Docker-compose

- Backend with:

- Python

- .NET

- Java

- Database integration

<!-- ===================== RODAPÉ ===================== -->
✨ Author

Camila Dziubat
Junior Software Engineer | Backend Developer
Learning Docker, Linux, and Backend technologies 🚀













