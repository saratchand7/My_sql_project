🎬 Cinema Seat & Ticket Booking System Using MySQL

📌 Project Overview

The **Cinema Seat & Ticket Booking System** is a database management project developed using MySQL. It is designed to manage movie details, cinema screens, seats, show schedules, customer information, bookings, and payment records in a structured and relational database.

The project demonstrates practical SQL concepts, including table creation, primary and foreign keys, constraints, joins, aggregate functions, subqueries, indexes, views, stored procedures, stored functions, and triggers.

 🎯 Objectives

- Design a relational database for cinema seat and ticket booking.
- Maintain relationships between movies, shows, screens, seats, customers, and bookings.
- Use constraints to maintain data consistency.
- Retrieve booking details and show schedules using SQL queries.
- Generate customer booking summaries and payment-wise revenue reports.
- Implement reusable database objects using views, procedures, functions, and triggers.

 🗂️ Database Schema

The database contains seven main tables:

| Table | Description |
|---|---|
| `movies` | Stores movie titles, genres, languages, durations, release dates, and ratings. |
| `screens` | Stores cinema screen names, types, and total seat capacity. |
| `seats` | Stores seat numbers, row names, seat types, and screen references. |
| `shows` | Stores movie schedules, screen assignments, show dates, timings, and ticket prices. |
| `customers` | Stores customer names, email addresses, phone numbers, cities, and registration dates. |
| `bookings` | Stores customer bookings, booking dates, amounts, booking statuses, and payment details. |
| `booking_seats` | Connects bookings with shows and individual seats, including seat prices. |

🔗 Entity Relationship Diagram

The ER diagram illustrates the relationships between the seven database tables, including primary keys, foreign keys, and one-to-many relationships.

Add the ER diagram image to your repository as `ER-Diagram.png` and display it here:

![Cinema Seat and Ticket Booking System ER Diagram](ER-Diagram.png)

🛠️ Technologies Used

- **Database:** MySQL
- **Database Tool:** MySQL Workbench
- **Language:** SQL
- **Concepts:** Relational Database Design, Constraints, Joins, Indexes, Views, Stored Procedures, Functions, and Triggers

⚙️ Database Features

1. Relational Database Design

- Seven related tables with primary and foreign keys.
- Unique constraints for customer email addresses, phone numbers, screen names, and seat assignments.
- Check constraints for movie duration, ratings, ticket prices, and booking amounts.
- ENUM columns for booking status, payment method, and payment status.

2. SQL Queries and Reports

The project includes queries for:

- Displaying and filtering movies.
- Finding movies by language, genre, and rating.
- Retrieving show schedules and screen details.
- Viewing customer booking histories.
- Calculating revenue by payment method.
- Counting movies by genre.
- Calculating average ratings.
- Identifying customers with multiple bookings.
- Finding customers without bookings.
- Counting booked seats for each show.

3. Indexes

Indexes are used to support frequently accessed data and filtering operations.

- `idx_shows_date_time`
- `idx_shows_movie_date`
- `idx_bookings_customer_status`
- `idx_bookings_date`

 4. Views

The project defines reusable views for reporting:

- `view_show_schedule` – Displays movie and show scheduling information.
- `view_booking_details` – Combines customer, movie, show, and booking details.
- `view_show_occupancy` – Summarizes booked seats and occupancy percentages.
- `view_customer_booking_summary` – Summarizes confirmed bookings and customer spending.

 5. Stored Procedures

- `sp_get_customer_bookings` – Retrieves bookings for a specified customer.
- `sp_revenue_by_payment` – Summarizes successful booking revenue by payment method.
- `sp_get_shows_by_date` – Retrieves shows scheduled on a given date.
- `sp_get_available_seats` – Lists seats available for a specified show.

6. Stored Functions

- `fn_booking_seat_total` – Calculates the total seat price for a booking.
- `fn_customer_spending` – Calculates a customer's confirmed, successfully paid booking amount.
- `fn_available_seats` – Estimates the remaining seats for a show.

7. Triggers

- `trg_validate_booking_show_insert` – Checks that a booking-seat record uses the same show as its booking.
- `trg_validate_seat_screen_insert` – Checks that a seat belongs to the screen assigned to the show.
- `trg_update_booking_total_insert` – Recalculates a booking total after a seat is inserted.
- `trg_block_movie_delete` – Prevents deleting a movie while shows reference it.

🚀 How to Run the Project

1. Install MySQL Server and MySQL Workbench.
2. Download or clone this repository.
3. Open the SQL script in MySQL Workbench.
4. Review the script before execution. **The setup script drops and recreates the `cinema_booking` database**, so do not run it against a database containing data you need to keep.
5. Execute the script to create the tables and insert the sample data.
6. Execute the SQL statements for indexes, views, stored procedures, triggers, and functions.
7. Run the provided `SELECT` queries, `CALL` statements, and function queries to examine the results.

Example Queries

Display all movies:

```sql
USE cinema_booking;

SELECT *
FROM movies;
```

View the show schedule:

```sql
SELECT *
FROM view_show_schedule;
```

Retrieve bookings for customer ID 1:

```sql
CALL sp_get_customer_bookings(1);
```

Calculate the total seat price for booking ID 1:

```sql
SELECT fn_booking_seat_total(1) AS booking_seat_total;
```

Calculate successful revenue by payment method:

```sql
CALL sp_revenue_by_payment();
```

📚 Learning Outcomes

Through this project, I practised:

- Designing relational database schemas.
- Defining primary keys, foreign keys, and constraints.
- Writing SQL queries using joins, grouping, filtering, and subqueries.
- Creating indexes for common query patterns.
- Building reusable views, stored procedures, and functions.
- Implementing triggers for data validation and automatic updates.
- Testing database operations and reviewing query results in MySQL Workbench.

 🔮 Future Enhancements

- Develop a web-based interface for customers and administrators.
- Add interactive seat selection and booking management.
- Improve seat availability handling for cancelled bookings.
- Integrate a payment gateway.
- Add user authentication and role-based access.
- Generate additional reports and booking analytics.

 👨‍💻 Author

**Sarat Chand Chintala**

MCA Graduate | Python Full Stack Trainee

GitHub: [saratchand7](https://github.com/saratchand7)

---

*This project was developed for learning and demonstrating relational database design and SQL programming using MySQL.*
