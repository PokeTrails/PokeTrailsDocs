![PokeTrails App Logo](./docs/app_logo.png)

# PokéTrailsDocs

Official Documentation for the PokéTrails Application, developed by Rahal Abeyrathna, Suraj Shrestha, Talie Hodge.

## Table of Contents

- [R1 - Application Purpose and Features](#r1---application-purpose-and-features)
  - [Purpose](#purpose)
  - [Features](#features)
  - [Target Audience](#target-audience)
  - [Tech Stack](#tech-stack)
- [R2 - Dataflow Diagrams](#r2---dataflow-diagrams)
- [R3 - Application Architecture Diagram](#r3---application-architecture-diagram)
- [R4 - User Stories and Personas](#r4---user-stories-and-personas)
  - [Persona - Pokémon Caretaker](#persona---pokémon-caretaker)
  - [Persona - Pokémon Enthusiast](#persona---pokémon-enthusiast)
  - [Persona - Pokémon Trainer](#persona---pokémon-trainer)
  - [Persona - Pokémon Fan](#persona---pokémon-fan)
  - [User Stories](#user-stories)
- [R5 - Mobile, Tablet and Desktop Wireframes](#r5---mobile-tablet-and-desktop-wireframes)
  - [Sign Up Page](#sign-up-page)
  - [Log In Page](#log-in-page)
  - [Main Page](#main-page)
  - [Party Page](#party-page)
  - [Trail Menu Page](#trail-menu-page)
  - [Trail Selection Page](#trail-selection-page)
  - [Trail Selection Page Alt](#trail-selection-page-alt)
  - [Pokédex Page](#pokédex-page)
  - [Store Menu Page](#store-menu-page)
  - [Store Purchase Page](#store-purchase-page)
  - [Store Upgrade Page](#store-upgrade-page)
  - [Store Upgrade Page Alt](#store-upgrade-page-alt)
  - [Store Send Pokémon Page](#store-send-pokémon-page)
  - [Store Send Pokémon Page Alt](#store-send-pokémon-page-alt)
  - [User Settings Page](#user-settings-page)
- [R6 - Trello Board Project Management Screenshots (Part A)](#r6---trello-board-project-management-screenshots-part-a)

## 🚀 Deployed Applications

- **Front End Deployed App Site:** [https://poketrails.com](https://poketrails.com)
- **Front End Development Site:** [https://dev.poketrails.com](https://dev.poketrails.com)
- **Back End API:** [https://api.poketrails.com](https://api.poketrails.com)

## 📂 Repositories

- **Documentation:** [PokeTrailsDocs](https://github.com/PokeTrails/PokeTrailsDocs)
- **Client:** [poketrails-frontend](https://github.com/PokeTrails/poketrails-frontend)
- **Server:** [poketrails-backend](https://github.com/PokeTrails/poketrails-backend)

## 📄 Documentation

## Frontend Install Instrcutions

1. **Clone the Front-End Repository**:
   - Use the following command to clone the repository:

     ```bash
     git clone git@github.com:PokeTrails/poketrails-frontend.git
     ```

2. **Install Dependencies**:
   - Navigate to the project directory and install the required npm dependencies:

     ```bash
     npm install
     ```

3. **Start the Application**:
   - Launch the application with the following command:

     ```bash
     npm start
     ```

4. **Access the Application**:
   - Open your browser and go to [localhost:5173](http://localhost:5173/)

5. **Verify Backend Server Is Running**:
   - Ensure the backend server is running on port 8080 using the instructions provided below.

## Backend Install Instructions

1. **Create a `.env` File**:
   - In the root directory of the project, create a `.env` file and add the following configuration:

     ```sh
     PORT=8080
     DATABASE_URL="YOUR URL HERE"
     JWT_KEY="YOUR JWT KEY HERE"
     ```

2. **Start MongoDB (WSL Users)**:
   - If you are using Windows Subsystem for Linux (WSL), start MongoDB with:

     ```sh
     sudo systemctl start mongod
     ```

3. **Start the Server in Development Mode**:
   - Install the packages needed for the app

     ```sh
     npm run dev
     ```

   - Use the following command to start the server:

     ```sh
     npm run dev
     ```

4. **Seed Data to the Database**:
   - Populate the database with initial data by running:

     ```sh
     npm run seed
     ```

5. **Login Details**:
   - For user login, use the following credentials:

     ```sh
     USERNAME: user3
     PASSWORD: user3
     ```

## Endpoints

### Authentication

| **Operation** | **URL**                | **Method** | **Body**                                   | **Access**           |
|---------------|------------------------|------------|--------------------------------------------|----------------------|
| Login          | `/login`                | POST       | `{"username": "abc", "password": "abc"}`   | Public               |

### Pokémon

| **Operation**                       | **URL**                                | **Method** | **Body**                      | **Access**           |
|-------------------------------------|----------------------------------------|------------|-------------------------------|----------------------|
| Create a New Pokémon                | `/pokemon`                             | POST       | -                             | Protected (JWT)      |
| Get All Pokémon                     | `/pokemon`                             | GET        | -                             | Protected (JWT)      |
| Get All Donated Pokémon             | `/pokemon/donated`                     | GET        | -                             | Protected (JWT)      |
| Get Pokémon by ID                   | `/pokemon/:pokemonID`                  | GET        | -                             | Protected (JWT)      |
| Set/Edit Pokémon Nickname           | `/pokemon/nickname/:pokemonID`         | PATCH      | `{"nickname": "<NewNickname>"}` | Protected (JWT)      |
| Hatch Pokémon                       | `/pokemon/hatch/:pokemonID`            | PATCH      | -                             | Protected (JWT)      |
| Donate Pokémon                      | `/pokemon/donate/:pokemonID`           | PATCH      | -                             | Protected (JWT)      |
| View Donation Reward                | `/pokemon/donate/reward/:pokemonID`    | GET        | -                             | Protected (JWT)      |
| Talk with Pokémon                   | `/pokemon/talk/:pokemonID`             | PATCH      | -                             | Protected (JWT)      |
| Play with Pokémon                   | `/pokemon/play/:pokemonID`             | PATCH      | -                             | Protected (JWT)      |
| Feed Pokémon                        | `/pokemon/feed/:pokemonID`             | PATCH      | -                             | Protected (JWT)      |
| Evolve Pokémon                      | `/pokemon/evolve/:pokemonID`           | PATCH      | -                             | Protected (JWT)      |

### Pokedex

| **Operation**       | **URL**            | **Method** | **Body** | **Access**           |
|---------------------|--------------------|------------|----------|----------------------|
| Get Pokedex Data    | `/pokedex`         | GET        | -        | Protected (JWT)      |

### Party

| **Operation**                      | **URL**           | **Method** | **Body** | **Access**           |
|------------------------------------|-------------------|------------|----------|----------------------|
| Get Party Details                  | `/party`          | GET        | -        | Protected (JWT)      |

### Store

| **Operation**           | **URL**                   | **Method** | **Body** | **Access**           |
|-------------------------|---------------------------|------------|----------|----------------------|
| Get All Items           | `/store`                  | GET        | -        | Protected (JWT)      |
| View Item by ID         | `/store/view/:id`         | GET        | -        | Protected (JWT)      |
| Buy Item by ID          | `/store/buy/:id`          | PATCH      | -        | Protected (JWT)      |

### User

| **Operation**         | **URL**                 | **Method** | **Body**                                                       | **Access**           |
|-----------------------|-------------------------|------------|----------------------------------------------------------------|----------------------|
| Create a New User     | `/user/signup`          | POST       | `{"username": "James", "trainerName": "James3", "sprite": "boySprite", "password": "password"}` | Public               |
| Login a User          | `/user/login`           | POST       | `{"username": "James", "password": "password"}`               | Public               |
| Delete a User         | `/user/delete/:userID`  | DELETE     | -                                                              | Protected (JWT)      |
| Edit a User           | `/user/patch/:userID`   | PATCH      | -                                                              | Protected (JWT)      |
| Find a User by ID     | `/user/find/:userID`    | GET        | -                                                              | Protected (JWT)      |
| Find All Users        | `/user`                 | GET        | -                                                              | Protected (JWT)      |

### Trail

| **Operation**         | **URL**                          | **Method** | **Body**                                             | **Access**           |
|-----------------------|----------------------------------|------------|------------------------------------------------------|----------------------|
| Send on Trail         | `/trail/simulate`                 | POST       | `{"title": "Wild Trail", "pokemonId": "12123123aseasdasda"}` | Protected (JWT)      |
| Finish Trail          | `/trail/finish`                  | POST       | `{"pokemonId": "12123123aseasdasda"}`                | Protected (JWT)      |
| Find a Trail by Title | `/trail/:trailtitle` (e.g., `wettrail`) | GET        | -                                                    | -                    |
| Get All Trails        | `/trail/`                        | GET        | -                                                    | -                    |
| Delete a Trail by Title | `/trail/:trailtitle` (e.g., `wettrail`) | DELETE     | -                                                    | -                    |
| Patch a Trail by Title | `/trail/:trailtitle` (e.g., `wettrail`) | PATCH      | Any fields present on Trail Model (e.g., `{"length": "12030"}`) | -                    |

## Libaries Used

### Front-end

- **`react` (v18.3.1)**: The core library for building user interfaces. React's component-based architecture allows for the creation of reusable UI components, ensuring a modular and maintainable codebase.

- **`react-dom` (v18.3.1)**: Provides DOM-specific methods that are used by React to render components into the DOM. This is essential for managing updates to the UI.

- **`react-router-dom` (v6.25.1)**: Facilitates routing and navigation in the application. It allows the creation of a dynamic, single-page application with client-side routing capabilities.

### Styling and UI

- **`@mui/material` (v5.16.4)**: A popular React UI framework that provides a comprehensive set of components and styles based on Material Design principles. This library is used for building a responsive and visually appealing user interface.

- **`@mui/icons-material` (v5.16.4)**: Includes a set of Material Design icons that can be used in the application to enhance the visual representation and user interaction.

- **`@emotion/react` (v11.13.0) and `@emotion/styled` (v11.13.0)**: Used for writing CSS styles with JavaScript. Emotion provides a flexible and efficient way to style components in React, with support for dynamic styling and theming.

- **`@fontsource/roboto` (v5.0.13) and `@fontsource/saira` (v5.0.28)**: Custom font loading library to include Roboto and Saira fonts in the application, ensuring a consistent and modern typography. Roboto is used as a backup font, Saira is used as the main font in the application.

### Development and Build Tools

- **`vite` (v5.3.4)**: A fast and modern build tool that provides an optimized development experience with features such as hot module replacement (HMR) and efficient bundling.

- **`@vitejs/plugin-react` (v4.3.1)**: A Vite plugin that provides React-specific features such as fast refresh and automatic JSX transformation, optimizing the development workflow.

### State Management and Data Handling

- **`axios` (v1.7.2)**: A promise-based HTTP client for making API requests. It simplifies data fetching and error handling, making it easier to interact with backend services.

- **`dotenv` (v16.4.5)**: Loads environment variables from a `.env` file into `process.env`, allowing for configuration and secrets management outside of the codebase.

### Testing

- **`cypress` (v13.13.2)**: An end-to-end testing framework that provides a reliable way to write and run tests for the application's UI, ensuring that user interactions and workflows function as expected.

- **`mocha` (v10.7.3)**: A test framework for writing unit and integration tests. Mocha provides a flexible and extensible testing environment.

- **`mochawesome` (v7.1.3) and `mochawesome-merge` (v4.3.0)**: Reporters for Mocha that generate detailed and visually appealing test reports, which can be used to analyze test results and coverage.

### Additional Features

- **`howler` (v2.2.4)**: A library for managing audio in the application, providing support for features like sound playback, control, and customization. Used to play Pokémon cry sounds.

- **`react-confetti` (v6.1.0)**: A lightweight React component for rendering confetti animations, adding visual effects to celebrate events or interactions in the application. Used in the Pokémon hatching pop up to add a bit more style and interaction for the user.

### Back-end

- **bcryptjs**: Used for securing user passwords by hashing them before storing them in the database. It also provides a method to verify hashed passwords against plain text inputs, enhancing application security by ensuring safe user authentication.

- **cors**: Manages and controls access to resources from different domains. It allows or restricts requests from external origins, ensuring that only authorized domains can interact with the API, thus preventing unauthorized access while enabling legitimate cross-origin requests.

- **dotenv**: Facilitates secure management of environment variables by loading configurations from a `.env` file into `process.env`. This keeps sensitive information like API keys and database credentials out of the source code, improving security and making it easier to manage different environments (development, testing, production).

- **express**: A web framework used to build server-side logic and manage HTTP requests and responses. It provides robust features for routing, middleware support, and integration with various templating engines, simplifying the definition of routes and processing of requests.

- **jsonwebtoken**: Manages user authentication by generating a token that encodes user information (e.g., user ID) using a secret key. This token is sent to the client and used for authenticating subsequent requests, ensuring secure access by verifying the token's authenticity.

- **mongoose**: An Object Data Modeling (ODM) library for interacting with MongoDB. It offers a schema-based solution to model application data, allowing easy creation, reading, updating, and deletion of database records. Mongoose also provides data validation, middleware support, and complex querying capabilities.

- **nodemon**: A development tool that automatically monitors project files for changes and restarts the server when code changes are detected. This ensures that the application reflects the latest updates without needing manual server restarts.

- **jest**: A testing framework designed to ensure code reliability and correctness. It offers a suite of utilities for writing unit and integration tests, verifying that the application functions as expected.

- **supertest**: An HTTP assertion library used for testing API endpoints. It simulates HTTP requests to Express routes, allowing verification of the API's behavior in different scenarios and ensuring that endpoints operate correctly.

## Testing

### Front-end Testing

Front-end testing was conducted through multiple stages to ensure the application met our quality standards and functioned as intended across various environments.

#### Local Development Testing

Each feature was developed locally and thoroughly tested in a local development environment. This initial testing phase involved verifying the functionality of individual functions, components, and pages.

#### Public Development Testing

Once features were deemed stable in the local environment, they were pushed to a development branch. Here, testing was conducted using a public development database to simulate real-world usage and ensure compatibility with production settings. This phase also included testing on different devices and screen sizes, such as tablets and smartphones, to ensure the application’s accessibility and responsiveness.

#### Production User Testing

Features were then tested in a staging environment that closely mirrored the production setup. This phase involved gathering feedback from real users to validate the usability and functionality of the application in a near-production environment.

#### Automated Testing with Cypress

Automated tests were run using Cypress to validate the overall functionality and performance of the application. Cypress testing included various scenarios to ensure comprehensive coverage and identify any potential issues early in the development process.

Detailed results from user testing, including feedback and observations related to the login and sign-up workflows, are documented in a spreadsheet available in the GitHub repository. Additionally, a screenshot capturing further notes from the user testing is also provided in the same directory.

The results of the automated testing conducted with Cypress can be found in the Output.html file.

For additional context and visualization, screenshots of the testing processes and results are provided below, including commits and pushes to the dev branch:

![Development Testing](./docs/testing/development_testing.png)

![User Testing](./docs/testing/user_testing.png)

![User Testing Notes](./docs/testing/user_testing_notes.png)

![Cypress Testing](./docs/testing/cypress_testing.png)

![Dev Branch](./docs/testing/dev_branch.png)

### Back-end Testing

## Overview

Backend testing was carried out meticulously to ensure the robustness, security, and accuracy of API endpoints as outlined in the project specifications. The testing process was comprehensive, covering all aspects from data validation to performance under load, and ensuring secure access through proper authentication mechanisms. The testing was divided into several phases, including local, staging, and production environments, each designed to thoroughly validate each feature under various conditions and scenarios, from typical use cases to potential edge cases. This approach ensured that the API was not only functional but also resilient and scalable.

### Local Development Testing

Initial testing of the backend API routes was conducted in a local environment using Postman. Each route was subjected to detailed scrutiny, ensuring correct HTTP status codes, response bodies, and JWT token authentication where applicable. The testing process involved various scenarios, including valid and invalid inputs, boundary conditions, and error responses. Special attention was given to edge cases, such as handling of malformed requests, rate limiting, and ensuring proper data validation rules were enforced. Logging and error reporting mechanisms were also verified to ensure that they provided sufficient information for debugging and monitoring. This phase focused on verifying the basic functionality and ensuring that the API could handle different input cases reliably, preparing it for more rigorous testing in later stages.

### Production Environment Testing

Final testing was conducted in the production environment using the live API. This testing phase was critical to validate that all endpoints functioned as expected in a real-world setting with actual user data. In addition to functional testing, this phase included performance and stress testing to evaluate the API's behavior under heavy load, ensuring that it could scale appropriately without degradation of service. Security testing was also a key focus, with JWT authentication being rigorously tested for vulnerabilities such as token expiration, revocation handling, and protection against unauthorized access. The overall API performance, including response times, was measured to ensure it met the required standards. Monitoring tools were employed to track the API's health and performance metrics, ensuring that any issues could be quickly identified and addressed.

### Summary

The backend testing process was comprehensive and covered all possible scenarios, from normal operation to potential edge cases. Each endpoint was tested rigorously across different environments, ensuring not only correct functionality but also security, scalability, and resilience. Automated tests were implemented to facilitate continuous integration and catch regressions early in the development process. All tests passed successfully, and the API was deemed ready for production deployment. The detailed logs and results from the testing phases are stored in the project repository for further reference, providing a clear audit trail and insights for future development and maintenance.

![Server Testing](./docs/testing/ServerTesting.png)

## R1 - Application Purpose and Features

### Purpose

This web application/game aims to create an enjoyable and engaging experience for both long-time Pokémon fans and newcomers. It provides a fun and casual platform where users can learn about different Pokémon through interactive features and captivating visuals. By exploring various Pokémon species, users can deepen their knowledge and appreciation of the Pokémon universe. The app/game also includes challenges to make the learning process entertaining and rewarding, fostering a community of enthusiastic.

### Features

Below are the features that we've planned to implement in this application, including any optional features that we will try fit in if we have enough time.

#### Party Management

- Hatch eggs to receive new Pokémon
- Play, feed and talk to your Pokémon
  - Hear the Pokémon's cry when interacting with it
  - Pokémon has animations and reacts according to interaction user selects
    - *Note this has been removed from the deployed application, all Pokémon instead play a cry on succcessful interaction*
- Evolve Pokémon after raising happiness
- Rename Pokémon with nicknames

#### Trails

- Send Pokémon on specific trails to receive items, egg vouchers and happiness
- View countdown of how long it takes for the Pokémon to complete the trail
- View a log of what the Pokémon is doing on the trail

#### Store

- Purchase in-game buffs to improve progression speed
  - Happiness buffs, increased chance to get egg vouchers etc
- Purchase Eggs using egg vouchers to discover new Pokémon
- Send Pokémon to the Professor to receive currency to use in the store and to fill out the Pokédex
- Talk with the Professor who has new quotes depending on item or Pokémon selected

#### Pokédex

- View Pokémon you have discovered and sent to the Pokémon
- View Pokédex entries with descriptions with Pokémon you have sent to the Professor
- View shiny Pokémon if you have discovered any
- Check overall progress of how far the user has filled out the Pokédex
  - *Note this has been removed from the deployed application, only Pokémon that the user has hatched or donated are shown in the Pokédex*
- View trainer information easily like player level
  - *Note this has been removed from the deployed application and cannot be viewed in the Pokédex*

#### User settings

*Note this feature has been removed from the deployed application entirely due to time contraints and is replaced by a temporary placeholder page until it is completed.*

- Customisation options for user engagement and interaction
  - Custom profile icons and trainer sprites which can be unlocked in store
- View trainer stats and information
- Delete user account if desired

### Target Audience

As Pokémon is a product that is popular with all ages and demographics our target audience will tend to mimic that. The age range that that online Pokémon fans tend to be is somewhere between 20-29. As this product is an online application we will be catering to that demographic. While Pokémon fans will be our main target, the game has Gacha mechanics which allow us to appeal to the gacha game player demographic as well

### Tech Stack

- **Front End**
  - HTML
  - CSS
  - Javascript
  - React
  - Netlify
  - Tech Domains
- **Back End**
  - Javascript
  - NodeJS
  - ExpressJS
  - Mongoose
  - MongoDB
  - Render
- **Third Party Services**
  - PokéAPI

## R2 - Dataflow Diagrams

The below diagrams depict how data travels, and is stored, throughout various processes present within the application.

**PART B CHANGES:** The user model now includes the shop, as shop items are directly linked to the player. Initially, the trails and trailLog were going to be separate entities, with trailLog acting as a joiner document between Pokémon and the trails. However, the trailLog has now been integrated into the Pokémon schema. The trails themselves have been simplified to only track which Pokémon are present on each trail.

### Login Process

![Login](./docs/images/dfd/DFD_Login.PNG)

### Shop Process

![Shop](./docs/images/dfd/DFD_Shop.PNG)

### Trail Process

![Trail](./docs/images/dfd/DFD_Trail.PNG)

### Pokémon Interaction Process

![Interactions](./docs/images/dfd/DFD_Interactions.PNG)

## R3 - Application Architecture Diagram

The PokéTrails application leverages a modern web architecture that includes a front-end built with HTML, CSS, JavaScript, and React, hosted on Netlify. The back-end, hosted on Render, utilises Node.js with Express.js and Mongoose for handling API requests and MongoDB operations. The system integrates with third-party services like PokéAPI to enhance functionality and provide comprehensive data to users.

Below is an overview of the full app architecture:
![Application Architecture Diagram.](./docs/images/App%20Architect.jpg)

## R4 - User Stories and Personas

In this section, we outline the key user personas and their respective user stories to ensure we cater to their needs and expectations.

### Persona - Pokémon Caretaker

![Caretaker](./docs/images/user-stories-personas/Persona_Caretaker.png)

### Persona - Pokémon Enthusiast

![Enthusiast](./docs/images/user-stories-personas/Persona_Enthusiast.png)

### Persona - Pokémon Trainer

![Trainer](./docs/images/user-stories-personas/Persona_Trainer.png)

### Persona - Pokémon Fan

![Fan](./docs/images/user-stories-personas/Persona_Fan.png)

### User Stories

Below are the detailed user stories for each persona, outlining their needs, motivations, and the desired outcomes. Each story includes specific acceptance criteria to ensure that the implementation meets the user's expectations and provides a satisfying experience. By addressing these user stories, we aim to create a comprehensive and engaging application that resonates with our diverse user base.

```md
As a: Pokémon Caretaker
I want to: play, talk, feed, evolve Pokémon,
So that: I can build a strong bond with my Pokémon, help it grow and evolve
```

**Acceptance Criteria**:

- I can access an interactive screen where I can view stats and interact with my Pokémon.
- Action provides immediate feedback on how it affects my Pokémon's happiness.
- I can play with my Pokémon to increase its happiness.
- I can initiate conversations with my Pokémon and the Pokémon responds with a cry.
- I can feed my Pokémon to increase its happiness.
- I can evolve my Pokémon when the happiness criteria is met.

---

```md
As a: Pokémon Trainer
I want to: send it on trails, collect valuable items.
So that: I can accelerate their evolution.
```

**Acceptance Criteria**:

- I can send my Pokémon on various trails to find items and gain experience.
- Each trail has a different set of potential rewards.
- A timer or progress indicator shows the trail's completion.

---

```md
As a: Pokémon Enthusiast
I want to: Buy Items from Professor's Store and register Pokémon to the Pokédex,:
So that: I can enhance my Pokémon with applied buffs/enhancements and keep track of my Pokémon collection
```

**Acceptance Criteria**:

- I can visit the professor's store to buy items using in-game currency.
- The store updates its inventory regularly.
- The store interface shows available items, their prices, and descriptions.
- I can purchase items and see the updated inventory and currency balance.

---

```md
As a: Pokémon Fan
I want to: receive notifications and alerts for important updates
So that: I can stay informed and engage with the app regularly.
```

**Acceptance Criteria**:

- I can receive in app alerts when my Pokémon returns from a trail, evolves, or needs attention.

---
***This feature was removed from the application due to time constraints and other moving parts of the application.***

### User Stories Refinement

Below is an overview of the refinement to the user stories. The user stories were first drafted based on the user personas and further refined after a team discussions and user feedback. The updates include more detailed acceptance criteria and clearer descriptions to better align with user needs and application functionality.

#### What Has Changed

#### Added Acceptance Criteria

- Each user story now includes specific acceptance criteria to clearly define when a user story is complete and meets the requirements.

#### Refined User Stories

- User stories have been rephrased for clarity and better alignment with the intended functionality and user personas.

#### Additional Details for User Interactions

- More details have been provided on how users will interact with the application, ensuring a better understanding of the user experience.

#### Enhanced Specificity

- The user stories now contain more specific information regarding the features and functionalities, reducing ambiguity and aiding in more precise implementation.

#### Change Log

![Refined User Stories](./docs/images/user-stories-personas/UserStory_Refinement.png)

## R5 - Mobile, Tablet and Desktop Wireframes

Below are the wireframes that we developed for this application, consisting of mock ups for Mobile, Tablet and Desktop screens. Annotations can be found on the desktop wireframe for each page, depicting each notable element or component and its function/purpose.

These wireframes were developed and created using Figma, the online version can be viewed and accessed [here](https://www.figma.com/design/l4WFNwF8tMJdNZ5tBWap1D/Pok%C3%A9trails?node-id=935169-448&t=SS62FQ7YuaaWgltJ-1).

### Note about Wireframes

Some wireframes were changed during development of the application, these have been noted in the wireframes and referenced in the screenshots of the wireframes, as well as of the deployed application further down.

For example, the Navbar layout has been changed from the wireframes slightly, with different styling and mobile layout.

### Sign Up Page

![Sign Up Page](./docs/images/wireframes/wf_1_sign_up.png)

*Trainer sprite sizes have been changed and image for male trainer has been updated. Form input labels have also been removed.*

### Log In Page

![Log In Page](./docs/images/wireframes/wf_2_log_in.png)

*Removed labels from form inputs.*

### Main Page

![Main Page](./docs/images/wireframes/wf_3_main.png)

### Party Page

![Party Page](./docs/images/wireframes/wf_4_party.png)

*Layout has been changed to be more in line with the other pages, placing the party component on the bottom and having the other main components share the space on the top.*

### Trail Menu Page

![Trail Menu Page](./docs/images/wireframes/wf_5_trails.png)

*Extra trail option has been added called 'Wet Trail' to give even amount of trails and increase options for the users.*

### Trail Selection Page

![Trail Selection Page](./docs/images/wireframes/wf_6_trail_selection.png)

*Components have been split into 2 sections, Party is not nested directly into the main trail data section. Eggs are not greyed out as user can select them, is applies to other pages with party component such as store.*

### Trail Selection Page Alt

![Trail Page Alt Page](./docs/images/wireframes/wf_7_trail_selection_alt.png)

### Pokédex Page

![Pokédex Page](./docs/images/wireframes/wf_8_pokedex.png)

*Background not been added due to time restraints, and layout has entirely been changed with a new design, while keeping the core functionality the same.*

### Store Menu Page

![Store Menu Page](./docs/images/wireframes/wf_9_store_menu.png)

*Icons used for the menu options have been changed to be more accurate and scale better with the application.*

### Store Purchase Page

![Store Purchase Page](./docs/images/wireframes/wf_10_store_purchase.png)

*Amount of slots the user can purchase from has been reduced as not many items were implemented in backend. Also added eggs to be along side items, as eggs have been re-purposed to be purchasable infinitely as long as the user has enough vouchers. Professor Oak has been removed entirely due to not being necessary and not adding value to page. Buttons and other text elements have been centered and moved around to make use of new space.*

### Store Upgrade Page

![Store Upgrade Page](./docs/images/wireframes/wf_11_store_upgrade.png)

### Store Upgrade Page Alt

![Store Upgrade Alt Page](./docs/images/wireframes/wf_12_store_upgrade_max.png)

### Store Send Pokémon Page

![Store Send Pokémon Page](./docs/images/wireframes/wf_13_store_send.png)

*Professor Oak is no longer shown, and component has been renamed to 'Professor Analysis'. The Pokémon happiness has also been moved to below the Pokémon to keep it using the same component as in the Party page and Trail pages. Total trail time has been removed from the application.*

### Store Send Pokémon Page Alt

![Store Send Pokémon Alt Page](./docs/images/wireframes/wf_14_store_send_alt.png)

### User Settings Page

![User Settings Page](./docs/images/wireframes/wf_15_user_settings.png)

*Page has been completely removed from deployed application due to time restraints. Decided to focus on getting main features and gameplay loop of application live so the user settings page has been replaced with a placeholder at time of submission.*

### Deployed Application Screenshots

#### Main Menu

![Main Menu](./docs/screenshots/Main%20Menu.png)

#### Login

![Login](./docs/screenshots/Login.png)

#### Sign Up

![Sign Up](./docs/screenshots/SignUp.png)

#### Store Menu

![Store Menu](./docs/screenshots/Store%20Menu.png)

#### Store Donate Pokémon

![Store Donate Pokemon](./docs/screenshots/Store%20Donate%20Pokemon.png)

#### Store Item Upgrade

![Store Item Upgrade](./docs/screenshots/Store%20Item%20Upgrade.png)

#### Trails Menu

![Trails Menu](./docs/screenshots/Trails%20Menu.png)

#### Trails Pokémon Return

![Trails Pokémon Return](./docs/screenshots/Trails%20Pokemon%20Return.png)

#### Rocky Trails

![Rocky Trails](./docs/screenshots/Rocky%20Trails.png)

#### Frosty Trails

![Frosty Trails](./docs/screenshots/Frosty%20Trails.png)

#### Wet Trails

![Wet Trails](./docs/screenshots/Wet%20Trails.png)

#### Wild Trails

![Wild Trails](./docs/screenshots/Wild%20Trails.png)

#### Party

![Party](./docs/screenshots/Party.png)

#### Pokedex

![Pokedex](./docs/screenshots/Pokedex.png)

#### Donation Reward

![Donation Reward](./docs/screenshots/Donation%20Reward.png)

## R6 - Trello Board Project Management Screenshots (Part A)

We initially used Miro as our way brainstorming for the project and then moved onto Trello once the idea had been initialised and the features were sent in stone. This allowed for a Trello board that was a lot more stable from day 1 that didn't need many improvisations. Throughout the use of the Trello board we used many inbuilt features that allowed us to keep on track and progress at a steady pace, the features we used are:

- Due Dates
- Assigning Tasks
- Checklists
- Priorities

### Miro Board

![Miro1](./docs/images/trello/miro_1.png)
![Miro2](./docs/images/trello/miro_2.png)

### 4/07

![4th](./docs/images/trello/4th.png)

### 5/07

![5th](./docs/images/trello/5th.png)

### 6/07

![6th](./docs/images/trello/6th.png)

### 7/07

![7th](./docs/images/trello/7th.png)

### 8/07

![8th](./docs/images/trello/8th.png)

### 9/07

![9th](./docs/images/trello/9th.png)

### 13/07

![13th](./docs/images/trello/13th.png)

### 16/07

![16th](./docs/images/trello/16th.png)

### 19/07

![19th](./docs/images/trello/19th.png)

## Trello Project Management (Part B)

Much like our Part A, we utilized Trello as our primary tool for delegating tasks, tracking progress, and setting due dates. Trello's intuitive interface allowed us to effectively organize our workflow and ensure that every team member was aware of their responsibilities. We made extensive use of Trello’s features, such as labels, checklists, and due dates, to streamline the planning process and keep everything on track. On each Saturday, we would review and update the Trello board with new tasks and priorities for the upcoming week, ensuring that everyone was aligned with the project's goals and deadlines.

We decided to split the project into back-end and front-end development, and delegated our tasks and deliverables according to each members strengths and weaknesses. As a result, Rahal was given the front-end to work on as he had more experience working with frameworks such as Material UI which would help him get the website up and running faster, and because he created the wireframes and so would be most comfortable designing the pages. Suraj and Talie were then given back-end to work on, as they were much more comfortable and familiar with MongoDB and working with databases. This led us to complete our tasks and goals in a timely fashion which may not have been possible if we did not take these factors into account.

To complement our use of Trello, we scheduled regular meetings on Saturdays, Tuesdays, and Mondays to discuss progress, address any blockers, and plan the next steps. These meetings provided a structured opportunity to collaborate, share updates, and ensure that the project was progressing smoothly. In addition to our scheduled meetings, we remained flexible and arranged ad hoc meetings throughout the week whenever we encountered questions, needed assistance, or had new ideas to discuss. Whenever we ran into any road bumps or issues with our progress, we would make it clear here to realign ourselves and organise how we would plan our tasks out for that given week. We would also re-assign tasks if needed so ensure we were steadily making progress.

Our primary communication tool was Discord, where we created a dedicated server for the project. This server served as the central hub for all project related discussions, file sharing, and meeting coordination. Within the Discord server, we stored a Google Meet link, which we used for all our virtual meetings. This setup allowed us to quickly jump into meetings and collaborate effectively, regardless of where team members were located. The combination of Trello for task management and Discord for communication created a seamless workflow.

When reviewing the Trello board, you'll notice that each card is marked with the first initial of the team member responsible for that task, making it clear who is accountable for its completion. We've utilized color coded labels to convey essential information about each task.

- Priority levels are indicated by:
  - Red for high priority,
  - Orange for medium priority, and
  - Dark Green for low priority.
  
- Task type is identified by:
  - Light Green for front-end work, and
  - Dark Blue for back-end tasks.

- Feature classification is denoted by:
  - Purple for core functionality, and
  - Blue for optional features.

This system allowed us to easily manage and prioritize tasks, ensuring that everyone was on the same page and that the most critical work received the attention it needed.

### [Link to trello board](https://trello.com/b/sKn4uEWQ/t3a2-fullstack-app-partb)

## Screenshots of Trello Board

### 21/07

![21/07 Screenshot](./docs/trello/21-07.png)

### 24/07

![24/07 Screenshot](./docs/trello/24-07.png)

### 27/07

![27/07 Screenshot](./docs/trello/27-07.png)

### 30/07

![30/07 Screenshot](./docs/trello/30-07.png)

### 01/08

![01/08 Screenshot](./docs/trello/01-08.png)

### 06/08

![06/08 Screenshot](./docs/trello/06-08.png)

### 11/08

![11/08 Screenshot](./docs/trello/11-08.png)
