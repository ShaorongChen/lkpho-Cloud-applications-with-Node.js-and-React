# Node.js HTTP Server with Time-based Greetings

This is a simple Node.js HTTP server that responds with time-based greetings. The server listens on port 8080 and returns different greeting messages based on the current time of day.

## Features

- Time-based greetings (morning, afternoon, evening, night)
- Simple HTTP server implementation using Node.js built-in `http` module
- Modular design with a separate `today` module for date handling

## How It Works

The server determines the appropriate greeting based on the current hour:
- 6:00 AM - 11:59 AM: "Good morning!"
- 12:00 PM - 5:59 PM: "Good afternoon!"
- 6:00 PM - 8:59 PM: "Good evening!"
- 9:00 PM - 11:59 PM: "Good night!"

If the time is between 12:00 AM and 5:59 AM, it returns "It is still not morning".

## Prerequisites

- Node.js (version 20 or higher recommended)

## Setup

1. Create a new directory for your project
2. Initialize a new Node.js project:
   ```bash
   npm init -y
   ```
3. Create the main server file (`index-with-require.js`) with the provided code
4. Create a `today.js` module file with the following content:
   ```javascript
   // today.js
   const getDate = () => {
     return new Date();
   };
   
   module.exports = { getDate };
   ```

## Running the Server

1. Save both files in the same directory
2. Run the server using Node.js:
   ```bash
   node index-with-require.js
   ```
3. Open your browser and navigate to `http://localhost:8080`
4. You should see a greeting message based on the current time

## Project Structure

```
project/
├── index-with-require.js
└── today.js
```