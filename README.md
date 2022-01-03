# Rentx API - A complete API for car registration and rental.

This project was developed during the NodeJS track, available on Rocketseat's Ignite.

## Table of contents

- [Overview](#overview)
  - [The project](#the-project)
  - [Routes](#routes)
- [Development process](#development-process)
  - [Built with](#built-with)
- [Coded by](#coded-by)
- [How to run the project](#how-to-run-the-project)

## Overview

### The project

Users should be able to:

- Register a car
- List the cars
- Register car specifications
- Rent a car
- Return a car
- List rentals by user
- Recover password

### Routes

To get all the application routes and how to use them, after running the project, view the documentation created with Swagger, just access localhost:3333/api-docs.

## Development process

### Built with

- Express
- BCrypt
- JSON Web Token
- Typeorm
- Postgres
- NodeJS
- Sentry
- Handlebars
- Nodemailer

## Coded by

- Website - [Daniel Mafra](https://danielmafra.github.io)
- LinkedIn - [@danielmafradev](https://linkedin.com/in/danielmafradev)
- Instagram - [@danielmafradev](https://instagram.com/danielmafradev)

## How to run the project

Clone the repository using "git clone". After that, go to the project folder and use the command "npm install" or "yarn install" to install the dependencies.

Make sure you are running Postgres and rename the .env.example file to .env, and also the ormconfig.example.json file to ormconfig.json. After that, edit using your Postgres information and also other environment information.

Finally use the command "yarn typeorm migration:run" and then "npm run dev" or "yarn dev" to start the project.

# Guide to developing the API:

## Car registration

- FR: Functional Requirements
- BR: Business rules
- NFR: Non-functional requirements

**FR**
- It must be possible to register a new car.


**BR** 
- It must not be possible to register a car with an existing license plate.
- The car must be registered, by default, with availability.
- The user responsible for registration must be an administrator user.

## Car listing

**FR** 
- It should be possible to list all available cars
- It should be possible to list all available cars by - category name
- It should be possible to list all available cars by - brand name
- It should be possible to list all available cars by - car name

**BR**
- The user does not need to be logged into the system.


## Car Specification Registration

**FR**
- It must be possible to register a specification for a car


**BR**
- It must not be possible to register a specification for a - unregistered car.
- It must not be possible to register an existing specification for the same car.
- The user responsible for registration must be a user - administrator.


## Car image registration

**FR**
- It must be possible to register the car image

**NFR**
- Use multer to upload files

**BR**
- The user must be able to register more than one image for the same car
- The user responsible for registration must be a user - administrator.


## Car rental

**FR**
- It must be possible to register a rental


**BR**
- The rental must have a minimum duration of 24 hours.
- It should not be possible to register a new rental if it already exists - there is one open for the same user
- It should not be possible to register a new rental if it already exists - there is one open for the same car
- The user must be logged in to the application
- When renting, the status of the car must be - changed to unavailable


## Car return 

**FR**
- It must be possible to return a car

**BR**
- If the car is returned with less than 24 hours, it must be - charged in full daily.
- When returning, the car must be released for - another rental.
- When making the return, the user must be released - for another rental.
- When returning, the total rent must be calculated.
- If the return time is longer than the scheduled delivery time, a fine will be charged - proportional to the days of delay.
- If there is a fine, it must be added to the total rent.
- The user must be logged in to the application


## User Rental Listing

**FR**
- It must be possible to search all rentals for the user

**BR**
- The user must be logged in to the application


## Recover Password

**FR**
- It must be possible for the user to recover the password by entering the email
- The user should receive an email with the step-by-step password recovery
- User must be able to enter a new password

**BR**
- User needs to enter a new password
- Link sent for recovery must expire in 3 hours
