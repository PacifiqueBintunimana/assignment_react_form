<img width="713" alt="retrieved user" src="https://github.com/user-attachments/assets/b9fea3d3-df2e-41a6-96e4-d115741a5409">
<img width="953" alt="add user" src="https://github.com/user-attachments/assets/d4173c2b-ef30-4bb5-9d75-fe050ce14d3a">
# User Management Application

This is a full-stack web application built using React for the frontend and a Java/Spring Boot backend. The application allows users to create, read, and display user data in a simple form and display format.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Features](#features)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Future Enhancements](#future-enhancements)

## Project Overview
The User Management Application is designed to allow the addition of users through a form and display them in a list format. Users have attributes such as `name`, `email`, and `password`.

## Technologies Used
- **Frontend**: React, Material-UI (for UI components)
- **Backend**: Java, Spring Boot (REST API)
- **Dependencies**:
  - `@mui/material`, `@mui/icons-material`
  - `react` and `react-dom`
- **HTTP Requests**: Fetch API

## Features
- Add a new user through a form.
- View a list of all users retrieved from the backend.
- Handle user submissions and display success or error messages.
- Modern UI with Material-UI components.

## Setup and Installation

### Prerequisites
- **Node.js** (for running the React app)
- **Java 8+** (for running the Spring Boot application)
- **Maven** (for managing backend dependencies)

### Installation Steps

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/user-management-app.git
    cd user-management-app
    ```

2. **Frontend Setup**:
    - Navigate to the `frontend` directory:
      ```bash
      cd frontend
      ```
    - Install the dependencies:
      ```bash
      npm install
      ```
    - Start the development server:
      ```bash
      npm start
      ```

3. **Backend Setup**:
    - Navigate to the backend project root directory.
    - Run the Spring Boot application:
      ```bash
      mvn spring-boot:run
      ```

### Backend CORS Configuration
Ensure your backend allows CORS from the frontend by adding this configuration in your Spring Boot app:


