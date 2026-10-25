# React CRUD – Book Store (MERN)

Full-stack book store CRUD application. The React front end lists books (table or card view), shows book details in a page or modal, and creates, edits and deletes books. The Node.js/Express back end stores books (title, author, publish year) in MongoDB through Mongoose.

## Tech stack

| Part | Technologies |
| --- | --- |
| `frontend/` | React 18, Vite 5, React Router 6, Tailwind CSS 3, axios, react-icons |
| `backend/` | Node.js (ES modules), Express 4, Mongoose 8, cors |
| Database | MongoDB |

## Folder structure

```text
React-CRUD-Front-Back-2/
├── backend/
│   ├── models/
│   ├── routes/
│   ├── index.js
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── conponents/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── package.json
│   ├── README.md
│   └── vite.config.js
├── .editorconfig
├── .gitignore
├── package-lock.json
├── package.json
└── README.md
```

## API endpoints (`backend/index.js`)

| Method | Path | Description |
| --- | --- | --- |
| GET | `/books` | List all books (`{ count, data }`) |
| GET | `/books/:id` | Get one book |
| POST | `/books` | Create a book (`title`, `author`, `publishYear` required) |
| PUT | `/books/:id` | Update a book |
| DELETE | `/books/:id` | Delete a book |

`backend/routes/booksRoute.js` contains an Express router version of the same endpoints, currently commented out.

## Prerequisites

- Node.js 18+ and npm
- MongoDB running locally on `mongodb://localhost:27017`

## Configuration

`backend/config.js` defines the port (`5555`) and the MongoDB connection string (`mongodb://localhost:27017/mydatabase`). The front end calls the API at `http://localhost:5555`.

## Running locally

```bash
# 1. Back end
cd backend
npm install
npm start                 # http://localhost:5555

# 2. Front end (in a second terminal, from the repository root)
npm install               # root package.json provides axios and react-icons used by the front end
cd frontend
npm install
npm run dev               # Vite dev server on http://localhost:5173 (the origin allowed by the API CORS settings)
```

Build the front end for production with `npm run build` inside `frontend/` (output in `frontend/dist`).
