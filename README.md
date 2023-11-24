# Task Manager Application (Frontend)

## Overview

This repository contains the frontend for the Task Manager web application, built using NuxtJS (Version 2). The Task Manager web application is a straightforward yet powerful tool designed to help you manage your tasks efficiently. Built with modern web technologies, the application provides a seamless user experience with its intuitive interface.

## Application Features

- **Task List Overview:** View a comprehensive list of your current tasks at a glance.

- **Create New Task:** Easily create a new task with a specified name, due date, and completion status.

- **Mark Task as Done/Completed:** Keep track of your progress by marking tasks as done when completed.

## How to Run the Application

1. **Clone the Repository:**

2. **Install Dependencies:**
      ```bash
      npm install  

2. **Install Dependencies:**
      ```bash
      npm install  

   
3. **Run the Application:**
      ```bash
      npm install  

   
5. **Build and Deployment Instructions (more):**
   To build and deploy the application, follow these steps:
   I. Run npm install to install dependencies.
   II. Configure the necessary environment variables.
   III. Run npm run dev for local development.
   IV. Deploy the application as per your hosting environment requirements.

6. **Application Features:**
    - The application will run at http://localhost:3000.
    - Note: There is no Database linked! The page refresh will clear the form.
    - New tasks can be registered under "Task Registration" by entering the task name and the due date (both fields are mandatory).
    - Once data is entered, sorting (by due date or task name) and filtering (incomplete, completed, all) can be tested.
    - The application is for demonstration purposes only, and no additional services are implemented.

7. **Future Plans:**
    - User authentication using the Auth0 protocol.
    - Display tasks based on user rights/department.
    - Record user details (UserID, registered Date & Time) once a task is registered.
    - Update task details by clicking on the task (e.g., status update) and maintain the update history log with user details.
    - Modify any tasks depends on the permission assigned.
    - Reporting.
      
8. **Project Structure:**
   The project follows the standard structure expected in NuxtJS projects. Key directories include:
    -  components: Vue components used in the project.
    -  layouts: NuxtJS layouts defining the structure of the pages.
    -  pages: Vue pages representing the different views of the application.
    -  static: Static assets like images, fonts, etc.
    -  store: Vuex store modules for managing the application state.
   
9. **Dependencies:**
    - NuxtJS (Version 2): Frontend framework for building Vue.js applications.
    - Vue.js: JavaScript framework for building user interfaces.
    - Auth0: Authentication and authorization platform for securing the application. (not yet applied)

10. **Environment Variables:**
    The application relies on the following environment variables:

   - AUTH0_DOMAIN: The domain provided by Auth0 for authentication.
   - AUTH0_CLIENT_ID: The client ID provided by Auth0 for authentication.
   
   Ensure these variables are set in your environment for proper application functionality.

11. **Testing:**
The application includes unit tests for critical components. Run tests using the command:
    ```bash
    npm run test

12. **Code Style and Linting:**
   The project follows the standard Vue.js and NuxtJS code style guidelines. Linting is enforced using ESLint.

13. **Troubleshooting:**
    If you encounter issues or error messages, refer to the Troubleshooting Guide for common solutions.
    
14. **Contributions:**
    We welcome contributions, feedback, and bug reports. Please follow the guidelines in CONTRIBUTING.md when contributing to this project.
    
15. **Acknowledgments:**
    We would like to thank the following projects and libraries for their contributions to this application:

      - Vue.js
      - NuxtJS
      - Auth0

16. **Reports**
    If you have any suggestions or issues related to reports, please provide feedback or report them to help us enhance the reporting functionality.
    Feel free to adjust any details according to the specific structure and needs of your project.
    
17. **License**

The Task Manager project is licensed under the MIT License.

Thanks for using Task Manager! 🚀 Udithac, 23/11/2023, Berlin, GE.
