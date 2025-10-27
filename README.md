🗨️ Real-Time Chat App
📌 Overview

The Real-Time Chat App is a full-stack web application that enables users to send and receive messages instantly.
It uses React (frontend), Node.js + Express (backend), and Socket.IO for real-time communication.

🧠 Features

💬 Instant messaging using Socket.IO

👤 Username-based chat rooms

⚡ Real-time message updates (no refresh needed)

🧩 Simple and responsive UI with React

🚀 Backend built with Node.js & Express

🏗️ Project Structure
real-time-chat-app/
│
├── backend/
│   ├── server.js              # Main backend server file
│   ├── routes/                # API routes (if any)
│   ├── models/                # Database models (optional)
│   ├── package.json           # Backend dependencies
│
├── frontend/
│   ├── public/                # Static files (index.html, icons, etc.)
│   ├── src/
│   │   ├── App.js             # React main component
│   │   ├── index.js           # React entry point
│   │   ├── App.css            # Styling
│   ├── package.json           # Frontend dependencies
│
└── README.md                  # Project documentation

⚙️ Installation Steps
1️⃣ Clone or download the repository
git clone https://github.com/your-username/real-time-chat-app.git
cd real-time-chat-app

2️⃣ Install backend dependencies
cd backend
npm install

3️⃣ Run backend server
npx nodemon server.js


Backend runs on http://localhost:5000

4️⃣ Install frontend dependencies

Open a new terminal:

cd ../frontend
npm install

5️⃣ Run React app
npm start


Frontend runs on http://localhost:3000

🔌 Tech Stack
Area	Technology
Frontend	React.js, Socket.IO Client
Backend	Node.js, Express, Socket.IO
Communication	WebSockets
Styling	CSS, Tailwind (optional)
🧩 Example Code Snippet

Backend (server.js):

const express = require("express");
const http = require("http");
const { Server } = require("socket.io");
const cors = require("cors");

const app = express();
app.use(cors());

const server = http.createServer(app);
const io = new Server(server, {
  cors: { origin: "http://localhost:3000" },
});

io.on("connection", (socket) => {
  console.log("User connected:", socket.id);

  socket.on("chatMessage", (data) => {
    io.emit("chatMessage", data);
  });

  socket.on("disconnect", () => {
    console.log("User disconnected:", socket.id);
  });
});

server.listen(5000, () => console.log("✅ Server running on port 5000"));

💡 Future Improvements

✅ Add user authentication

💾 Store messages in MongoDB

🕒 Add timestamps and typing indicators

📱 Make fully responsive

📸 Screenshot (Optional)

Add a screenshot of your UI here once your app is running.

👨‍💻 Author

Ayush Tuptewar
📧 tuptewarayush@gmail.com
💼 https://www.linkedin.com/in/ayush-tuptewar-b9a87b372/
