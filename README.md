# PokéTrailsDocs

Official Documentation for the PokéTrails Application.

Developed by Rahal Abeyrathna, Suraj Shrestha, Talie Hodge.

## Table of Contents

- [R1 - Application Purpose and Features](#r1---description-of-your-website)
  - [Purpose](#purpose)
  - [Features](#features)
  - [Target Audience](#target-audience)
  - [Tech Stack](#tech-stack)
- [R2 - Dataflow Diagrams](#r2---dataflow-diagrams)
- [R3 - Application Architecture Diagram](#r1---description-of-your-website)
- [R4 - User Stories and Personas](#r4---user-stories-and-personas)
  - [Persona - Pokémon Caretaker](#persona---pokémon-caretaker)
  - [Persona - Pokémon Enthusiast](#persona---pokémon-enthusiast)
  - [Persona - Pokémon Trainer](#persona---pokémon-trainer)
  - [Persona - Pokémon Fan](#persona---pokémon-fan)
  - [User Stories](#user-stories)
- [R5 -  Mobile, Tablet and Desktop Wireframes](#r5---mobile-tablet-and-desktop-wireframes)
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

## R1 - Description of your Website

### Purpose

The app/game aims to create an enjoyable and engaging experience for both long-time Pokémon fans and newcomers. It provides a fun and casual platform where users can learn about different Pokémon through interactive features and captivating visuals. By exploring various Pokémon species, users can deepen their knowledge and appreciation of the Pokémon universe. The app/game also includes challenges to make the learning process entertaining and rewarding, fostering a community of enthusiastic.

### Features

- To choose between two unique character sprites.
- The ability to hatch a random Pokémon.
- To be able to feed, play and hear the cries of Pokémon in the party.
- To allows players fill out and view their individual Pokédex seeing more information about the Pokémon the player hatches.
- To evolve Pokémon, seeing the different Pokémon forms.
- To interact with the professor and to buy items from him that improve the progression speed.
- To buy eggs from the professor which have a random Pokémon inside.
- To donate Pokémon the player raises to obtain currency to use in the professors store.
- A trail system that allows players to send their Pokémon on adventures.
- A trail log that allows players to see what the Pokémon is encountering on the trails.

### Target Audience

As Pokémon is a product that is popular with all ages and demographics our target audience will tend to mimic that. The age range that that online Pokémon fans tend to be is somewhere between 20-29. As this product is an online application we will be catering to that demographic. While Pokémon fans will be our main target, the game has Gacha mechanics which allow us to appeal to the gacha game player demographic as well.

### Tech Stack

- **Front End**
  - Render
  - HTML
  - CSS
  - Javascript
  - React
  - Tech Domains
- **Back End**
  - Netlify
  - Javascript
  - NodeJS
  - ExpressJS
  - Mongoose
  - MongoDB
  - PokéAPI

## R2 - Dataflow Diagrams

The below diagrams depict how data travels, and is stored, throughout various processes present within the application.

### Login Process

![Login](./Images/DFD_Login.PNG)

### Shop Process

![Shop](./Images/DFD_Shop.PNG)

### Trail Process

![Trail](./Images/DFD_Trail.PNG)

### Pokémon Interaction Process

![Interactions](./Images/DFD_Interactions.PNG)

## R3 - Application Architecture Diagram

The PokéTrails application leverages a modern web architecture that includes a front-end built with HTML, CSS, JavaScript, and React, hosted on Netlify. The back-end, hosted on Render, utilises Node.js with Express.js and Mongoose for handling API requests and MongoDB operations. The system integrates with third-party services like PokéAPI to enhance functionality and provide comprehensive data to users.

Below is an overview of the full app architecture:
![Application Architecture Diagram.](./Images/App%20Architect.jpg)

## R4 - User Stories and Personas

In this section, we outline the key user personas and their respective user stories to ensure we cater to their needs and expectations.

### Persona - Pokémon Caretaker

![Caretaker](./Images/Persona_Caretaker.png)

### Persona - Pokémon Enthusiast

![Enthusiast](./Images/Persona_Enthusiast.png)

### Persona - Pokémon Trainer

![Trainer](./Images/Persona_Trainer.png)

### Persona - Pokémon Fan

![Fan](./Images/Persona_Fan.png)

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

## R6 - Trello Board Project Management Screenshots
