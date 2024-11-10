<img width="713" alt="retrieved user" src="https://github.com/user-attachments/assets/b9fea3d3-df2e-41a6-96e4-d115741a5409">
<img width="953" alt="add user" src="https://github.com/user-attachments/assets/d4173c2b-ef30-4bb5-9d75-fe050ce14d3a">
<img width="960" alt="Screenshot 2024-11-10 134143" src="https://github.com/user-attachments/assets/cce0f9c3-1467-4d40-8aa2-ded2bdaab161">

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

question  
Handling forms in React: form inputs, validation, and submission.
Managing form state and controlled components.
React Form Handling
This repository provides examples and explanations of how to manage forms in React. It covers the core concepts of controlled components, form state management, form validation, and handling form submission.

Table of Contents
Introduction
1. Form Inputs and Controlled Components
2. Managing Form State
3. Form Validation
4. Handling Form Submission
5. Key Points to Remember
Introduction
Handling forms in React involves managing the state of form inputs, validating data, and handling form submissions. In this guide, we will cover how to work with controlled components, manage form state, add custom validation logic, and handle form submissions.

1. Form Inputs and Controlled Components
In React, controlled components are form input elements whose values are controlled by the component's state. This approach allows React to manage the form's state and gives you more control over the input values.

Example of a Basic Controlled Form Input:
jsx
Copy code
import React, { useState } from 'react';

function SimpleForm() {
  const [name, setName] = useState('');

  const handleChange = (event) => {
    setName(event.target.value);
  };

  return (
    <form>
      <label>
        Name:
        <input type="text" value={name} onChange={handleChange} />
      </label>
    </form>
  );
}
In this example:

The input's value is tied to the name state variable.
The onChange event handler updates the state whenever the user types in the input.
2. Managing Form State
For forms with multiple inputs, you can use a single state object to manage all form data. This allows you to update the form data dynamically.

Example of Managing State for Multiple Inputs:
jsx
Copy code
import React, { useState } from 'react';

function MultiInputForm() {
  const [formData, setFormData] = useState({
    name: '',
    email: '',
    password: ''
  });

  const handleChange = (event) => {
    const { name, value } = event.target;
    setFormData({ ...formData, [name]: value });
  };

  return (
    <form>
      <label>
        Name:
        <input type="text" name="name" value={formData.name} onChange={handleChange} />
      </label>
      <label>
        Email:
        <input type="email" name="email" value={formData.email} onChange={handleChange} />
      </label>
      <label>
        Password:
        <input type="password" name="password" value={formData.password} onChange={handleChange} />
      </label>
    </form>
  );
}
In this example:

formData contains all the values of the form fields.
The handleChange function updates the specific field that changed by using the name attribute.
3. Form Validation
Form validation ensures that the user submits valid data. You can implement validation logic in the onChange or onSubmit handlers. Validation errors can be stored in state and displayed conditionally.

Example with Simple Validation:
jsx
Copy code
import React, { useState } from 'react';

function ValidatedForm() {
  const [formData, setFormData] = useState({ email: '' });
  const [errors, setErrors] = useState({});

  const handleChange = (event) => {
    const { name, value } = event.target;
    setFormData({ ...formData, [name]: value });

    // Basic email validation
    if (name === 'email' && !/\S+@\S+\.\S+/.test(value)) {
      setErrors({ ...errors, email: 'Invalid email format' });
    } else {
      setErrors({ ...errors, email: '' });
    }
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    if (!formData.email) {
      alert('Please fill out the form');
    } else if (!errors.email) {
      alert('Form submitted successfully');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Email:
        <input type="email" name="email" value={formData.email} onChange={handleChange} />
      </label>
      {errors.email && <span style={{ color: 'red' }}>{errors.email}</span>}
      <button type="submit">Submit</button>
    </form>
  );
}
In this example:

The handleChange function checks the email format and updates the error state if necessary.
The error message is displayed below the input field if the validation fails.
4. Handling Form Submission
In React, you can handle form submission using the onSubmit event handler. You typically call event.preventDefault() to prevent the default form submission behavior (which would reload the page).

You can then send the form data to a server using fetch or axios.

Example of Form Submission with fetch:
jsx
Copy code
const handleSubmit = async (event) => {
  event.preventDefault();
  const response = await fetch('/submit-form', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify(formData)
  });
  if (response.ok) {
    alert('Form submitted successfully');
  } else {
    alert('Submission failed');
  }
};
In this example:

The form data is sent to the server using the fetch API in a POST request.
The submission result is handled with an alert indicating whether it was successful or not.
5. Key Points to Remember
Controlled Components: Ensure that form input values are tied to the component's state, which gives you more control over the form.
Validation: Implement validation logic in the form to check that the user input is correct. Display error messages if the validation fails.
Form State Management: Use useState for managing form data, or use third-party libraries like Formik or React Hook Form for complex forms.
Submission: Always handle form submissions using event.preventDefault() to prevent page reload, and send the data to the server with fetch or axios.
For more complex forms, consider using libraries like Formik or React Hook Form to simplify state management, validation, and submission.

