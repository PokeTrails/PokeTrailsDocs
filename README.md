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
- [R6 - Trello Board Project Management Screenshots](#r6---trello-board-project-management-screenshots)

## 🚀 Deployed Applications

- **Front End:** [https://poketrails.com](https://poketrails.com)
- **Back End:** [https://api.poketrails.com](https://api.poketrails.com)

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

For additional context and visualization, screenshots of the testing processes and results are provided below:

![Development Testing](./docs//images/development_testing.png)

![User Testing](./docs/testing/user_testing.png)

![User Testing Notes](./docs/testing/user_testing_notes.png)

![Cypress Testing](./docs/testing/cypress_testing.png)

### Back-end Testing

(Suraj)

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
- View trainer information easily like player level

#### User settings

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

### Login Process

![Login](./Images/dfd/DFD_Login.PNG)

### Shop Process

![Shop](./Images/dfd/DFD_Shop.PNG)

### Trail Process

![Trail](./Images/dfd/DFD_Trail.PNG)

### Pokémon Interaction Process

![Interactions](./Images/dfd/DFD_Interactions.PNG)

## R3 - Application Architecture Diagram

The PokéTrails application leverages a modern web architecture that includes a front-end built with HTML, CSS, JavaScript, and React, hosted on Netlify. The back-end, hosted on Render, utilises Node.js with Express.js and Mongoose for handling API requests and MongoDB operations. The system integrates with third-party services like PokéAPI to enhance functionality and provide comprehensive data to users.

Below is an overview of the full app architecture:
![Application Architecture Diagram.](./Images/App%20Architect.jpg)

## R4 - User Stories and Personas

In this section, we outline the key user personas and their respective user stories to ensure we cater to their needs and expectations.

### Persona - Pokémon Caretaker

![Caretaker](./Images/user-stories-personas/Persona_Caretaker.png)

### Persona - Pokémon Enthusiast

![Enthusiast](./Images/user-stories-personas/Persona_Enthusiast.png)

### Persona - Pokémon Trainer

![Trainer](./Images/user-stories-personas/Persona_Trainer.png)

### Persona - Pokémon Fan

![Fan](./Images/user-stories-personas/Persona_Fan.png)

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

![Refined User Stories](./Images/user-stories-personas/UserStory_Refinement.png)

## R5 - Mobile, Tablet and Desktop Wireframes

Below are the wireframes that we developed for this application, consisting of mock ups for Mobile, Tablet and Desktop screens. Annotations can be found on the desktop wireframe for each page, depicting each notable element or component and its function/purpose.

These wireframes were developed and created using Figma, the online version can be viewed and accessed [here](https://www.figma.com/design/l4WFNwF8tMJdNZ5tBWap1D/Pok%C3%A9trails?node-id=935169-448&t=SS62FQ7YuaaWgltJ-1).

### Sign Up Page

![Sign Up Page](./Images/wireframes/wf_1_sign_up.png)

### Log In Page

![Log In Page](./Images/wireframes/wf_2_log_in.png)

### Main Page

![Main Page](./Images/wireframes/wf_3_main.png)

### Party Page

![Party Page](./Images/wireframes/wf_4_party.png)

### Trail Menu Page

![Trail Menu Page](./Images/wireframes/wf_5_trails.png)

### Trail Selection Page

![Trail Selection Page](./Images/wireframes/wf_6_trail_selection.png)

### Trail Selection Page Alt

![Trail Page Alt Page](./Images/wireframes/wf_7_trail_selection_alt.png)

### Pokédex Page

![Pokédex Page](./Images/wireframes/wf_8_pokedex.png)

### Store Menu Page

![Store Menu Page](./Images/wireframes/wf_9_store_menu.png)

### Store Purchase Page

![Store Purchase Page](./Images/wireframes/wf_10_store_purchase.png)

### Store Upgrade Page

![Store Upgrade Page](./Images/wireframes/wf_11_store_upgrade.png)

### Store Upgrade Page Alt

![Store Upgrade Alt Page](./Images/wireframes/wf_12_store_upgrade_max.png)

### Store Send Pokémon Page

![Store Send Pokémon Page](./Images/wireframes/wf_13_store_send.png)

### Store Send Pokémon Page Alt

![Store Send Pokémon Alt Page](./Images/wireframes/wf_14_store_send_alt.png)

### User Settings Page

![User Settings Page](./Images/wireframes/wf_15_user_settings.png)

## R6 - Trello Board Project Management Screenshots (Part A)

We initially used Miro as our way brainstorming for the project and then moved onto Trello once the idea had been initialised and the features were sent in stone. This allowed for a Trello board that was a lot more stable from day 1 that didn't need many improvisations. Throughout the use of the Trello board we used many inbuilt features that allowed us to keep on track and progress at a steady pace, the features we used are:

- Due Dates
- Assigning Tasks
- Checklists
- Priorities

### Miro Board

![Miro1](./Images/trello/miro_1.png)
![Miro2](./Images/trello/miro_2.png)

### 4/07

![4th](./Images/trello/4th.png)

### 5/07

![5th](./Images/trello/5th.png)

### 6/07

![6th](./Images/trello/6th.png)

### 7/07

![7th](./Images/trello/7th.png)

### 8/07

![8th](./Images/trello/8th.png)

### 9/07

![9th](./Images/trello/9th.png)

### 13/07

![13th](./Images/trello/13th.png)

### 16/07

![16th](./Images/trello/16th.png)

### 19/07

![19th](./Images/trello/19th.png)


## Trello Project Management (Part B)

Much like our part A we used Trello as our main way of delgating tasks, tracking progress and setting due dates. We made extensive use of trello and its features to make the planning process simple and streamlined. On each Saturday we would update the trello board for new tasks to do during the coming week. 

Meeting had scheduled days on Saturday, Tuesday and Monday with meetings throughout the weeks if we had questions for each other or needed help. Our main way of organising these meetings were through discord, in the discord we then had a stored google meet link where we had conducted all our meetings. Using the discord server we had made was our main way of communicating and ideas or issue we had came accross in the development process.

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
