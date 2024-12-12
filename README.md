# Task Manager App

## Description
A simple Task Manager application built with Vue 3, TailwindCSS, and Vite. This app allows users to manage their daily tasks. It provides a user-friendly interface with features such as adding, deleting, and filtering tasks, along with persisting data using localStorage.

---

## Screenshots

![vue3 vite tailwindcss](https://laravelcodesnippets.com/images/github/vue3-vite-tailwind-task-manager-app.png)

---

## Features

### 1. Adding Tasks
- Users can add tasks with a name input field.
- Tasks must have a name of at least 3 characters.

### 2. Marking Tasks as Completed
- Toggle a task's completion status using a checkbox.
- Completed tasks dynamically update their appearance with:
    - **Light Green Background**
    - **Red Border**

### 3. Deleting Tasks
- Remove tasks from the list with a delete button.

### 4. Filtering Completed Tasks
- Option to filter the task list to show only completed tasks.

### 5. Persisting Data
- Task data is stored in `localStorage` to ensure persistence across browser reloads.

### 6. Dynamic UI Updates
- Displaying a toggleable form for adding new tasks.
- Showing a message, "No tasks available," when the task list is empty.

---

## Project Setup

### Installation
1. Clone this repository:
   ```bash
   https://github.com/mahfoman/vuejs-task-management-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd vuejs-task-management-app
   ```
3. Install dependencies:
   ```bash
   npm install
   ```

### Development
To start the development server:
```bash
npm run dev
```
Open your browser and navigate to `http://localhost:5173/`.

### Build
To create a production build:
```bash
npm run build
```
---

## File Structure

### Main Components
- **App.vue**: Main entry point of the application. Includes form handling, task filtering, and manages the global state.
- **TaskList.vue**: Handles rendering of the task list, including individual task elements and their respective event handling.

### Styles
- TailwindCSS is used for consistent and responsive styling.

---

## Technologies Used
- **Vue 3**: Framework for building the user interface.
- **Vite**: Development environment and build tool for faster builds.
- **TailwindCSS**: Utility-first CSS framework for styling.
- **localStorage**: Web API for data persistence.

---

