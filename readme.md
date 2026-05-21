# DevLog 🛠️

> A minimal, offline-first daily standup tracker for developers — log what you did, what's blocked, and what's next. Built with React + Node.js + MongoDB.

---

## What is this?

DevLog is a personal productivity tool designed specifically for developers. It replaces scattered notes, forgotten commits, and lost context with a clean daily log system modeled after the agile standup format:

- **Yesterday** — What did I work on?
- **Today** — What am I planning to do?
- **Blockers** — What's in my way?

It also tracks time spent per task, links logs to GitHub commits, and generates weekly summaries you can paste directly into team standups or performance reviews.

---

## Features

### Core
- **Daily Log Entry** — Markdown-supported input with autosave
- **Tag System** — Categorize entries by project, type (`bug`, `feature`, `review`, `meeting`), and priority
- **Timeline View** — Scroll through your history day by day
- **Streak Tracker** — Builds a habit of logging every working day
- **Weekly Summary Generator** — Auto-generates a formatted weekly report from your logs

### Developer-Focused
- **GitHub Integration** — Link log entries to commits via GitHub OAuth (optional)
- **CLI Support** — `devlog add "fixed auth bug"` from your terminal
- **Export** — Download logs as Markdown or PDF
- **Offline First** — Works without internet; syncs when connected

### UI/UX
- Clean, distraction-free editor
- Dark/light mode toggle
- Keyboard shortcuts for power users (`Ctrl+Enter` to save, `/` to search)
- Mobile-friendly responsive layout

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, Vite, Tailwind CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB (Mongoose ODM) |
| Auth | JWT (JSON Web Tokens) |
| GitHub OAuth | Passport.js |
| CLI Tool | Node.js standalone script |
| Deployment | Vercel (frontend) + Render (backend) |

---

## Project Structure

```
devlog/
├── client/                   # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Route-level page components
│   │   ├── hooks/            # Custom React hooks
│   │   ├── context/          # Auth and theme context
│   │   ├── services/         # API call functions
│   │   └── utils/            # Helper functions
│   ├── index.html
│   └── vite.config.js
│
├── server/                   # Node.js + Express backend
│   ├── controllers/          # Route handler logic
│   ├── models/               # Mongoose schemas
│   ├── routes/               # API route definitions
│   ├── middleware/            # Auth, error handling
│   ├── config/               # DB connection, env setup
│   └── index.js              # App entry point
│
├── cli/                      # Terminal CLI tool
│   └── devlog.js
│
├── docs/                     # Documentation and API reference
├── .env.example
├── .gitignore
├── package.json              # Root-level scripts (concurrently)
└── README.md
```

---

## Getting Started

### Prerequisites

- Node.js v18 or above
- MongoDB (local or Atlas URI)
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/devlog.git
cd devlog

# Install dependencies for both client and server
npm install
cd client && npm install
cd ../server && npm install
```

### Environment Setup

Create a `.env` file inside `/server` based on the provided example:

```bash
cp .env.example server/.env
```

Fill in the values:

```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/devlog
JWT_SECRET=your_secret_key_here
GITHUB_CLIENT_ID=optional
GITHUB_CLIENT_SECRET=optional
```

### Running Locally

```bash
# From the root directory — starts both client and server
npm run dev
```

- Frontend: `http://localhost:5173`
- Backend API: `http://localhost:5000`

---

## API Overview

All endpoints are prefixed with `/api`.

| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/register` | Create a new account |
| POST | `/auth/login` | Login and receive JWT |
| GET | `/logs` | Fetch all logs for the authenticated user |
| POST | `/logs` | Create a new log entry |
| PUT | `/logs/:id` | Update an existing log |
| DELETE | `/logs/:id` | Delete a log entry |
| GET | `/logs/summary/week` | Get auto-generated weekly summary |
| GET | `/tags` | Get all tags used by the user |

Full API documentation is in [`/docs/api.md`](./docs/api.md).

---

## CLI Usage

After installing globally:

```bash
npm install -g .

devlog add "Fixed login redirect bug"
devlog add "Working on dashboard redesign" --tag feature
devlog list --today
devlog summary --week
```

---

## Screenshots

> Coming soon — UI is under active development.

---

## Roadmap

- [x] Project structure and boilerplate
- [ ] Auth system (register/login with JWT)
- [ ] Log CRUD with MongoDB
- [ ] React frontend — editor + timeline
- [ ] Tag and filter system
- [ ] Weekly summary generator
- [ ] GitHub OAuth integration
- [ ] CLI tool
- [ ] Export to Markdown / PDF
- [ ] Deploy to Vercel + Render

---

## Contributing

This project is built in public. PRs and issues are welcome.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "add: your feature"`
4. Push and open a pull request

Please follow the [Conventional Commits](https://www.conventionalcommits.org/) format for commit messages.

---

## License

MIT License. See [LICENSE](./LICENSE) for details.

---

## Author

Built by **Shobhit Jain**  
[GitHub](https://github.com/jshobhit13) · [LinkedIn](https://linkedin.com/in/jshobhit13) · jshobhit8172@gmail.com
