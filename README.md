# MEAN Stack Project

This project is built using the MEAN stack, which includes:

- **MongoDB:** A NoSQL database used for storing application data.
- **Express.js:** A Node.js web application framework for building the backend API.
- **Angular:** A front-end framework for building the user interface.
- **Node.js:** A JavaScript runtime environment for executing server-side code.

## Project Structure

The project is organized into the following directories:

- **`backend/`**: Contains the server-side code (Node.js/Express.js).
  - `models/`: Database models (e.g., Mongoose schemas).
  - `routes/`: API routes for handling requests.
  - `controllers/`: Logic for handling requests and interacting with the database.
  - `app.js`: Main application file for setting up the server and middleware.
  - `server.js`: entry point that calls app.js
- **`frontend/`**: Contains the client-side code (Angular).
  - `src/app/`: Main application directory.
    - `components/`: Angular components.
    - `services/`: Services for interacting with the backend API.
    - `models/`: Frontend representations of data models.
    - `app.module.ts`: Main application module.
    - `app-routing.module.ts`: Defines application routes.

## Getting Started

### Prerequisites

1.  **Node.js and npm:** Make sure you have Node.js (version 16 or later) and npm (Node Package Manager) installed on your system. You can download them from [nodejs.org](https://nodejs.org/).
2.  **MongoDB:** Install and run MongoDB Community Server. You can download it from [mongodb.com](https://www.mongodb.com/try/download/community).
3.  **Angular CLI:** Install Angular CLI globally: `npm install -g @angular/cli`

### Installation and Setup

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <project_directory>
    ```

2.  **Install backend dependencies:**

    ```bash
    cd backend
    npm install
    ```

3.  **Install frontend dependencies:**

    ```bash
    cd ../frontend
    npm install
    ```

4.  **Configure Environment Variables**
    Create a `.env` file in the `backend` directory and set up necessary environment variables. For example:

    ```
    PORT=3000
    MONGODB_URI=mongodb://localhost:27017/your-database-name
    ```

    Replace `your-database-name` with your desired database name.

### Running the Application

1.  **Start the backend server:**

    ```bash
    cd backend
    npm start
    ```

2.  **Start the frontend development server:**

    ```bash
    cd ../frontend
    ng serve --open
    ```

    The `--open` flag automatically opens the application in your default browser (usually at `http://localhost:4200`).

### Building for Production

1. Build the Angular application
   ```
   cd frontend
   ng build
   ```
2. Copy the contents of `frontend/dist/<project-name>` to a `public` folder in your backend.
3. Configure express to serve static files from the public folder.

   ```javascript
   //In backend/app.js
   const path = require("path");
   app.use(express.static(path.join(__dirname, "public")));

   //add a catch-all route to serve the index.html file for all other routes:
   app.get("*", (req, res) => {
     res.sendFile(path.join(__dirname, "public", "index.html"));
   });
   ```

## API Endpoints

Describe the available API endpoints (created in the `backend/routes` directory). For example:

- `GET /api/items`: Get all items.
- `POST /api/items`: Create a new item.
- `GET /api/items/:id`: Get a specific item by ID.
- `PUT /api/items/:id`: Update an item.
- `DELETE /api/items/:id`: Delete an item.

## Database Schema

Describe the structure of your database tables (created in the `backend/models` directory). Include details about columns, data types, and relationships. For example:

**Item**

| Column Name | Data Type | Constraints                 |
| ----------- | --------- | --------------------------- |
| id          | INTEGER   | Primary Key, Auto-increment |
| name        | TEXT      | Not Null                    |
| description | TEXT      |                             |
| createdAt   | DATETIME  |                             |
| updatedAt   | DATETIME  |                             |

## Testing

Provide information about how to run tests for both backend and frontend.

- Backend (Example using Jest)
  ```
  cd backend
  npm test
  ```
- Frontend (using karma and jasmine, Angular's default)
  ```
  cd frontend
  ng test
  ```

## Deployment

Provide instructions on how to deploy the application to a production environment (e.g., Heroku, AWS, DigitalOcean). This might involve setting up environment variables, configuring build scripts, and using a process manager like PM2.

## Contributing

Explain how others can contribute to the project (e.g., submitting pull requests, reporting issues).

## License

Specify the project's license (e.g., MIT).
