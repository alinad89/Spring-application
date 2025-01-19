# README for Culinary Masters Project

## Author
Alina Dimova

## Project Overview
The Culinary Masters project is a multi-layered Spring Boot application developed to manage chefs, recipes, ingredients, and their relationships. The project implements features such as data export, interactive web pages, and database handling. The assignments were broken into weekly tasks, progressively building a complete application.

---

## Domain and Relationships

### Entities
1. **Chef**: Represents a chef entity with attributes such as name, expertise, and an image.
2. **Recipe**: Represents a recipe entity with attributes like name, description, and an associated chef.
3. **Ingredient**: Represents ingredients used in recipes.

### Relationships
- **Many-to-Many**: Chefs can create multiple recipes, and recipes can involve multiple chefs. This relationship is implemented through the `chef_recipe` join table.
- **Many-to-Many**: Recipes can involve multiple ingredients, and ingredients can be used in multiple recipes. This relationship is implemented through the `recipe_ingredients` join table.

---

## Weekly Progress

### Week 2: Layered Architecture
- Refactored the application into a layered architecture:
    - **Presentation Layer**: Contains view logic and controllers.
    - **Business Layer**: Contains service classes and domain entities.
    - **Data Access Layer**: Manages repositories and database interactions.
- Used interfaces for loose coupling and dependency injection to connect layers.
- Converted the application into a Spring Boot application.

### Week 3: Web Application
- Developed a web application with **4 main pages**:
    - **All Chefs**: Displays all chefs in a table. (chef-details page for viewing the concrete information for each chef)
    - **All Recipes**: Displays all recipes in a table. (recipe-details page for viewing the concrete information for each recipe)
    - **Add chef**: Form to add a new chef.
    - **Add recipe**: Form to add a new recipe.
    - **Session History**: View the page visited by the user

- Added a **Navbar** and **Footer** using Thymeleaf fragments.
- Implemented responsive design using Bootstrap.
- Added basic validation for forms.

### Week 5: Responsive Design and Multi-language Support
- Enhanced responsive design with **Bootstrap**:
    - Used **Bootstrap cards** to display entities with attributes and images.
    - Made pages responsive to display in 1, 2, or 4 columns based on screen size.
- Added a **Navbar** and **Footer** using Thymeleaf fragments.
- Implemented **Client-side validation** for form fields.
- Added **Multi-language support** with property files for localization.

### Week 6: Presentation Layer Enhancements
- Developed **ViewModels** for `Chef` and `Recipe` entities.
- Implemented a custom converter for converting strings to `Type` objects.
- Added **Bean Validation** annotations to ViewModels for error handling.
- Created a **Session History** page to log user activity using session scope.

### Week 7: JDBC Repository
- Implemented repositories using **Spring JDBC (JdbcTemplate)** with H2 in-memory database.
- Used `schema.sql` and `data.sql` for database initialization.
- Enabled profiles to switch between JDBC and Java Collections implementation.

### Week 8: Entity Relationships
- Added **Many-to-Many relationships** between Chef and Recipe entities using the `chef_recipe` join table.
- Added **Many-to-Many relationships** between Recipe and Ingredient entities using the `recipe_ingredients` join table.
- Used `JdbcTemplate` to implement and manage relationships.
- Enabled interaction with related entities through clickable lists in the UI.
- Added a delete functionality for entities in tables.

### Week 9: JPA with EntityManager
- Implemented a repository using **EntityManager** for direct control of the persistence context.
- Profiles `dev` and `prod` use this implementation to manage JPA interactions.
- Enhanced relationships using JPA annotations (`@OneToMany`, `@ManyToMany`).
- Provided configuration files for H2 (dev) and PostgreSQL (prod).

### Week 10: Spring Data JPA
- Added a new implementation using **Spring Data JPA** for repository management.
- Profile `jpa` utilizes this implementation, simplifying database interaction using Spring abstractions.
- Extended JPA repository with:
    - **Two method queries**.
    - **4 custom queries`@Query` annotations for Recipes**.
- Added new pages to demonstrate the queries.

### Week 11: Exception Handling
- Added custom exception handling:
    - **Database Error Page** for database-specific issues.
    - **General Error Page** for other errors.
- Implemented a custom exception (`CustomApplicationException`) for the service layer.
- Used `@ControllerAdvice` for global exception handling.

### Week 12: JSON Export
- Added export functionality using **GSON**:
    - Export chefs with their associated recipes.
    - Export recipes and their ingredients.
- Integrated download functionality for the JSON files on the homepage.

---

## Profiles
1. **Development**: Uses H2 in-memory database with JDBC or EntityManager JPA based on profile.
2. **Collections**: Uses in-memory Java Collections for data storage.
3. **JDBC**: Uses H2 in-memory database with JdbcTemplate.
4. **Jpa-Development**: Uses H2 in-memory database with Spring JPA.
5.  **Jpa-production**: Uses PostgreSQL for the database with Spring JPA
5. **Production**: Uses PostgreSQL for the database with EntityManager JPA.

---

## Database Configuration
- **H2 (Dev)**:
    - Name: `assignment1`
    - User: `sa`
    - Password: (empty)
- **PostgreSQL (Prod)**:
    - Name: `assignment1`
    - User: `postgres`
    - Password: `persik89A`

---

## Instructions to Run
1. Clone the repository.
2. Choose a profile (`development`, `collections`, `jdbc`, `jpa-dev`, `jpa-prod`,`dev`,`prod` ) in `application.properties`.
3. Run the project using the Spring Boot command.
4. Access the web application at `http://localhost:8888`.

---

## Completed and Pending Tasks
- **Completed**: All major functionalities and weekly tasks up to Week 12.

---

## Start URL for Web App
- Home Page: (http://localhost:8888)

---

## Notes
- Logs are configured for debug messages in the application properties.
- Not sure if string to type converter works properly
- Hope everything was implemented correctly!
