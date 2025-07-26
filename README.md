# Blog Platform with Microservices

![Architecture](https://img.shields.io/badge/Architecture-Microservices-blue.svg) ![Language](https://img.shields.io/badge/Language-Node.js-green.svg) ![Frontend](https://img.shields.io/badge/Frontend-Next.js-black.svg) ![Deployment](https://img.shields.io/badge/Deploy-AWS%20%7C%20Vercel-orange.svg)

A scalable, full-stack blog application built with a modern microservices architecture. This project demonstrates real-world patterns for building resilient and performant web applications, including asynchronous communication, distributed caching, and polyglot persistence.

## ✨ Key Features

-   **Microservices Architecture:** Independent services for Users, Blogs, and Authors.
-   **Asynchronous Communication:** Services communicate via **RabbitMQ** for a decoupled and resilient system.
-   **Smart Caching:** **Redis** is used for caching frequently accessed data with an intelligent cache invalidation strategy.
-   **Polyglot Persistence:** Uses the best database for the job: **PostgreSQL** for structured user data and **MongoDB** for flexible blog content.
-   **Secure Authentication:** Integrated with **Google Authentication (OAuth 2.0)** for secure and easy login.
-   **Containerized Deployment:** All backend services are containerized with **Docker** for consistent environments and easy deployment on **AWS EC2**.
-   **Modern Frontend:** A fast and responsive frontend built with **Next.js** and deployed on **Vercel**.

## ⚙️ Technology Stack

-   **Backend:** Node.js, Express.js
-   **Frontend:** Next.js, React
-   **Databases:** PostgreSQL, MongoDB
-   **Caching:** Redis
-   **Message Broker:** RabbitMQ
-   **Authentication:** Google OAuth 2.0
-   **Containerization:** Docker
-   **Deployment:** AWS EC2 (Backend), Vercel (Frontend)

## 🏗️ Architecture Overview

This project is composed of three primary backend microservices:

1.  **User Service:** Handles user registration, profiles, and authentication (Google OAuth). Persists data in PostgreSQL.
2.  **Author Service:** Manages author profiles and their relationship to content.
3.  **Blog Service:** Manages CRUD operations for blog posts. Uses MongoDB for storage and Redis for caching.

These services communicate asynchronously using RabbitMQ. The frontend is a separate Next.js application that interacts with the backend services via a public API.


[User] <--> [Frontend (Next.js on Vercel)] <--> [API Gateway] <--> [Backend Services (Docker on AWS)]
