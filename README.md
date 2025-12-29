# HotelSalesDB

This repository contains SQL scripts for managing a hotel sales database. The database includes tables for Customers, Staff, Rooms, Bookings, and Payments, along with queries, views, and triggers for various operational and analytical purposes.

## Database Schema

### Tables

1. **Customers**  
   - CustomerID (INT, Primary Key, Auto Increment)  
   - FirstName (VARCHAR)  
   - LastName (VARCHAR)  
   - Email (VARCHAR, Unique)  
   - Phone (VARCHAR)  
   - City (VARCHAR)

2. **Staff**  
   - StaffID (INT, Primary Key, Auto Increment)  
   - FirstName (VARCHAR)  
   - LastName (VARCHAR)  
   - Role (VARCHAR)  
   - Phone (VARCHAR)  
   - Email (VARCHAR)

3. **Rooms**  
   - RoomID (INT, Primary Key, Auto Increment)  
   - RoomType (VARCHAR)  
   - PricePerNight (DECIMAL)  
   - Capacity (INT)

4. **Bookings**  
   - BookingID (INT, Primary Key, Auto Increment)  
   - CustomerID (INT, Foreign Key → Customers)  
   - RoomID (INT, Foreign Key → Rooms)  
   - StaffID (INT, Foreign Key → Staff)  
   - CheckInDate (DATE)  
   - CheckOutDate (DATE)  
   - TotalAmount (DECIMAL)

5. **Payments**  
   - PaymentID (INT, Primary Key, Auto Increment)  
   - BookingID (INT, Foreign Key → Bookings)  
   - PaymentDate (DATE)  
   - PaymentMethod (VARCHAR)  
   - Amount (DECIMAL)

## SQL Queries

This repository contains SQL queries for:

- Listing, filtering, and updating data in all tables
- Aggregate queries like AVG, MIN, MAX, COUNT
- Using `CONCAT` and `CONCAT_WS` to format output
- Subqueries for analytical purposes
- Self joins to identify duplicates or patterns
- Ordering and limiting results

### Examples

- Find rooms with capacity greater than the average:  
  ```sql
  SELECT * FROM Rooms WHERE Capacity > (SELECT AVG(Capacity) FROM Rooms);
