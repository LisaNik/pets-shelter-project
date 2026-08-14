# 🐾 Animal Shelter Adoption Web Service

A multifunctional web application for browsing animals from a shelter, finding a suitable pet, saving favorites, and submitting adoption requests.
This project was developed as a Bachelor's thesis in Computer Science.

**[Live Demo](https://lisa.freehosting.dev/PetsShelter_project/home.html)** · **[Repository](https://github.com/LisaNik/movie-watchlist)**

## Overview

The application is designed to make the process of finding and adopting a shelter animal more convenient. Users can browse animal profiles, filter the catalog, save favorite animals, learn more about individual pets, complete a personalized pet-selection test, and submit an adoption request.

A key feature of the project is a recommendation algorithm based on **weighted Euclidean distance**. The algorithm compares the user's preferred pet characteristics with the characteristics stored for available animals and selects the closest match.

## Features

- 🐶 **Animal catalog** with detailed pet profiles
- 🔎 **Filtering** by animal type, size, gender, and age
- ❤️ **Favorites** stored in the browser using `localStorage`
- 📄 **Individual pet pages** with detailed information
- 📝 **Adoption form** for submitting an adoption request
- 🧠 **Personalized pet-selection quiz**
  - 24 questions
  - 12 desired pet characteristics
  - 12 importance/weight parameters
  - ratings from 1 to 5
  - weighted Euclidean distance calculation
- 🎮 **Two interactive games**
  - picture puzzle
  - sliding puzzle (15-puzzle style)
- 💰 **Donation section** with one-time and monthly donation UI
- 📊 **Interactive donation statistics**
- 📱 Responsive web interface
- 🎨 UI designed and prototyped in Figma

## Recommendation Algorithm

The pet-selection test uses a weighted Euclidean distance to compare the user's preferences with the parameters of available animals.

The process is:

1. The user answers 24 questions using a 1–5 scale.
2. The first 12 answers represent desired pet characteristics.
3. The remaining 12 answers determine the importance of each characteristic.
4. Pet parameters are loaded from the MySQL database.
5. The application calculates the weighted distance for each animal.
6. The animal with the smallest distance is presented as the best match.

This approach allows the recommendation to consider not only how closely a pet matches the user's preferences, but also which characteristics are more important to the user.

## Tech Stack

### Frontend
- HTML5
- CSS3
- Vanilla JavaScript

### Backend
- PHP
- MySQL
- JSON-based data exchange using `fetch()`

## Database

The application uses MySQL to store:

- animal profiles
- animal characteristics and behavioral parameters
- adoption requests

The database is accessed through PHP scripts that return JSON data to the frontend and process submitted adoption forms.

The database structure was designed using an ER model.

## Project Structure

```text
PetsShelter_project/
├── home.html
├── pets.html
├── petPage.html
│
├── css/
│   ├── styles.css
│   ├── catalog.css
│   ├── petcatalog.css
│   ├── petpage.css
│   ├── quiz.css
│   ├── modal.css
│   ├── donations.css
│   ├── graphs.css
│   ├── partners.css
│   ├── footer.css
│   └── button.css
│
├── images/
├── imagesPets/
│
├── script.js
├── petscript.js
├── petsphp.js
├── pagePetScript.js
├── homephp.js
├── modal.js
├── game.js
│
├── profile.php
├── parameters.php
├── user.php
└── profile/
```

## Running Locally

Because the project contains PHP and MySQL backend functionality, it cannot be run correctly by simply opening the HTML files in a browser.

### Requirements

- PHP
- MySQL
- A local development environment such as XAMPP
- Web browser

### Setup

1. Clone the repository:

```bash
git clone <repository-url>
cd PetsShelter_project
```

2. Place the project inside your local web server directory, for example:

```text
xampp/htdocs/PetsShelter_project
```

3. Create a MySQL database and the required tables for animal profiles, animal parameters, and adoption requests.

4. Configure the database connection in the PHP backend files.

5. Start **Apache** and **MySQL** in XAMPP.

6. Open the application through the local server:

```text
http://localhost/PetsShelter_project/home.html
```

> Do not commit database usernames, passwords, or other credentials to GitHub. Database credentials should be stored in a local configuration file or environment variables.

## Project Focus

The main technical focus of the project was combining frontend development with backend/database functionality and implementing a recommendation algorithm for personalized pet selection.

## Academic Project

**Bachelor's Thesis — Computer Science, 2024**

Topic:

> Development of a web service for searching and adopting animals from shelters using selection strategies.
