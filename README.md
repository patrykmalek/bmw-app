# Aplikacja do obsługi biura nieruchomości

# Project Objective
Student project.

The aim of the project was to build a system for a real estate office that would streamline the process of buying and selling properties. The system allows for adding new property listings, browsing them by users, and managing and monitoring the purchasing process.

# Requirements List
## BMW Application Features:
- Login
- Registration
- Adding, deleting, and editing properties in the system
- Scheduling property visits for "on-site inspections"
- Contacting the office through a contact form
- Property search
- Monitoring the status of investments

# Main Actors
- Client - a person looking to purchase a property
- Agent - a real estate office agent

# Technologies Used
## Front-end
- React
- Redux
- Ant Design
- Playwright

## Back-end
- Spring Boot
- Spring Security
- Keycloak
- Eureka
- Zipkin
- Docker
- PostgresSQL
- InfluxDB

## Layers of Microservices

0. Application - Starts our microservice

1. Controller - separates the UI from the front-end,
   describes all endpoints that front-end can call.
   
2. Service - interact with data, contains the business logic

3. Repository - interacts with the DB

### Additional files

1. Entities - represents data (for example: Customer.java)
2. Request - contains the request body

## Remember when adding the new microservice

1. Register the Controller endpoints in the API Gateway (apigw/main/resources/application.yml)
2. add the eureka dependency and add an EurekaClient decorator in the application

### Ports

- 5432 - postgres
- 5050 - pgadmin
- 9411 - zipkin
- 8761 - eureka
- 8083 - API Gateway (main backend port)
- 8084,8081,8082 - microservices
- 8080 - keycloak
- 8090 - App monitoring using InfluxDB

## To run docker

1. Make sure you are in the root directory
2. first run: `docker-compose up -d` (you need docker version > 2.1)
3. next runs: `docker-compose start`

## TODO: In the future

1. For now, we run all the database's in the one Docker container,
we can change that in the `docker-compose.yml`, adding the separate
   service for every microservice database, f.e: postgres-appointment


