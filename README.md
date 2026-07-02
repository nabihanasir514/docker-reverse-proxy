# 🐳 Docker Reverse Proxy Project

This project demonstrates a simple containerized architecture using **Docker Compose**, where:

* **Nginx** acts as a reverse proxy
* A **Python Flask backend** serves a basic response

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

---

## ⚙️ How It Works

* The **backend service** runs a Flask application on port **5000**.
* The **nginx service** listens on port **80** inside the container.
* All incoming requests are forwarded by Nginx to the backend.
* Docker Compose creates a shared network, allowing services to communicate using service names (e.g., `backend`).

---

## 🌐 Network Configuration

* Docker Compose automatically creates a **default bridge network**.

* Services communicate internally using:

  ```
  http://backend:5000
  ```

* Nginx uses Docker’s built-in DNS to resolve the backend service name.

---

## ▶️ How to Run (Step-by-Step)

### 1. Navigate to the project folder

```bash
cd docker-reverse-proxy
```

### 2. Build and start containers

```bash
docker-compose up --build
```

### 3. Open in browser

Visit:

```
http://localhost:8080
```

### 4. Expected Output

```
Hello from Backend
```

---

## ⛔ Stopping the Containers

Press:

```bash
CTRL + C
```

Then run:

```bash
docker-compose down
```

---

## ✅ Key Takeaways

* Nginx acts as a **reverse proxy**
* Backend runs in a **separate container**
* Docker Compose enables **service-to-service communication**
* Clean separation between **application layer and proxy layer**

---

## 🚀 Future Improvements (Optional)

* Add **load balancing** with multiple backend instances
* Implement **health checks**
* Use **Node.js backend** as an alternative
* Deploy on cloud platforms like **AWS / Render**

---
