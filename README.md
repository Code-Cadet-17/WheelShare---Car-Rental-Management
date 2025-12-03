# WheelShare - Car Rental Management (Spring Boot Version)

**Technologies Used:** Java (Spring Boot), JavaScript, HTML, CSS, Bootstrap 5, MySQL

This project implements:

- Viewing available cars
- Booking rentals (with start & end dates)
- Returning vehicles
- Viewing complete rental history for a user (by email)

## 1. Database Setup (MySQL)

Run the SQL script in `database/wheelshare.sql`:

```sql
SOURCE database/wheelshare.sql;
```

(or copy paste its contents into your MySQL client)

This creates:

- `wheelshare_db` database
- `cars` table with sample rows
- `bookings` table with FK to `cars`

## 2. Configure DB credentials

Edit `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/wheelshare_db?createDatabaseIfNotExist=true&useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=root
```

Put your own MySQL username/password.

## 3. Build & Run

```bash
mvn clean install
mvn spring-boot:run
```

Then open in browser:

```
http://localhost:8080/
```

## 4. Main URLs

- `/cars` – List available cars (landing page)
- `/bookings/new?carId={id}` – Booking form
- `POST /bookings` – Create booking, calculate total, mark car unavailable
- `/history` – Shows email form
- `/history?email=xyz@example.com` – Rental history table
- `POST /bookings/{id}/return` – Mark booking as RETURNED + free the car

## 5. For your resume / report

> **WheelShare - Car Rental Management**  
> Developed a web-based application to manage car rentals. Features include viewing available cars with dates, booking rentals, returning vehicles, and maintaining complete rental history for users. Technologies used: **Java (Spring Boot), JavaScript, HTML, CSS, Bootstrap, MySQL**.
