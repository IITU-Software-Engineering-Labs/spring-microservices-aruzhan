Spring Boot Microservices Project
Student: Aruzhan
Branch: aruzhan-microservice
Commit Hash: 79955d41f3d1557c0c069d584399a5bdefb18280

What I Built
Eureka Server:
This is the center where all services register and discover each other. It runs on port 8761, and it doesn't register itself but accepts registrations from other microservices.

API Gateway:
The main gateway — it accepts all external requests and forwards them to the appropriate microservice. It runs on port 8085. I set up the route so that requests to /api/students/** are forwarded to the Student-Service.

Student-Service:
This is the main microservice that returns student information. It runs on port 9090 and is registered in Eureka. I added a basic endpoint /students/{id} that returns the student's ID, name, and specialty.

Unique Feature — Favorite Drink:
I added a new field favoriteDrink, because it's something simple but personal. Everyone has a favorite drink — coffee, tea, or something unusual. This shows that even in technical things, individuality can be reflected. The endpoint /students/favorite-drink/{drink} allows finding students based on their favorite drink.

Why These Technologies
Eureka Server is necessary for microservices to know about each other — it's like a contact list for services.

API Gateway simplifies the process — instead of calling each service directly, we go through a single entry point.

This helps build a scalable, resilient, and easily manageable architecture.

How to Run
Clone the repository:
git clone https://github.com/IITU-Software-Engineering-Labs/2116.git

Switch to your branch:
git checkout aruzhan-microservice

Run each service in order in IntelliJ IDEA:

eureka-server (port 8761)

student-service (port 9090)

api-gateway (port 8085)

Check the services via Postman or a browser:

To get student information:
http://localhost:8085/api/students/1

To get students by their favorite drink:
http://localhost:8085/api/students/favorite-drink/coffee
