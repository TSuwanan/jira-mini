# Jira Mini

ระบบจัดการโปรเจกต์และงาน (Task Management System) แบบ Lightweight ที่ได้รับแรงบันดาลใจจาก Jira พัฒนาด้วย Modern Tech Stack

## Tech Stack

### Frontend
- **Next.js 16** (App Router)
- **React 19** + TypeScript
- **Tailwind CSS 4**
- **React Hook Form** + Zod (Form Validation)
- **Zustand** (State Management)
- **Lucide React** (Icons)

### Backend
- **Bun** (Runtime)
- **Elysia.js** (Web Framework)
- **PostgreSQL 14** (Database)
- **JWT** (Authentication)
- **Swagger/OpenAPI** (API Documentation)

### Infrastructure
- **Docker** + Docker Compose

## Features

- **Authentication** - JWT-based login with role-based access (Admin/User)
- **User Management** - CRUD operations for users with position and level
- **Project Management** - Create/Edit/Delete projects with team members
- **Task Management** - Full task lifecycle (Todo → In Progress → Done)
- **Task Priority** - Low, Medium, High
- **API Documentation** - Swagger UI at `/swagger`

## Quick Start

### ใช้ Docker Compose (แนะนำ)

```bash
# Clone repository
git clone <repository-url>
cd jira-mini

# Start all services
docker-compose up --build
```

Services:
- Frontend: http://localhost:3000
- API: http://localhost:8000
- Swagger Docs: http://localhost:8000/swagger

### Local Development

#### Backend

```bash
cd jira-api

# Install dependencies
bun install

# Setup environment
cp .env.example .env

# Run migrations
bun run database/migrate.ts

# Seed database (optional)
bun run database/seed.ts

# Start server
bun run dev
```

#### Frontend

```bash
cd jira-front

# Install dependencies
npm install

# Setup environment
cp .env.example .env.local

# Start server
npm run dev
```

## Project Structure

```
jira-mini/
├── jira-api/                # Backend API
│   ├── src/
│   │   ├── index.ts         # Entry point
│   │   ├── config/          # Database config
│   │   ├── routes/          # API routes
│   │   ├── controllers/     # Business logic
│   │   ├── schemas/         # Zod validation
│   │   ├── middleware/      # Auth middleware
│   │   └── utils/           # Utilities
│   └── database/
│       ├── migrations/      # DB migrations
│       └── seeders/         # Seed data
│
├── jira-front/              # Frontend
│   ├── app/                 # Next.js pages
│   │   ├── login/
│   │   ├── manage-users/
│   │   ├── manage-projects/
│   │   └── manage-tasks/
│   ├── components/          # React components
│   ├── lib/                 # API client & utils
│   └── constants/           # App constants
│
└── docker-compose.yml       # Docker orchestration
```

## API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/login` | Login |
| GET | `/api/auth/me` | Get current user |

### Users
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/users/` | List users |
| POST | `/api/users/` | Create user |
| GET | `/api/users/members` | Get members |
| DELETE | `/api/users/{id}` | Delete user |

### Projects
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/projects/` | List projects |
| POST | `/api/projects/` | Create project |
| GET | `/api/projects/{id}` | Get project |
| PUT | `/api/projects/{id}` | Update project |
| DELETE | `/api/projects/{id}` | Delete project |

### Tasks
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tasks/` | List tasks |
| POST | `/api/tasks/` | Create task |
| GET | `/api/tasks/{id}` | Get task |
| PUT | `/api/tasks/{id}` | Update task |
| DELETE | `/api/tasks/{id}` | Delete task |
| PUT | `/api/tasks/{id}/status` | Update status |

## Environment Variables

### Backend (.env)
```env
DATABASE_URL=postgresql://user:pass@host:port/dbname
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=postgres
DB_NAME=mini_jira
JWT_SECRET=your-secret-key
PORT=8000
FRONTEND_URL=http://localhost:3000
```

### Frontend (.env.local)
```env
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_FRONTEND_URL=http://localhost:3000
NODE_ENV=development
```

## Constants

### Position Codes
| Code | Description |
|------|-------------|
| DEV | Developer |
| QA | Quality Assurance |

### Level Codes
| Code | Description |
|------|-------------|
| S | Senior |
| M | Middle |
| J | Junior |

### Task Status
| Code | Description |
|------|-------------|
| T | Todo |
| I | In Progress |
| D | Done |

### Task Priority
| Code | Description |
|------|-------------|
| L | Low |
| M | Medium |
| H | High |

## Scripts

### Backend (jira-api)
```bash
bun run dev       # Development server
bun run build     # Build
bun start         # Production
```

### Frontend (jira-front)
```bash
npm run dev       # Development server
npm run build     # Build
npm start         # Production
npm run lint      # Lint check
```

## License

MIT
