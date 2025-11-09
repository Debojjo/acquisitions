# 🧩 Acquisitions API

A production-ready **backend API** built using **Node.js**, **Express**, **Drizzle ORM**, **Neon Postgres**, and **Docker**, with complete **authentication**, **logging**, **security**, and **CI/CD pipelines**.

---

## 🚀 Overview

The **Acquisitions API** is a secure, modular backend service designed for scalability and maintainability.  
It provides user authentication (JWT-based), database integration with **Neon Postgres**,  
and automated deployment pipelines powered by **GitHub Actions** and **Docker**.

---

## ⚙️ Tech Stack

| Category | Technology |
|-----------|-------------|
| **Runtime** | Node.js (v20.x) |
| **Framework** | Express.js |
| **ORM** | Drizzle ORM |
| **Database** | Neon Postgres (Cloud & Local via Docker) |
| **Authentication** | JWT + Cookies |
| **Validation** | Zod |
| **Logging** | Winston + Morgan |
| **Security** | Helmet + ArcJet |
| **CI/CD** | GitHub Actions |
| **Containerization** | Docker & Docker Compose |

---

## 🏗️ Project Structure
acquisitions/
├── src/
│ ├── app.js
│ ├── index.js
│ ├── server.js
│ ├── config/
│ │ ├── database.js
│ │ ├── logger.js
│ │ ├── jwt.js
│ │ └── cookies.js
│ ├── models/
│ │ └── user.model.js
│ ├── controllers/
│ │ └── auth.controller.js
│ ├── routes/
│ │ └── routes.js
│ ├── validations/
│ │ └── auth.validation.js
│ └── services/
│ └── user.service.js
├── docker-compose.dev.yml
├── docker-compose.prod.yml
├── Dockerfile
├── .env.development
├── .env.production
├── package.json
└── README.md


---

## 🧰 Setup & Installation

### 🔹 Development Setup

# 1. Clone the repository
git clone https://github.com/Debojjo/acquisitions.git
cd acquisitions

# 2. Install dependencies
npm install

# 3. Start the app (development mode)
npm run dev


This uses Neon Local (via Docker) to simulate Postgres locally.

To start with Docker Compose:

docker-compose -f docker-compose.dev.yml up --build

🔹 Production Setup

Set your production environment variables in .env.production:

NODE_ENV=production
DATABASE_URL=postgres://user:password@neon.tech/dbname
JWT_SECRET=your_jwt_secret


Then build and run:

docker-compose -f docker-compose.prod.yml up --build

🔐 Authentication Routes
Method	Endpoint	Description
POST	/signup	Register a new user
POST	/signin	Log in a user
POST	/signout	Log out a user
GET	/users/:id	Retrieve user by ID
PATCH	/users/:id	Update user data
DELETE	/users/:id	Delete a user

Tested with HTTPie for fast command-line API testing.

🧱 Security

Helmet: Adds security headers to Express responses.

ArcJet: Protects from malicious traffic and abuse patterns.

CORS & Cookie Parser: Handles secure sessions and cross-origin requests.

JWT Tokens: Stateless authentication for APIs.

🧩 CI/CD Workflows
Workflow	Description	Trigger
lint-and-format.yml	Runs ESLint and Prettier checks	On push/pull_request
tests.yml	Runs automated tests and uploads coverage	On push/pull_request
docker-build-and-push.yml	Builds & pushes Docker images to Docker Hub	On push to main

All workflows are visible under the Actions tab.

🐳 Docker Setup

Development (with Neon Local):

docker-compose -f docker-compose.dev.yml up --build


Production:

docker-compose -f docker-compose.prod.yml up --build -d

📘 API Testing

Example using HTTPie:

# Signup
http POST :3000/signup name="John Doe" email="john@example.com" password="secure123"

# Signin
http POST :3000/signin email="john@example.com" password="secure123"


For future expansion, a Postman workspace or Swagger UI can be linked here.

🧩 Future Enhancements

 Add role-based access control

 Integrate request caching (Redis)

 Add rate-limiting & monitoring dashboard

 Deploy backend on Render or Railway

👨‍💻 Author

Debojjo Talukdar
📍 Web Developer | DevOps Enthusiast
🔗 GitHub

📬 debojjotalukdar@gmail.com
Feel free to fork, explore, and contribute!


