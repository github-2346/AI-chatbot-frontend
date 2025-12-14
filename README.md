
## Overview
This is the frontend interface of the real-time chat application. It connects to the Spring Boot backend using REST APIs and WebSockets, manages authentication, displays conversations, loads message history with pagination, and shows real-time AI responses.

## Features
- JWT authentication (register + login)
- Real-time chat using STOMP over WebSockets
- REST API integration with Axios
- Paginated message history with infinite scroll
- Conversation list management
- AI typing indicators and status updates
- Clean UI with message bubbles
- WebSocket reconnect handling

## Tech Stack
- React (Vite)
- @stomp/stompjs + sockjs-client (WebSockets)
- Axios
- TailwindCSS (optional)
- JavaScript / JSX

## Installation

### 1. Clone the repository

git clone <your-frontend-repo-url>
cd chat-frontend


### 2. Install dependencies

npm install

### 3. Run development server

npm run dev

Frontend runs by default on:

http://localhost:5173


## Environment Variables
Create a `.env` file:

VITE_BACKEND_URL=http://localhost:8080

## Project Structure

src/
│
├── components/
│   ├── ChatWindow.jsx
│   ├── ConversationList.jsx
│
├── hooks/
│   ├── useChat.js
│
├── services/
│   ├── ws/wsService.js
│
├── styles/
│   ├── chat.css
│
├── App.jsx
└── main.jsx

## WebSocket Endpoints
Backend WebSocket endpoint:

ws://localhost:8080/ws

### Client → Server (Send)

/app/chat

### Server → Client (Subscribe)

/topic/conversations/{conversationId}

## Scripts
- `npm run dev` — start development server  
- `npm run build` — build for production  
- `npm run preview` — preview production build  

## Notes
- Ensure backend is running before starting frontend.
- JWT must be stored securely (recommended: HttpOnly cookie or memory state).
- WebSocket reconnect is enabled by default.
