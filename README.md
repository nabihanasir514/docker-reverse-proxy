# Docker Reverse Proxy Project

This project demonstrates a simple containerized setup using Docker Compose where:

* Nginx acts as a reverse proxy
* A Python Flask backend serves a basic response

---

## 📦 Project Structure

```
docker-reverse-proxy/
│
├── docker-compose.yml
│
├── nginx/
│   └── default.conf
│
└── backend/
    ├── app.py
    └── Dockerfile
```


## ⚙️ How It Works

* The **backend service** runs a Flask app on port 5000.
* The **nginx service** listens on port 80 inside the container and forwards all requests to the backend.
* Docker Compose creates a shared network, allowing services to communicate using service names (e.g., `backend`).

---

## 🌐 Network Configuration

* Docker Compose automatically creates a default network.

* Services communicate using:

  http://backend:5000

* Nginx uses this internal DNS to forward requests to the backend container.

---

## ▶️ How to Run (Step-by-Step)

### 1. Navigate to project folder

```bash
cd docker-reverse-proxy
```

### 2. Build and start containers

```bash
docker-compose up --build
```

### 3. Open in browser

Go to:

```
http://localhost:8080
```

### 4. Expected Output

```
Hello from Backend
```

---

## ⛔ Stop Containers

Press:

```bash
CTRL + C
```

Then run:

```bash
docker-compose down
```

---

## ✅ Summary

* Nginx acts as a reverse proxy
* Backend runs independently in another container
* Docker Compose connects them via an internal network
* Clean separation of concerns (proxy vs application)

---
