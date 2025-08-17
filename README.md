# 🚗 Uber Ride Booking Platform (Microservices Architecture)

This project is a **backend system** for an Uber-like ride booking platform, designed with a scalable **Microservices Architecture** using **Spring Boot, Spring Cloud, and distributed technologies**.  

---

## 🗂️ Microservices Overview  

| Microservice        | Description                                                                 | Repository Link |
|----------------------|-----------------------------------------------------------------------------|-----------------|
| **AuthService**      | Manages user registration, login, and token-based authentication using JWT & Spring Security | [GitHub](https://github.com/harshu1236/UberProject-AuthService) |
| **BookingService**   | Handles ride booking lifecycle: request, assignment, and completion         | [GitHub](https://github.com/harshu1236/UberProject-BookimgService) |
| **ReviewService**    | Manages user feedback and ride ratings                                      | [GitHub](https://github.com/harshu1236/UberProject-ReviewService) |
| **LocationService**  | Manages driver geolocation data using Redis GeoSpatial                      | [GitHub](https://github.com/harshu1236/UberProject-LocationService) |
| **SocketService**    | Enables real-time rider-driver communication via WebSockets (STOMP Protocol) | [GitHub](https://github.com/harshu1236/UberProject-SocketService) |
| **EntityService**    | Defines shared data models/entities used across services for consistency    | [GitHub](https://github.com/harshu1236/UberProject-EntityService) |
| **EurekaServer**     | Implements service discovery and dynamic service registration using Netflix Eureka | [GitHub](https://github.com/harshu1236/UberProject-EurekaServer) |

---

## 🏗️ Architecture Overview  

A **scalable microservices architecture** where services communicate via REST APIs and WebSockets.  
- **Eureka Server** handles service discovery.  
- **JWT Authentication + Spring Security** secures user sessions.  
- **Redis GeoSpatial** is used for driver location tracking and queries.  
- **MySQL** stores persistent data.  
- **WebSocket (STOMP Protocol)** powers real-time updates between riders and drivers.  

*(Optional: Add architecture diagram here if available)*  

---

## 🚀 Technologies Used  

- **Backend:** Spring Boot, Spring Cloud (Netflix Eureka)  
- **Security:** JWT Authentication (Spring Security + BCrypt)  
- **Database:** MySQL, Redis (for GeoSpatial queries)  
- **Communication:** WebSocket with STOMP Protocol  
- **Build Tool:** Maven  

---

## 📦 How to Run  

### 1️⃣ Clone all microservices  
```bash
git clone https://github.com/harshu1236/UberProject-EurekaServer.git
git clone https://github.com/harshu1236/UberProject-EntityService.git
git clone https://github.com/harshu1236/UberProject-SocketService.git
git clone https://github.com/harshu1236/UberProject-LocationService.git
git clone https://github.com/harshu1236/UberProject-ReviewService.git
git clone https://github.com/harshu1236/UberProject-AuthService.git
git clone https://github.com/harshu1236/UberProject-BookimgService.git


# Start Eureka Server first
cd Uber-ServiceDiscovery-EurekaServer
mvn spring-boot:run

# Then start other services:
cd UberProject-AuthService
mvn spring-boot:run

cd UberBookingService
mvn spring-boot:run

# ...repeat for all services
