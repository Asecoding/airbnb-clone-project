# **airbnb-clone-project**
*The Airbnb Clone Project Blueprint*

## About the Project

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

# Team Roles

## Business analyst (BA)

- Understands customer’s business processes

- Translates customer business needs into requirements

A business analyst dives deep into a customer’s workflows and analyzes stakeholder feedback to help a client formulate what their wants look like and align a customer’s vision with what a development team is producing. They translate an abstract product idea into a set of tangible requirements.

## Product owner (PO)

- Holds responsibility for a product vision and evolution


- Makes sure the final product meets customer requirements

Holding more responsibility for a product’s success than any other development team member, a product owner is a decision-maker. Balancing both business needs and market trends, they define a business strategy, shape up the product vision, make sure it satisfies customer needs, and manage a product backlog. Associated mainly with flexible Agile environments, a product owner is particularly useful in scenarios where requirements and workflows frequently change. The responsibilities of a BA and a PO sound quite similar. What’s the difference between the two, and is there a need for both in one project?

The critical difference is that a product owner provides the vision of a product without diving deep into how it is technically implemented, while a business analyst bridges the gap between a customer and a team, being a bit more on the technical side. So, a PO is more customer-oriented, while a BA is often more focused on the technicalities of the project. Professional business analysts are usually qualified to take over some of a product owner’s tasks, like managing the product backlog and modeling workflows, among other responsibilities.

## Project manager (PM)

- Makes sure a product or its part is delivered on time and within budget

- Manages and motivates the software development team

In sequential models, a project manager is responsible for distributing tasks across team members, planning work activities, and updating project status.

In Agile projects where the focus is on self-management, transparency, and shared ownership, a PM sets up the vision of a product, maintains transparency, fosters communication, searches for improvements in the development process, and makes sure a team delivers more value with each iteration.

## UI/UX designer

- Transforms a product vision into user-friendly designs

- Creates user journeys for the best user experience and highest conversion rates

There are two aspects to the product design process—user interface (UI) and user experience (UX) design.

A UI designer devises intuitive, easy-to-use, and eye-pleasing interfaces for a product, while the UX part stands for thinking out an entire journey of a user’s interaction with a product. A UX designer is thus involved in such activities as user research, persona development, information architecture design, wireframing, prototyping, and more.

## Software developer

- Engineers and stabilizes the product

- Solves any technical problems emerging during the development lifecycle

A software developer does the actual job and codes an application. And just like an app features a front end and a back end, there are front-end and back-end developers.

Front-end developers create the part of an application that users interact with, ensuring that an app offers an equally smooth experience to all—no matter the device, platform, or operational system.

Back-end developers, in turn, implement the core of an app—its algorithms and business logic. Experienced back-end developers not only write code but also do the tasks of an architect—for example, devise an app architecture or design and implement the necessary integrations.

## Test automation engineer

- Designs a test automation ecosystem

- Writes and maintains test scripts for automated testing

A test automation engineer is there to help you test faster and better. To enable that, they develop test automation scripts—small programs that provide reliable and continuous feedback on application quality without any human involvement.

## DevOps engineer

- Facilitates cooperation between development and operations teams

- Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery

Even in Agile environments, development and operations teams can be siloed. DevOps engineers serve as a link between the two teams, unifying and automating the software delivery process and helping strike a balance between introducing changes quickly and keeping an application stable. Working together with software developers, system administrators, and operational staff, DevOps engineers oversee and facilitate code releases on a CI/CD basis.
# Technology Stack
## Django
- Django: high level python web framework for building RESTful APIs

## PostgreSQL
- Advanced open-source reletional database

## GraphQL
- Modern API quary language (Alternative to REST)

# Database Design
Here’s a foundational overview of key entities for a database design that supports a property booking platform—think Airbnb-style. I'll outline the entities, key fields, and how they're connected:
## User
Represents individuals using the platform—both guests and hosts.
### Key Fields:

- user_id (Primary Key)

- name

- email

- phone_number

- user_type (e.g., guest, host, admin)

### Relationships:

- A user can own multiple properties

- A user can make many bookings

- A user can write many reviews

## 2. Properties

Represents listings available for booking.
### Key Fields:
- property_id (Primary Key)

- host_id (Foreign Key → Users.user_id)

- title

- location

- price_per_night

### Relationships:

- A property is owned by one host

- A property can have multiple bookings

- A property can receive multiple reviews

## 3. Bookings
Captures reservation details made by guests.

- Key Fields:

- booking_id (Primary Key)

- guest_id (Foreign Key → Users.user_id)

- property_id (Foreign Key → Properties.property_id)

- check_in_date

- check_out_date

### Relationships:

- A booking is made by one user (guest)

- A booking is for one property

- A booking may be tied to a payment

## 4. Reviews
Allows users to leave feedback on properties.

### Key Fields:

- review_id (Primary Key)

- guest_id (Foreign Key → Users.user_id)

- property_id (Foreign Key → Properties.property_id)

- rating (e.g., 1 to 5)

- comment

### Relationships:

- A review is written by a guest

- A review is about a specific property

## 5. Payments
Tracks financial transactions related to bookings.

### Key Fields:

- payment_id (Primary Key)

- booking_id (Foreign Key → Bookings.booking_id)

- amount

- payment_method

- payment_status

### Relationships:

- A payment is linked to one booking

- Each booking typically has one payment record
