# BookMyShow - MERN Stack Project

**BookMyShow** is a movie ticket booking application built using the MERN stack (MongoDB, Express, React, Node.js). Users can select a movie, a time slot, and specific seats to book tickets. The application communicates with a backend server to store and retrieve booking details.

---

## Features
- **Select Movie:** Users can choose from a list of available movies.
- **Select Schedule:** Users can choose a time slot for the selected movie.
- **Select Seats:** Users can select specific seats.
- **Booking:** Submit a booking with selected movie, schedule, and seats.
- **View Last Booking:** Display the most recent booking details.

---

## Tech Stack
- **Frontend:** React, React Context API
- **Backend:** Node.js, Express, MongoDB (Mongoose)
- **Database:** MongoDB
- **State Management:** React Context API

---

## Project Setup

### Backend Setup

1. **Clone the repository:**

    ```bash
    git clone <repo_url>
    cd <project_directory>/backend
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Setup MongoDB:**
    - Make sure you have MongoDB installed locally. You can install MongoDB from [here](https://www.mongodb.com/try/download/community).
    - Ensure that MongoDB is running locally on port `27017`.

4. **Run the backend:**

    ```bash
    npm start
    ```

    The server will start running on `http://localhost:8080`.

---

### Frontend Setup

1. **Navigate to the frontend directory:**

    ```bash
    cd <project_directory>/frontend
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Run the frontend:**

    ```bash
    npm start
    ```

    The React app will be available at `http://localhost:3000`.

---

## Backend Details

### Routes:
- `POST /api/booking`: Create a new booking with movie, time slot, and seat details.
- `GET /api/booking`: Retrieve the most recent booking.

### Database Schema (MongoDB):
- **Ticket Schema:**
    ```js
    const TicketSchema = new mongoose.Schema({
      movie: { type: String },
      slot: { type: String },
      seats: {
        A1: { type: Number },
        A2: { type: Number },
        A3: { type: Number },
        A4: { type: Number },
        D1: { type: Number },
        D2: { type: Number },
      },
    });
    ```

### Database Connection:

- The backend connects to the MongoDB database (`bookMyShow`) running locally on `mongodb://127.0.0.1:27017`.

---

## Frontend Details

### React Components:
1. **Home.js**: The main component that houses the movie selection, time schedule, seat selection, and booking functionalities.
2. **SelectMovie.js**: Allows users to choose a movie from the available list.
3. **TimeShedule.js**: Lets users pick a time slot for the selected movie.
4. **SelectSeats.js**: Provides seat selection options.
5. **LastBookingDetails.js**: Displays the most recent booking.
6. **ModalComponent.js**: A modal that shows success/error messages.
7. **BsState.js**: Manages global state using the Context API, including movie, time, seats, and last booking details.

### Local Storage:
- The app stores user selections (movie, time, and seats) in `localStorage` to persist data across page reloads.

---

## How It Works

1. **Select Movie:** Users choose a movie from the list.
2. **Select Schedule:** After selecting the movie, users choose a time slot.
3. **Select Seats:** Users then choose seats (A1, A2, A3, etc.) and specify the number of seats for each.
4. **Submit Booking:** Once the selections are made, users click the "Book Now" button to submit the booking to the backend.
5. **View Last Booking:** The app fetches and displays the most recent booking when the page loads.

---

## Example Data

**Movies List:**
- Justice League
- Tenet
- Fast X
- Planet of the Apes
- Come Play

**Time Slots:**
- 10:00 AM
- 01:00 PM
- 03:00 PM
- 08:00 PM

**Seats:**
- A1, A2, A3, A4, D1, D2

---

## File Structure

