# CodeColab2

CodeColab2 is a real-time collaborative code editor that allows multiple users to write and edit code together seamlessly. It features a modern, responsive UI with presence awareness (seeing who is currently in the session). 

The project is built using a modern JavaScript stack with **React** and **Monaco Editor** on the frontend, and **Express** and **Socket.io** on the backend. It uses **Yjs** for efficient Conflict-free Replicated Data Types (CRDTs) to sync the editor state in real-time.

## Tech Stack

**Frontend (Client)**
- React 19
- Vite
- TailwindCSS v4
- Monaco Editor (`@monaco-editor/react`)
- Yjs & y-socket.io (Real-time code synchronization)

**Backend (Server)**
- Node.js & Express
- Socket.io
- y-socket.io (Yjs WebSocket server provider)

## Project Structure

```text
CodeColab2/
├── client/                 # Frontend React Application
│   ├── public/             # Static assets
│   ├── src/                
│   │   ├── app/            # Main application components (App.jsx contains Editor logic)
│   │   ├── assets/         # Images and icons
│   │   └── main.jsx        # React entry point
│   ├── package.json        # Frontend dependencies and scripts
│   ├── vite.config.js      # Vite build configuration
│   └── netlify.toml        # Netlify deployment routing config
├── server/                 # Backend Node.js Server
│   ├── public/             # Static assets served by Express
│   ├── package.json        # Backend dependencies and scripts
│   └── server.js           # Express app, HTTP server, and Socket.io setup
├── .gitignore              # Git ignore rules
└── README.md               # Project documentation
```

## Running Locally

### Prerequisites
- Node.js (v18 or higher recommended)
- npm or yarn

### 1. Start the Server
Open a terminal, navigate to the `server` directory, install dependencies, and start the development server.

```bash
cd server
npm install
npm run dev
```
The server will run on `http://localhost:8000`.

### 2. Start the Client
Open a new terminal, navigate to the `client` directory, install dependencies, and start the Vite development server.

```bash
cd client
npm install
npm run dev
```
The client will usually run on `http://localhost:5173`. Open this URL in your browser to start collaborating!

## Deployment

### Frontend (Netlify)
The frontend is pre-configured to be deployed on Netlify. 
1. Connect the repository to Netlify and select the `client` folder as the **Base directory**.
2. Set the build command to `npm run build` and publish directory to `client/dist`.
3. Add an Environment Variable: `VITE_BACKEND_URL` pointing to your deployed backend URL.

### Backend (Render)
The backend is ready to be deployed on Render as a Web Service.
1. Connect the repository to Render.
2. Set the **Root Directory** to `server`.
3. Use the build command `npm install` and start command `npm start`. Render will dynamically assign the correct `PORT`.
