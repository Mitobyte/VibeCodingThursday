# Developer / Engineer Templates
## Copy-Paste Ready Prompts for Technical Roles

> **For: Software engineers, web developers, backend developers, full-stack developers**

---

## 🛠️ Full-Stack Application

```
Build a full-stack task management application with:

Frontend:
- React with TypeScript
- Tailwind CSS for styling
- React Router for navigation

Backend:
- Node.js + Express
- RESTful API endpoints
- JWT authentication
- PostgreSQL database

Features:
- User registration and login
- Create, read, update, delete tasks
- Task categories and tags
- Due dates and priorities
- Search and filter functionality

Include:
- Input validation
- Error handling
- Loading states
- Responsive design
- API documentation

Use best practices for code organization and include comments explaining key decisions.
```

---

## 🔌 REST API Service

```
Create a RESTful API for a blog platform with:

Endpoints:
- POST /api/users/register - Create new user
- POST /api/users/login - Authenticate user
- GET /api/posts - List all posts (with pagination)
- GET /api/posts/:id - Get single post
- POST /api/posts - Create new post (auth required)
- PUT /api/posts/:id - Update post (auth required)
- DELETE /api/posts/:id - Delete post (auth required)
- POST /api/posts/:id/comments - Add comment

Tech Stack:
- Node.js + Express
- MongoDB with Mongoose
- JWT for authentication
- bcrypt for password hashing

Include:
- Input validation with Joi
- Error handling middleware
- Rate limiting
- CORS configuration
- API documentation with Swagger
- Environment variables setup

Follow RESTful conventions and include Postman collection for testing.
```

---

## 🧪 Test Suite

```
Create a comprehensive test suite for a user authentication module:

Testing framework: Jest
Coverage areas:
- Unit tests for authentication functions
- Integration tests for auth endpoints
- Edge cases and error handling
- Token generation and validation
- Password hashing and comparison

Include tests for:
- Valid registration
- Duplicate email rejection
- Invalid email format
- Weak password rejection
- Successful login
- Wrong password handling
- Missing credentials
- Token expiration
- Refresh token flow

Use proper test structure with describe/it blocks, setup/teardown, and meaningful assertions.
Aim for >80% code coverage.
```

---

## 🔄 Microservice Architecture

```
Design a microservices architecture for an e-commerce platform:

Services:
1. User Service (authentication, profiles)
2. Product Service (catalog, inventory)
3. Order Service (cart, checkout)
4. Payment Service (payment processing)
5. Notification Service (emails, SMS)

For each service, define:
- API endpoints
- Database schema
- Inter-service communication
- Event-driven patterns
- Error handling strategy

Tech Stack:
- Node.js microservices
- Docker containers
- RabbitMQ for messaging
- Redis for caching
- PostgreSQL databases
- API Gateway (Express Gateway or Kong)

Include:
- Service discovery approach
- Load balancing strategy
- Logging and monitoring plan
- Deployment architecture diagram

Provide implementation for the User Service as starting point.
```

---

## 📊 Database Schema & Migrations

```
Design a database schema for a social media platform with:

Tables:
- users (id, username, email, password_hash, bio, avatar_url, created_at)
- posts (id, user_id, content, image_url, created_at, updated_at)
- comments (id, post_id, user_id, content, created_at)
- likes (id, post_id, user_id, created_at)
- follows (follower_id, following_id, created_at)
- messages (id, sender_id, receiver_id, content, read, created_at)

Include:
- Foreign key relationships
- Indexes for performance
- Migration files (up and down)
- Seed data for development
- SQL queries for common operations (get user feed, count followers, etc.)

Use PostgreSQL syntax and include comments explaining design decisions.
```

---

## 🎨 Design System Components

```
Build a reusable component library with:

Components:
- Button (variants: primary, secondary, outline, ghost)
- Input (text, email, password, with icons)
- Select dropdown
- Modal/Dialog
- Toast notifications
- Card
- Badge
- Loading spinner
- Pagination

Tech:
- React + TypeScript
- Tailwind CSS
- Storybook for documentation
- Fully accessible (ARIA labels)

Each component should:
- Accept props for customization
- Have hover/focus/active states
- Include TypeScript interfaces
- Work with keyboard navigation
- Have usage examples
- Be mobile responsive

Start with Button and Input components with full documentation.
```

---

## ⚡ Performance Optimization

```
Optimize this React application for performance:

Current issues:
- Slow initial load time
- Re-renders on every state change
- Large bundle size
- Unoptimized images

Apply these optimizations:
1. Code splitting with React.lazy() and Suspense
2. Memoization with useMemo and useCallback
3. Virtual scrolling for long lists
4. Image optimization (lazy loading, WebP format)
5. Bundle analysis and tree shaking
6. Debouncing search input
7. Caching API responses
8. Service worker for offline support

Provide before/after metrics and explain each optimization technique.
```

---

## 🔐 Authentication System

```
Implement a complete authentication system with:

Features:
- Email/password registration
- Login with JWT tokens
- Refresh token rotation
- Password reset via email
- Email verification
- OAuth (Google, GitHub)
- Two-factor authentication (TOTP)
- Session management
- Rate limiting on auth endpoints

Security:
- Password hashing with bcrypt (12 rounds)
- HTTPS only cookies
- CSRF protection
- XSS prevention
- SQL injection protection
- Input sanitization

Tech:
- Node.js + Express backend
- React frontend
- PostgreSQL database
- Redis for session storage
- Nodemailer for emails

Include error handling, validation, and security best practices.
```

---

## 🐳 Docker & DevOps Setup

```
Create a complete Docker setup for local development:

Services:
- Frontend (React dev server)
- Backend API (Node.js)
- PostgreSQL database
- Redis cache
- Nginx reverse proxy

Files needed:
- Dockerfile for frontend
- Dockerfile for backend
- docker-compose.yml
- .dockerignore
- nginx.conf

Features:
- Hot reloading for development
- Volume mounting for live code changes
- Environment variables management
- Database initialization scripts
- Health checks
- Easy one-command startup

Include:
- README with setup instructions
- Makefile for common commands
- CI/CD pipeline configuration (GitHub Actions)

Make it production-ready with multi-stage builds.
```

---

## 🔍 Search & Filtering System

```
Implement advanced search and filtering for a product catalog:

Features:
- Full-text search across product name, description, tags
- Filters: price range, categories, ratings, availability
- Sort by: price, popularity, newest, rating
- Pagination
- URL-based state (shareable links)
- Search suggestions/autocomplete
- Debounced search input
- Clear all filters button

Tech:
- React frontend
- Elasticsearch or PostgreSQL full-text search
- URL query parameters for state

Performance:
- Index products for fast search
- Efficient query composition
- Result caching
- Loading states
- Skeleton loaders

Include API endpoint design and frontend implementation.
```

---

## 📝 CLI Tool

```
Build a command-line interface tool for project scaffolding:

Functionality:
- Interactive prompts for project setup
- Template selection (React, Vue, Node API, etc.)
- Dependency installation
- Git initialization
- Environment file creation
- README generation

Commands:
- create <project-name> - Create new project
- add <component> - Add component
- deploy - Deploy to hosting
- help - Show help

Tech:
- Node.js
- Commander.js for CLI
- Inquirer.js for prompts
- Chalk for colored output
- ora for loading spinners

Include:
- Error handling
- Input validation
- Help documentation
- Version management
- NPM package setup

Make it installable via: npm install -g your-cli-tool
```

---

## 🔗 GraphQL API

```
Create a GraphQL API for a blog platform with:

Schema:
- User (id, name, email, posts)
- Post (id, title, content, author, comments, createdAt)
- Comment (id, content, author, post, createdAt)

Queries:
- user(id): User
- users: [User]
- post(id): Post
- posts(limit, offset): [Post]

Mutations:
- createUser(name, email, password): User
- updateUser(id, name): User
- createPost(title, content): Post
- deletePost(id): Boolean
- addComment(postId, content): Comment

Subscriptions:
- postAdded: Post
- commentAdded(postId): Comment

Tech:
- Apollo Server
- PostgreSQL with Sequelize
- Authentication with JWT
- DataLoader for N+1 prevention

Include:
- Resolvers with business logic
- Database models
- Authentication middleware
- Error handling
- Query complexity limiting
- GraphQL Playground setup
```

---

## 💡 Tips for Developers

**When using these templates:**
1. Replace placeholder tech stack with your preferences
2. Add specific business logic requirements
3. Specify error handling needs
4. Include performance requirements
5. Request code comments and documentation

**Make prompts better by adding:**
- "Follow SOLID principles"
- "Include TypeScript types"
- "Add JSDoc comments"
- "Include unit tests"
- "Follow [framework] best practices"
- "Make it production-ready"

**For complex projects:**
- Start with architecture design prompt
- Then use specific component prompts
- Request code reviews
- Ask for refactoring suggestions

---

## 🔗 Related Resources

- [Prompt Builder](../../event-day/PROMPT-BUILDER.md) - Customize these templates
- [Spec-Kit Guide](../../guides/SPEC-KIT-GUIDE.md) - Structured development
- [Advanced Learning Path](../../learning-paths/advanced/README.md) - Go deeper

---

*Vibe Coding Thursday | Milwaukee Tech Community*
*[Back to Templates](../README.md) | [Main Guide](../../README.md)*
