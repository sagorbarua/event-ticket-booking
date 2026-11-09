##Users and roles

Anyone can register with name, email, password. Email must be unique.
Registered users log in and get a token.
Two roles: Admin and Customer.
Admin creates, edits, and deletes events. Customers can only view events.
A customer can see only their own bookings.

##Events

An event has a title, description, date/time, price, and total seats.
The system tracks how many seats are still available.

##Bookings

A customer books a number of seats for an event.
A new booking starts as Pending. After the fake payment it becomes Paid.
If not paid within 10 minutes, it becomes Expired and the seats go back to the event.
If the client sends the same request twice (double click, network retry), only one booking is created.
The business must never sell more seats than exist.

##Quality expectations

Passwords must not be readable by anyone, even with database access.
Bad input (negative seats, past date, empty title) must be rejected with a clear error.