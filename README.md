# web-dev-ii-25-26-final
web-dev-ii-25-26-final
# Tara-Yah Keto Kitchen — Recipe Manager

A multi-device recipe manager built with a React front-end and an Express.js
back-end, for the Web Dev II Multi-Device Application assessment.

## Project structure

tara-yah-keto-kitchen/
├── client/          React front-end (Vite)
│   └── src/
│       ├── components/   UI components (Header, CategoryChips, RecipeGrid, RecipeCard, modals)
│       ├── api.js        fetch wrapper for the recipes REST API
│       ├── App.jsx       top-level state and layout
│       └── styles.css    theme and layout styles
└── server/          Express.js back-end
    ├── data/recipes.json  recipe "database" (JSON file on disk)
    ├── routes/recipes.js  REST API route handlers
    └── server.js          Express app entry point

## Running the project

You need two terminals — one for the API, one for the front-end.

**1. Start the API server**
cd server
npm install
npm start

This runs on http://localhost:4000.

**2. Start the React app**
cd client
npm install
npm run dev

This runs on http://localhost:5173 and proxies any /api/... request
through to the Express server, so the front-end always calls a relative
path (/api/recipes) rather than a hardcoded host.

## API

| Method | Route              | Description                    |
|--------|--------------------|---------------------------------|
| GET    | /api/recipes       | List all recipes               |
| GET    | /api/recipes/:id   | Get a single recipe            |
| POST   | /api/recipes       | Create a recipe                |
| PUT    | /api/recipes/:id   | Update a recipe                |
| DELETE | /api/recipes/:id   | Delete a recipe                |

Recipes are stored in server/data/recipes.json, read and written by the
route handlers in server/routes/recipes.js.
