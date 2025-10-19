# airbnb-clone-project
This project is a full-stack clone of the popular accommodation booking platform AirBnB. The goal is to build a functional web application that allows users to browse property listings, view detailed property information, and complete bookings. The project will cover frontend development, backend APIs, database design, and deployment.

# Frontend
## Project goals
1. Translate the Figma mockups for the primary pages into functional web pages.
2. Implement a fully responsive layout that provides seamless user experiences on all devices.
3. Have organized and well-documented codebase following the best project practices.
4. Implement the key interactive features.
5. Optimize the web app with ARIA's set of attributes to be inclusive to people with disabilities.
6. Building the wireframes and prototypes of the app.

## Tech Stack
- **Frontend**: HTML, CSS, JAVASCRIPT (REACT or similar framework).
- **Version Control**: Git and GitHub.
- **Design Tools**: Figma for UI/UX design

## UI/UX Design Planning
### Design Goals
- Create an intuitive booking flow
- Maintain visual consistency
- Ensure fast loading times
- Prioritize mobile responsiveness
### Key Features
- Property search and filtering
- Detailed property viewing
- Secure checkout process
- User authentication
  
 ## Primary pages
-----------------------------------------------------------------------------------------
| Page                      | Description                                               |
|---------------------------|-----------------------------------------------------------|
| **Property Listing View** | Grid display of available properties with filters.        |
| **Listing Detailed View** | Complete property details with images and a booking form. |
| **Simple Checkout View**  | Streamlined payment and booking confirmation.             |
-----------------------------------------------------------------------------------------

## Importance of a user-friendly design in a booking platform
A user-friendly design directly increases revenue as customers are more likely to complete the path from discovery to purchase.
People are more likely to trust a professional and intuitive interface, as it creates enhanced trust with the brand.
The consistent design translates into customer retention. Previous smooth experiences can result in the customers going back to use your product.
The intuitive navigation and clear information prevent user frustration, and prevent losing users to competitors. 

## Figma Design Specifications
### Color Styles:
- **Primary**: #FF5A5F
- **Secondary**: #008489
- **Background**: #FFFFFF
- **Text**: #222222
- **Secondary Text**: #717171

## Typography:
- **Primary Font**: Circular, Medium (500), 16px
- **Headings**: Circular, Bold (700), 24px-32px
- **Secondary Text**: Circular, Book (400), 14px

## Importance of identifying design properties of a mock-up design
- The consistency allows you to create a style guide, creating a professional, cohesive user experience. It also reinforces the brand's visual identity.
- There can be reusable components that can be built and reused instead of styling every component individually.
- It ensures the initial design and the final product are matched.

## Project Roles and Responsibilities
| Role                   | Responsibilities                                                                                      |
| -----------------------|-----------------------------------------------------------------------------------------------        |
| **Project Manager**    | Manages the project schedule, ensures team collaboration, and is accountable for final delivery.      |
| **Frontend Developer** | Codes the user interface, builds reusable components, and ensures the site works on all devices.      |
| **Backend Developer**  | Creates the server-side logic, designs and manages the database, and builds the APIs.                 |
| **Designer**           | Creates the visual mockups, builds the style guide, and ensures a high-quality user experience.       |
| **QA/Tester**          | Develops testing plans, executes tests to find issues, and reports bugs to the development team.      |
| **DevOps Engineer**    | Manages the application's deployment, automates the release pipeline, and maintains the server.       |
| **Product Owner**      | Defines project features, sets priorities, and acts as the voice of the end-user and stakeholders.    |
| **Scrum Master**       | Leads agile ceremonies, helps the team overcome obstacles, and ensures the scrum process is followed. |

## UI Component Patterns
### Planned Components
**1. Navbar**
- Logo
- Search bar
- User navigation
- Responsive menu

 **2. Property Card**
- Property image
- Basic details (price, location, rating)
- Favorite button
- Responsive layout

**3. Footer**
- Site links
- Company information
- Social media links
- Copyright information

# Backend
## Project goals
1. **User Management:** Implement a secure system for user registration, authentication, and profile management.
2. **Property Management:** Develop features for property listing creation, updates, and retrieval.
3. **Booking System:** Create a booking mechanism for users to reserve properties and manage booking details.
4. **Payment Processing:** Integrate a payment system to handle transactions and record payment details.
5. **Review System:** Allow users to leave reviews and ratings for properties.
6. **Data Optimization:** Ensure efficient data retrieval and storage through database optimizations.

## Team Roles
  - **Backend developer**: Responsible for implementing API endpoints, database schemas, and business logic.
  - **Database Administrator**: Manages database design, indexing, and optimizations.
  - **Business analyst**: Analyzes a customer's business processes and translates their needs into detailed technical requirements for the development team.
  - **Product owner**: Owns the product vision and strategy, prioritizes features in the product backlog, and makes key decisions to ensure the final product meets customer requirements and market needs.
  - **Product manager**: Ensures the project is delivered on time and within budget by managing the team, planning work activities, and distributing tasks.
  - **UI/UX designer**: Transforms the product vision into an intuitive and user-friendly design, focusing on creating the best possible user journey and interface to maximize usability and conversion.
  - **Software architect**: Makes high-level technical decisions, designs the overall software architecture, selects the appropriate tools and platforms, and sets coding standards to ensure the product is stable and secure.
  - **Quality assurance engineer**: Verifies that the application performs according to its functional and non-functional requirements, identifying and reporting any defects to ensure overall product quality.
  - **Test automation engineer**: Designs and builds an automated testing system, writing and maintaining scripts that provide continuous feedback on application quality without manual intervention.
  - **DevOps engineer**: Bridges the gap between development and operations teams by building and managing CI/CD pipelines to automate and speed up the software delivery process while maintaining stability.
    
## Technology Stack
- **Django:** A high-level Python web framework used for building the RESTful API.
- **Django REST Framework:** Provides tools for creating and managing RESTful APIs.
- **PostgreSQL:** A powerful relational database used for data storage.
- **GraphQL:** Allows for flexible and efficient querying of data.
- **Celery:** For handling asynchronous tasks such as sending notifications or processing payments.
- **Redis:** Used for caching and session management.
- **Docker:** Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines:** Automated pipelines for testing and deploying code changes.

## Database Design
1. **Users**:
    - A user can own many different Properties.
    - A user can make many bookings as a guest.
    - A user writes many reviews for the bookings they have completed.
    - A user, as a host, receives many reviews from guests.
    - As a host, a user receives many payments from guests.
      
2. **Properties** :
   - A property is owned by one user.
   - A property can be booked many times by different users.
   - A property can get many reviews over time from its various bookings.
   - A property generates many payments for its bookings.
   - A property is booked by many Users(Guests).
3. **Bookings** :
     - A booking is made by exactly one guest (User).
     - A booking is always for exactly one Property.
     - Each booking has one corresponding payment record.
     - A booking can have one review written about it.
     - A booking creates an indirect link between the guest user and the property owner user.
5. **Reviews** :
    - A review is always about a single, specific Booking.
    - A review is given by the user who made the booking.
    - A review gives feedback on a specific property.
    - Review is indirectly linked to the user who owns the property.
    - Review is for a stay that was secured by a specific payment.
5. **Payments** :
   - A payment is made for one booking.
   - Payment secures a reservation at a specific property through booking
   - Payment is linked to one user (the user who paid for the property that was booked).
   - Payment is directed to the user who owns the property.
   - Payment is linked to the start_date and end_date of the duration of stay it covers.
   
  
