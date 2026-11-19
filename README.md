# Neha-AI

const express = require("express");
const cors = require("cors");

const app = express();

app.use(cors());
app.use(express.json());

const PORT = process.env.PORT || 3000;

// Home route
app.get("/", (req, res) => {
  res.send("NEHA AI Server is Running!");
});

// AI Chat route
app.post("/chat", (req, res) => {
  const message = req.body.message;

  if (!message) {
    return res.status(400).json({
      reply: "Please write a message."
    });
  }

  res.json({
    ai: "NEHA AI",
    reply: "Hello! Ami NEHA AI. Tomar message peyechi: " + message
  });
});

// Start server
app.listen(PORT, () => {
  console.log("NEHA AI Server running on port " + PORT);
});

{
  "name": "neha-ai-server",
  "version": "1.0.0",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^5.1.0",
    "cors": "^2.8.5"
  }
}
