---
layout: project
type: project
image: img/GameReviewDatabase.jpg
title: "Game Review Database"
date: 2025
published: True
labels:
  - Python
  - MySQL
  - Selenium
  - CSV
  - SQL Stored Procedures
summary: "This project is a Python and MySQL-based Game Review Database Platform that collects, stores, and manages structured video game information and reviews. I designed a normalized relational database for games, users, media outlets, reviews, companies, platforms, genres, and staff credits, then built a command-line application using PyMySQL to support account management, game browsing, search, and review CRUD operations. The project also includes custom BeautifulSoup and Selenium web scrapers to collect game data and reviews from Metacritic, with CSV import scripts and SQL stored procedures used to clean, load, and manage the data efficiently."
---
# Game Review Database Platform

**Tech Stack:** Python, MySQL, PyMySQL, BeautifulSoup, Selenium, CSV, SQL Stored Procedures, Command-Line Interface

## Project Overview

Game Review Database Platform is a Python and MySQL-based command-line application designed to collect, manage, and display video game information and reviews from both players and media sources. The system stores structured game data such as titles, descriptions, release dates, genres, platforms, developers, publishers, staff credits, user reviews, and media reviews.

The project was built to simulate a real-world game review platform where different types of users can create accounts, browse game information, post reviews, manage their own reviews, and search through game-related data. The database was populated using custom Python web scrapers that collected game information, critic reviews, user reviews, and staff credits from Metacritic.

## Key Features

- Designed a normalized relational database schema for games, users, media accounts, reviews, companies, platforms, genres, and staff credits.
- Built a Python command-line application that connects to MySQL using PyMySQL.
- Implemented user and media account registration, login, password update, and account deletion.
- Supported full review management, including creating, reading, updating, and deleting reviews.
- Added game browsing and detailed game information views, including genre, platform, publisher, developer, rating, and staff data.
- Developed custom web scrapers using BeautifulSoup and Selenium to collect structured game and review data.
- Imported CSV datasets into MySQL through Python scripts and stored procedures.
- Used SQL stored procedures to organize database operations and improve maintainability.
- Implemented keyword-based search for games, companies, staff, genres, and platforms.

## Technical Implementation

The application uses Python as the main host language for user interaction, data import, and database communication. MySQL is used as the database management system, with a schema designed around relational entities such as games, users, media outlets, reviews, companies, platforms, genres, and staff.

To reduce duplicate data and improve consistency, many-to-many relationships are handled through junction tables, such as game-to-genre, game-to-platform, game-to-developer, game-to-publisher, and game-to-staff mappings. This structure makes the database easier to query, extend, and maintain.

The project also uses SQL stored procedures for common database operations, including inserting games, adding reviews, updating records, deleting accounts, and retrieving review information. This separates database logic from the Python application layer and improves maintainability.

For data collection, the project includes multiple Python scraping scripts. BeautifulSoup is used to parse static game information, while Selenium is used for pages where reviews are loaded dynamically. The collected data is saved into CSV files and then imported into the database using a custom CSV import script.

## Database Design

The database schema was designed to organize game-related data into clear relational entities. Core entities include:

- Games
- Users
- Media accounts
- User reviews
- Media reviews
- Companies
- Platforms
- Genres
- Staff credits

Several many-to-many relationships are represented using junction tables. For example, one game can belong to multiple genres, appear on multiple platforms, have multiple developers and publishers, and include multiple staff members. This design improves data consistency and avoids storing repeated values directly inside the main game table.

## Data Collection Pipeline

The data pipeline follows this general process:

1. Scrape game information and review data from online sources.
2. Clean and organize the scraped data.
3. Store the cleaned data into CSV files.
4. Import the CSV files into MySQL using Python scripts.
5. Use stored procedures to insert and manage structured data.
6. Display and manage the data through the command-line application.

This pipeline helped transform unstructured web data into a structured relational database that can be queried and managed efficiently.

## What I Learned

Through this project, I gained practical experience in relational database design, SQL schema development, stored procedures, Python-to-MySQL integration, command-line application design, and real-world data collection.

I also learned how to handle messy external data, normalize multi-valued fields, manage many-to-many relationships, and design a system that supports both data management and user interaction.

## Future Improvements

Possible future improvements include:

- Building a web-based frontend for easier user interaction.
- Adding advanced filters for genre, platform, developer, publisher, and rating.
- Improving authentication security with password hashing.
- Expanding the dataset with more games and review sources.
- Adding game cover images and media assets.
- Migrating part of the data pipeline to a NoSQL database for easier handling of nested JSON-style data.
- Adding analytics features such as top-rated games, review trends, and platform comparisons.

## Portfolio Summary Version

Game Review Database Platform is a Python and MySQL-based command-line database application for managing video game information and reviews. The system allows users and media accounts to register, browse game details, post reviews, edit or delete their own reviews, and search structured game-related data.

I designed and implemented a normalized relational database schema covering games, reviews, users, media outlets, companies, platforms, genres, and staff credits. The project also includes custom Python web scrapers built with BeautifulSoup and Selenium to collect game data, critic reviews, user reviews, and staff information from Metacritic. Data was cleaned, stored in CSV files, and imported into MySQL using Python scripts and SQL stored procedures.

This project strengthened my experience in database design, SQL stored procedures, Python-MySQL integration, data scraping, CSV data processing, and command-line application development.

## Resume Bullet Points

- Built a Python and MySQL command-line application for managing video game information, user reviews, and media reviews.
- Designed a normalized relational database schema with tables for games, users, media outlets, reviews, companies, platforms, genres, and staff credits.
- Implemented CRUD functionality for user accounts, media accounts, reviews, and game-related data using PyMySQL and SQL stored procedures.
- Developed custom Python web scrapers with BeautifulSoup and Selenium to collect game details, reviews, and staff credits from Metacritic.
- Created CSV import scripts to clean and load scraped data into MySQL for structured querying and application use.
