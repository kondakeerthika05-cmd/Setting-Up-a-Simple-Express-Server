# Setting-Up-a-Simple-Express-Server
Setting Up a Simple Express Server (with Nodemon)
1️⃣ Initialize a Node.js Project

Open your terminal and run:

npm init -y


This creates a package.json file with default values.

2️⃣ Install Required Dependencies
Install Express
npm i express

Install Nodemon (for auto-restart)
npm i -D nodemon

3️⃣ Update package.json (Enable Auto Restart)

Edit your package.json and add a start script:

{
  "scripts": {
    "start": "nodemon index.js"
  }
}


✔️ This ensures the server restarts automatically whenever you change code.

4️⃣ Create index.js

Create a file named index.js and add the following code:

const express = require("express");

const app = express();
const PORT = 3000;

// Home Route
app.get("/home", (req, res) => {
  res.json({ message: "This is home page" });
});

// Contact Us Route
app.get("/contactus", (req, res) => {
  res.json({ message: "Contact us at contact@contact.com" });
});

// About Route (Bonus)
app.get("/about", (req, res) => {
  res.json({ message: "Welcome to the About page!" });
});

// Start Server
app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});

5️⃣ Run the Server

Instead of node index.js, use Nodemon:

npm start

✅ Console Output
Server is running on http://localhost:3000

6️⃣ Test Routes (Browser / Postman)
🔹 GET /home
http://localhost:3000/home


Response

{
  "message": "This is home page"
}

🔹 GET /contactus
http://localhost:3000/contactus


Response

{
  "message": "Contact us at contact@contact.com"
}

🔹 GET /about
http://localhost:3000/about


Response

{
  "message": "Welcome to the About page!"
}

7️⃣ Auto Restart Check (Important)

✔️ Modify any route text
✔️ Save the file
✔️ Server restarts automatically (no manual restart)

📁 Final Project Structure
project-folder/
│
├── node_modules/
├── index.js
├── package.json
└── package-lock.json
