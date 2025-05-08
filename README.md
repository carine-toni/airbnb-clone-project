Team Roles
Project Manager : is responsible for distributing tasks across team members, planning work activities and updating project status
UI/UX designer
Thy design an easy to use and eye pleasing interfaces for a product
Software developers
They create codes and application front end and back end.
Quality assurance engineer
Their job is to verify whether an application meets the requirements both functional and non-functional.
DevOperation engineers serve a link between unifying and automating changes quickly and keeping and application stable.
<<<<<<< HEAD

Technology Stack

Django: A high-level Python web framework used to build the backend of the application, including RESTful APIs and server-side logic.

MySQL: A relational database system used to store structured data such as user profiles, bookings, listings, and transactions.

GraphQL: A query language for APIs that allows efficient data retrieval and manipulation, enabling clients to request exactly what they need.

Docker: A containerization platform that simplifies development and deployment by packaging the application with all its dependencies.

GitHub: A code hosting platform used for version control and collaborative development, enabling team workflows and repository management.

GitHub Actions: A CI/CD tool integrated with GitHub, used to automate tasks like testing, building, and deploying the application.

Database Design
1. User
User_ID: Unique identifier for each user (Primary Key).

First_Name: User’s first name.

Email: User's email address, used for authentication and communication.

Role: Defines the role of the user (e.g., Admin, Host, Customer).

Date_Joined: The date the user registered in the system.

Relationship:

A User can have multiple Properties (a host can list many properties).

A User can make multiple Bookings (customers book properties).

A User can write multiple Reviews for different properties.

A User can have multiple Payments related to their bookings.

2. Property
Property_ID: Unique identifier for each property (Primary Key).

Host_ID: Foreign Key that links to the User entity (the host who owns the property).

Name: Name or title of the property.

Price_Per_Night: The price of the property per night.

Address: The physical address of the property.

Relationship:

A Property belongs to one User (the host).

A Property can have multiple Bookings (users can book the property).

A Property can receive multiple Reviews from users who have stayed there.

3. Booking
Booking_ID: Unique identifier for each booking (Primary Key).

User_ID: Foreign Key that links to the User entity (the customer who made the booking).

Property_ID: Foreign Key that links to the Property entity (the property being booked).

Check_In_Date: The date when the customer checks in.

Total_Price: The total amount for the booking (calculated based on duration and price per night).

Relationship:

A Booking belongs to one User (the customer who made the booking).

A Booking belongs to one Property (the property being booked).

A Booking has one associated Payment (once a booking is made, a payment is processed).

4. Review
Review_ID: Unique identifier for each review (Primary Key).

User_ID: Foreign Key that links to the User entity (the user who wrote the review).

Property_ID: Foreign Key that links to the Property entity (the property being reviewed).

Rating: The star rating (e.g., 1 to 5 stars).

Review_Text: Written feedback provided by the user.

Relationship:

A Review belongs to one User (the user who writes the review).

A Review belongs to one Property (the property being reviewed).

A Review is not directly related to Bookings, but can only be made by users who have stayed at the property.

5. Payment
Payment_ID: Unique identifier for each payment (Primary Key).

Booking_ID: Foreign Key that links to the Booking entity (the booking associated with this payment).

Amount: The amount paid for the booking.

Payment_Method: The method of payment (e.g., Credit Card, PayPal).

Payment_Status: The status of the payment (e.g., successful, failed, pending).

Relationship:

A Payment is linked to one Booking (a payment is made for a specific booking).

A Payment relates to the User through the Booking entity, as the user makes the payment for the booking.

Summary of Entity Relationships:
User to Property: One-to-many. A user can list multiple properties (if they are a host).

User to Booking: One-to-many. A user (as a customer) can make many bookings.

Property to Booking: One-to-many. A property can have multiple bookings over time.

User to Review: One-to-many. A user can write many reviews, but each review is for one property.

Property to Review: One-to-many. A property can receive multiple reviews from different users.

Booking to Payment: One-to-one. Each booking has one payment associated with it.

Feature Breakdown

User Authentication and Authorization
Secure user registration and login.

Role-based access for hosts and guests.

Password hashing and session/token management.

2. Property Listings
Hosts can create, update, and delete listings.

Listings include images, descriptions, pricing, and location.

Search and filter functionality for users.

3. Booking System
Guests can book available properties for specific dates.

Availability management to prevent double bookings.

Booking confirmation and cancellation features.

4. User Dashboard
Hosts can manage their listings and bookings.

Guests can view upcoming and past bookings.

Edit profile and account settings.

5. Reviews and Ratings
Guests can leave reviews and ratings after a stay.

Hosts and guests can view ratings to build trust.

6. Payment Integration (Optional/Advanced)
Simulated or real payment processing for bookings.

Invoices or receipts sent via email.

7. Admin Panel
Admins can manage users, listings, and bookings.

Analytics and reports for platform usage.

8. API Layer
REST or GraphQL APIs to power frontend or mobile apps.

Secured endpoints with proper validation and error handling.

9. Responsive Frontend (if included)
Mobile-first UI design.

Smooth navigation and user-friendly forms.




=======
>>>>>>> 31a8487298394cba6b5c286993b66e70c9f74544
