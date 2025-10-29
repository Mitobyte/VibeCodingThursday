# GitHub Spec-Kit Complete Guide

> Transform specifications into executable blueprints for AI-assisted development

**Official Repository:** [github.com/github/spec-kit](https://github.com/github/spec-kit)
**License:** MIT
**Stars:** 42.9k+ | **Forks:** 3.7k+

---

## Table of Contents

1. [What is Spec-Kit?](#what-is-spec-kit)
2. [Installation & Setup](#installation--setup)
3. [Core Philosophy](#core-philosophy)
4. [Six-Phase Workflow](#six-phase-workflow)
5. [Slash Commands Reference](#slash-commands-reference)
6. [File Structure & Organization](#file-structure--organization)
7. [Practical Examples](#practical-examples)
8. [Integration with AI Tools](#integration-with-ai-tools)
9. [Best Practices](#best-practices)
10. [Common Workflows](#common-workflows)
11. [Troubleshooting](#troubleshooting)

---

## What is Spec-Kit?

**Spec-Kit** is an open-source toolkit from GitHub that enables **spec-driven development**—a methodology where specifications become executable blueprints rather than static documentation.

### Key Concept

Traditional development: `Idea → Code → Documentation`
Spec-driven development: `Idea → **Specification** → Code (generated from spec)`

### Why Use Spec-Kit?

**Problem It Solves:**
- Vague prompts lead to inconsistent AI outputs
- Large projects require systematic planning
- Team collaboration needs shared understanding
- Specifications drift from implementation

**Spec-Kit Solution:**
- Structured, executable specifications
- Multi-phase development workflow
- AI agent integration with memory retention
- Systematic progression from idea to implementation

### When to Use Spec-Kit

✅ **Perfect For:**
- Mid-to-large applications (beyond simple prototypes)
- Team projects requiring documentation
- Complex features with multiple components
- Projects needing architectural planning
- 0-to-1 development (greenfield projects)
- Iterative enhancement (brownfield projects)

❌ **Not Ideal For:**
- Quick one-file scripts
- Simple UI components
- Rapid prototyping experiments
- Learning basic coding concepts

---

## Installation & Setup

### Prerequisites

**System Requirements:**
- Linux, macOS, or Windows
- Git installed
- Python 3.11+
- Supported AI coding agent

**Required Tools:**

1. **uv** (Python package manager)
   ```bash
   # macOS/Linux
   curl -LsSf https://astral.sh/uv/install.sh | sh

   # Windows (PowerShell)
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```

2. **Supported AI Agent** (choose one):
   - Claude Code
   - GitHub Copilot
   - Cursor
   - Windsurf
   - Gemini CLI
   - Qwen Code

### Installation Options

**Option 1: Persistent Installation (Recommended)**

```bash
# Install globally
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Verify installation
specify check
```

**Option 2: One-Time Use**

```bash
# Use without installing
uvx --from git+https://github.com/github/spec-kit.git specify init my-project
```

### Initialize Your First Project

```bash
# Create new project with spec-kit
specify init my-awesome-app

# Or with options
specify init my-app --ai claude --no-git

# Navigate to project
cd my-awesome-app
```

**Initialization Process:**
1. Creates project directory structure
2. Sets up `.specify/` configuration
3. Initializes git repository (unless `--no-git`)
4. Creates starter templates
5. Configures AI agent integration

### Verify Setup

```bash
# Check all requirements
specify check

# Should show:
# ✓ Python 3.11+
# ✓ Git installed
# ✓ AI agent configured
# ✓ Project structure ready
```

---

## Core Philosophy

### Spec-Driven Development Principles

**1. Intent-First Development**

Define the "what" and "why" before the "how":
- What problem does this solve?
- Why does the user need this feature?
- What are the acceptance criteria?

**2. Rich Specification Creation**

Use organizational guardrails:
- Project constitution (principles and constraints)
- Detailed user stories
- Technical requirements
- Architecture decisions

**3. Multi-Step Refinement**

Avoid single-prompt code generation:
- Phase 1: Establish principles
- Phase 2: Create specifications
- Phase 3: Plan architecture
- Phase 4: Generate tasks
- Phase 5: Implement systematically
- Phase 6: Validate and refine

**4. AI Model Reliance**

Leverage advanced AI for interpreting specs:
- AI understands context from constitution
- Generates code aligned with project principles
- Maintains consistency across features
- Adapts to project-specific patterns

### Methodology Advantages

**Compared to Direct Prompting:**

| Aspect | Direct Prompting | Spec-Kit |
|--------|------------------|----------|
| Planning | Ad-hoc | Systematic |
| Consistency | Varies | Enforced by constitution |
| Scalability | Difficult | Designed for growth |
| Team Collaboration | Challenging | Built-in documentation |
| AI Context | Per-session | Persistent memory |
| Quality Control | Manual | Structured validation |

---

## Six-Phase Workflow

### Phase 1: Establish Principles (`/speckit.constitution`)

**Purpose:** Define project governance and development guidelines

**What to Include:**
- Core values and principles
- Technology constraints
- Code style preferences
- Security requirements
- Performance goals
- Accessibility standards

**Example Constitution:**

```markdown
# Project Constitution: TaskFlow Manager

## Core Principles

1. **User Privacy First**: Never collect unnecessary data
2. **Performance**: Target <100ms API response times
3. **Accessibility**: WCAG 2.1 AA compliance minimum
4. **Simplicity**: Prefer simple solutions over clever ones

## Technology Constraints

- Backend: Node.js 20+, Express, PostgreSQL
- Frontend: React 18+, TypeScript, Tailwind CSS
- No external analytics or tracking
- Self-hostable architecture

## Code Standards

- TypeScript strict mode required
- 100% test coverage for business logic
- ESLint + Prettier enforcement
- Conventional commits

## Security Requirements

- JWT authentication with refresh tokens
- Rate limiting on all API endpoints
- Input validation with Zod
- SQL injection prevention via parameterized queries
- XSS protection via sanitization

## Performance Goals

- Lighthouse score >90 for all metrics
- Bundle size <200KB (gzipped)
- Database queries <50ms (95th percentile)
```

**Slash Command Usage:**

```bash
# In your AI agent (Claude Code, Cursor, etc.)
/speckit.constitution

# AI will guide you through creating the constitution
# Answer questions about your project principles
```

---

### Phase 2: Create Specifications (`/speckit.specify`)

**Purpose:** Define detailed requirements and user stories

**Specification Structure:**

```markdown
# Feature Specification: User Authentication

## Overview

Enable users to register, login, and manage their accounts securely.

## User Stories

### Story 1: User Registration
**As a** new user
**I want to** create an account with email and password
**So that** I can access the application

**Acceptance Criteria:**
- Email must be valid format
- Password minimum 8 characters
- Password requires: uppercase, lowercase, number
- Email verification required before login
- Duplicate email returns friendly error

### Story 2: User Login
**As a** registered user
**I want to** login with my credentials
**So that** I can access my personalized dashboard

**Acceptance Criteria:**
- Login with email and password
- "Remember me" option for 30-day session
- Failed login shows generic error (security)
- Account locked after 5 failed attempts
- Unlock via email verification

### Story 3: Password Reset
**As a** user who forgot password
**I want to** reset it via email
**So that** I can regain access to my account

**Acceptance Criteria:**
- Request reset via email address
- Receive secure reset link (1-hour expiry)
- Set new password meeting requirements
- Invalidate all existing sessions
- Confirmation email sent

## Technical Requirements

### Database Schema

**users table:**
- id (UUID, primary key)
- email (string, unique, indexed)
- password_hash (string)
- email_verified (boolean, default false)
- created_at (timestamp)
- updated_at (timestamp)

**sessions table:**
- id (UUID, primary key)
- user_id (UUID, foreign key)
- token_hash (string)
- expires_at (timestamp)
- created_at (timestamp)

### API Endpoints

- `POST /api/auth/register` - Create new user
- `POST /api/auth/login` - Authenticate user
- `POST /api/auth/logout` - Invalidate session
- `POST /api/auth/request-reset` - Request password reset
- `POST /api/auth/reset-password` - Complete password reset
- `GET /api/auth/verify-email/:token` - Verify email address

### Security Considerations

- bcrypt for password hashing (12 rounds)
- JWT tokens with RS256 signing
- HTTP-only cookies for session tokens
- CSRF protection via double-submit cookies
- Rate limiting: 5 requests/minute per IP

## Non-Functional Requirements

- Registration completes in <500ms
- Login completes in <200ms
- Email delivery within 1 minute
- Support 1000 concurrent users

## Edge Cases

- User registers with email then registers again
- User requests multiple password resets
- Email verification token expires during verification
- User changes password while logged in elsewhere
- Account lockout during active session
```

**Slash Command Usage:**

```bash
# Create specification for a feature
/speckit.specify

# AI will help structure your requirements
# Provide user stories and acceptance criteria
```

---

### Phase 3: Plan Implementation (`/speckit.plan`)

**Purpose:** Document technical architecture and implementation strategy

**Planning Document Structure:**

```markdown
# Implementation Plan: User Authentication

## Technology Stack

### Backend
- **Runtime:** Node.js 20 LTS
- **Framework:** Express 4.18
- **Database:** PostgreSQL 15
- **ORM:** Prisma 5.x
- **Validation:** Zod
- **Authentication:** jsonwebtoken, bcrypt

### Frontend
- **Framework:** React 18 with TypeScript
- **State Management:** React Context + useReducer
- **Forms:** React Hook Form + Zod
- **HTTP Client:** Axios with interceptors
- **Routing:** React Router 6

### Infrastructure
- **Hosting:** Railway (backend), Vercel (frontend)
- **Database:** Railway PostgreSQL
- **Email:** SendGrid
- **Environment:** Docker for local development

## Architecture Decisions

### Authentication Flow

1. **Registration:**
   ```
   User → Frontend Form → API Validation → Password Hash → DB Insert →
   Send Verification Email → Return Success
   ```

2. **Login:**
   ```
   User → Credentials → API Validation → Password Verify →
   Generate JWT → Set HTTP-only Cookie → Return User Data
   ```

3. **Session Management:**
   - Access token (15 min expiry, JWT)
   - Refresh token (7 day expiry, stored in DB)
   - Automatic refresh via axios interceptor

### Database Strategy

**Migration Plan:**
1. Initial migration: users table
2. Second migration: sessions table
3. Third migration: email_verification_tokens table
4. Fourth migration: password_reset_tokens table

**Indexes:**
- users.email (unique, B-tree)
- sessions.user_id (B-tree)
- sessions.expires_at (B-tree for cleanup queries)

### API Design

**RESTful Conventions:**
- Success: 200 (OK), 201 (Created)
- Client errors: 400 (Bad Request), 401 (Unauthorized), 409 (Conflict)
- Server errors: 500 (Internal Server Error)

**Response Format:**
```json
{
  "success": boolean,
  "data": object | null,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable message"
  } | null
}
```

### Error Handling

**Strategy:**
- Custom error classes for different scenarios
- Centralized error handler middleware
- Error logging with context (user_id, endpoint, timestamp)
- User-friendly error messages (no stack traces)

### Testing Strategy

**Unit Tests (Jest):**
- Password hashing functions
- Token generation/validation
- Input validation schemas
- Database models

**Integration Tests (Supertest):**
- API endpoint responses
- Database transactions
- Email sending (mocked)
- Session management

**E2E Tests (Playwright):**
- Complete registration flow
- Login and logout
- Password reset flow
- Email verification

### Security Measures

1. **Input Validation:** Zod schemas for all inputs
2. **Rate Limiting:** express-rate-limit (5 req/min)
3. **CORS:** Configured for frontend domain only
4. **Helmet.js:** Security headers
5. **SQL Injection:** Prisma ORM (parameterized queries)
6. **XSS Prevention:** Input sanitization, CSP headers

## File Structure

```
backend/
├── src/
│   ├── modules/
│   │   └── auth/
│   │       ├── auth.controller.ts
│   │       ├── auth.service.ts
│   │       ├── auth.routes.ts
│   │       ├── auth.validation.ts
│   │       └── auth.types.ts
│   ├── middleware/
│   │   ├── authenticate.ts
│   │   ├── errorHandler.ts
│   │   └── rateLimiter.ts
│   ├── utils/
│   │   ├── jwt.ts
│   │   ├── email.ts
│   │   └── crypto.ts
│   ├── prisma/
│   │   ├── schema.prisma
│   │   └── migrations/
│   └── index.ts
└── tests/
    ├── unit/
    ├── integration/
    └── e2e/

frontend/
├── src/
│   ├── features/
│   │   └── auth/
│   │       ├── components/
│   │       │   ├── LoginForm.tsx
│   │       │   ├── RegisterForm.tsx
│   │       │   └── ResetPasswordForm.tsx
│   │       ├── hooks/
│   │       │   └── useAuth.ts
│   │       ├── api/
│   │       │   └── authApi.ts
│   │       └── types/
│   │           └── auth.types.ts
│   ├── contexts/
│   │   └── AuthContext.tsx
│   └── utils/
│       └── axiosInstance.ts
```

## Implementation Phases

### Phase 1: Backend Foundation (Week 1)
- [ ] Set up Express server
- [ ] Configure Prisma with PostgreSQL
- [ ] Create database schema
- [ ] Implement password hashing utilities
- [ ] Create JWT utilities

### Phase 2: Core Auth APIs (Week 1-2)
- [ ] Registration endpoint
- [ ] Login endpoint
- [ ] Logout endpoint
- [ ] Email verification
- [ ] Password reset

### Phase 3: Frontend Components (Week 2)
- [ ] Auth context and hooks
- [ ] Login form component
- [ ] Registration form component
- [ ] Password reset form
- [ ] Protected route wrapper

### Phase 4: Integration & Testing (Week 3)
- [ ] Connect frontend to API
- [ ] Write unit tests
- [ ] Write integration tests
- [ ] E2E testing
- [ ] Security audit

### Phase 5: Deployment (Week 3)
- [ ] Set up Railway backend
- [ ] Configure environment variables
- [ ] Deploy frontend to Vercel
- [ ] Configure custom domain
- [ ] Set up monitoring

## Risks & Mitigation

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Email delivery failures | Medium | High | Use reliable provider (SendGrid), implement retry logic |
| Session hijacking | Low | Critical | HTTP-only cookies, secure flags, short expiry |
| Database performance | Medium | Medium | Proper indexing, connection pooling |
| Rate limit bypass | Low | Medium | IP-based + user-based limits, CAPTCHA for repeated failures |

## Dependencies

**Backend:**
```json
{
  "express": "^4.18.0",
  "@prisma/client": "^5.0.0",
  "bcrypt": "^5.1.0",
  "jsonwebtoken": "^9.0.0",
  "zod": "^3.22.0",
  "nodemailer": "^6.9.0",
  "express-rate-limit": "^7.0.0",
  "helmet": "^7.0.0"
}
```

**Frontend:**
```json
{
  "react": "^18.2.0",
  "react-router-dom": "^6.20.0",
  "react-hook-form": "^7.48.0",
  "axios": "^1.6.0",
  "zod": "^3.22.0",
  "@hookform/resolvers": "^3.3.0"
}
```
```

**Slash Command Usage:**

```bash
# Generate implementation plan
/speckit.plan

# AI creates technical architecture from specification
```

---

### Phase 4: Generate Tasks (`/speckit.tasks`)

**Purpose:** Break down implementation into actionable development tasks

**Task List Example:**

```markdown
# Development Tasks: User Authentication

## Backend Tasks

### Database Setup
- [ ] **TASK-001**: Install and configure Prisma
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: None
  - Acceptance: `npx prisma --version` works, connection string configured

- [ ] **TASK-002**: Create Prisma schema for users table
  - Priority: High
  - Estimate: 1 hour
  - Dependencies: TASK-001
  - Acceptance: Schema matches specification, migrations run successfully

- [ ] **TASK-003**: Create Prisma schema for sessions table
  - Priority: High
  - Estimate: 1 hour
  - Dependencies: TASK-002
  - Acceptance: Foreign key to users, proper indexes defined

### Authentication Utilities
- [ ] **TASK-004**: Implement password hashing module
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: None
  - File: `src/utils/crypto.ts`
  - Acceptance: Hash and verify functions, bcrypt rounds = 12, unit tests pass

- [ ] **TASK-005**: Implement JWT token utilities
  - Priority: High
  - Estimate: 3 hours
  - Dependencies: None
  - File: `src/utils/jwt.ts`
  - Acceptance: Generate, verify, decode functions, RS256 algorithm, unit tests pass

### API Endpoints
- [ ] **TASK-006**: Create auth service layer
  - Priority: High
  - Estimate: 4 hours
  - Dependencies: TASK-002, TASK-004, TASK-005
  - File: `src/modules/auth/auth.service.ts`
  - Acceptance: All business logic for auth operations, error handling

- [ ] **TASK-007**: Create registration endpoint
  - Priority: High
  - Estimate: 3 hours
  - Dependencies: TASK-006
  - File: `src/modules/auth/auth.controller.ts`
  - Endpoint: `POST /api/auth/register`
  - Acceptance: Input validation, returns 201, sends verification email

- [ ] **TASK-008**: Create login endpoint
  - Priority: High
  - Estimate: 3 hours
  - Dependencies: TASK-006
  - File: `src/modules/auth/auth.controller.ts`
  - Endpoint: `POST /api/auth/login`
  - Acceptance: Returns JWT, sets HTTP-only cookie, handles failures

- [ ] **TASK-009**: Create logout endpoint
  - Priority: Medium
  - Estimate: 1 hour
  - Dependencies: TASK-008
  - Endpoint: `POST /api/auth/logout`
  - Acceptance: Invalidates session, clears cookie

- [ ] **TASK-010**: Implement password reset request
  - Priority: Medium
  - Estimate: 3 hours
  - Dependencies: TASK-006
  - Endpoint: `POST /api/auth/request-reset`
  - Acceptance: Generates token, sends email, handles non-existent emails securely

- [ ] **TASK-011**: Implement password reset completion
  - Priority: Medium
  - Estimate: 2 hours
  - Dependencies: TASK-010
  - Endpoint: `POST /api/auth/reset-password`
  - Acceptance: Validates token, updates password, invalidates all sessions

### Middleware
- [ ] **TASK-012**: Create authentication middleware
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: TASK-005
  - File: `src/middleware/authenticate.ts`
  - Acceptance: Verifies JWT, attaches user to request, handles unauthorized

- [ ] **TASK-013**: Create rate limiting middleware
  - Priority: High
  - Estimate: 1 hour
  - Dependencies: None
  - File: `src/middleware/rateLimiter.ts`
  - Acceptance: 5 requests/minute, returns 429 when exceeded

## Frontend Tasks

### Context & Hooks
- [ ] **TASK-014**: Create AuthContext
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: None
  - File: `src/contexts/AuthContext.tsx`
  - Acceptance: Provides user state, login/logout/register functions

- [ ] **TASK-015**: Create useAuth hook
  - Priority: High
  - Estimate: 1 hour
  - Dependencies: TASK-014
  - File: `src/features/auth/hooks/useAuth.ts`
  - Acceptance: Returns auth context, TypeScript types correct

### API Layer
- [ ] **TASK-016**: Configure Axios instance
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: None
  - File: `src/utils/axiosInstance.ts`
  - Acceptance: Base URL configured, auth interceptor, error handling

- [ ] **TASK-017**: Create auth API functions
  - Priority: High
  - Estimate: 3 hours
  - Dependencies: TASK-016
  - File: `src/features/auth/api/authApi.ts`
  - Acceptance: All API calls typed, error handling, token refresh logic

### Components
- [ ] **TASK-018**: Create LoginForm component
  - Priority: High
  - Estimate: 4 hours
  - Dependencies: TASK-015, TASK-017
  - File: `src/features/auth/components/LoginForm.tsx`
  - Acceptance: React Hook Form, Zod validation, loading states, error display

- [ ] **TASK-019**: Create RegisterForm component
  - Priority: High
  - Estimate: 4 hours
  - Dependencies: TASK-015, TASK-017
  - File: `src/features/auth/components/RegisterForm.tsx`
  - Acceptance: Password strength indicator, email validation, success message

- [ ] **TASK-020**: Create ResetPasswordForm component
  - Priority: Medium
  - Estimate: 3 hours
  - Dependencies: TASK-015, TASK-017
  - File: `src/features/auth/components/ResetPasswordForm.tsx`
  - Acceptance: Request and complete flows, token validation

### Routing
- [ ] **TASK-021**: Create ProtectedRoute wrapper
  - Priority: High
  - Estimate: 2 hours
  - Dependencies: TASK-015
  - File: `src/components/ProtectedRoute.tsx`
  - Acceptance: Redirects to login if unauthenticated, preserves intended route

## Testing Tasks

- [ ] **TASK-022**: Unit tests for crypto utilities
  - Priority: High
  - Estimate: 2 hours
  - Coverage: >95%

- [ ] **TASK-023**: Unit tests for JWT utilities
  - Priority: High
  - Estimate: 2 hours
  - Coverage: >95%

- [ ] **TASK-024**: Integration tests for auth endpoints
  - Priority: High
  - Estimate: 4 hours
  - Coverage: All endpoints, error cases

- [ ] **TASK-025**: E2E tests for auth flows
  - Priority: Medium
  - Estimate: 6 hours
  - Coverage: Registration, login, logout, password reset

## Deployment Tasks

- [ ] **TASK-026**: Configure Railway backend deployment
  - Priority: Medium
  - Estimate: 2 hours
  - Acceptance: Auto-deploy from main branch, env vars configured

- [ ] **TASK-027**: Configure Vercel frontend deployment
  - Priority: Medium
  - Estimate: 1 hour
  - Acceptance: Auto-deploy, environment variables set

- [ ] **TASK-028**: Set up database backups
  - Priority: Low
  - Estimate: 1 hour
  - Acceptance: Daily backups to S3

## Total Estimates
- Backend: 29 hours
- Frontend: 21 hours
- Testing: 14 hours
- Deployment: 4 hours
- **Total: 68 hours (~2 weeks with buffer)**
```

**Slash Command Usage:**

```bash
# Generate actionable tasks from plan
/speckit.tasks

# AI breaks down plan into specific tasks with estimates
```

---

### Phase 5: Execute Development (`/speckit.implement`)

**Purpose:** Build features systematically according to tasks

**Implementation Workflow:**

```bash
# Start implementing a specific task
/speckit.implement TASK-001

# AI generates code for that specific task
# Follows constitution, specification, and plan
```

**Example Implementation Session:**

```
You: /speckit.implement TASK-004

AI: I'll implement the password hashing module according to the specification.

[Generates src/utils/crypto.ts]

```typescript
import bcrypt from 'bcrypt';

const SALT_ROUNDS = 12;

/**
 * Hash a plaintext password
 * @param password - Plaintext password to hash
 * @returns Hashed password
 */
export async function hashPassword(password: string): Promise<string> {
  return bcrypt.hash(password, SALT_ROUNDS);
}

/**
 * Verify a password against its hash
 * @param password - Plaintext password to verify
 * @param hash - Hashed password to compare against
 * @returns True if password matches hash
 */
export async function verifyPassword(
  password: string,
  hash: string
): Promise<boolean> {
  return bcrypt.compare(password, hash);
}
```

[Generates src/utils/__tests__/crypto.test.ts]

```typescript
import { hashPassword, verifyPassword } from '../crypto';

describe('Crypto Utilities', () => {
  describe('hashPassword', () => {
    it('should hash a password', async () => {
      const password = 'TestPassword123!';
      const hash = await hashPassword(password);

      expect(hash).toBeDefined();
      expect(hash).not.toBe(password);
      expect(hash.length).toBeGreaterThan(50);
    });

    it('should generate different hashes for same password', async () => {
      const password = 'TestPassword123!';
      const hash1 = await hashPassword(password);
      const hash2 = await hashPassword(password);

      expect(hash1).not.toBe(hash2);
    });
  });

  describe('verifyPassword', () => {
    it('should verify correct password', async () => {
      const password = 'TestPassword123!';
      const hash = await hashPassword(password);

      const isValid = await verifyPassword(password, hash);
      expect(isValid).toBe(true);
    });

    it('should reject incorrect password', async () => {
      const password = 'TestPassword123!';
      const hash = await hashPassword(password);

      const isValid = await verifyPassword('WrongPassword!', hash);
      expect(isValid).toBe(false);
    });
  });
});
```

Task TASK-004 complete. Ready for next task.
```

**Best Practices During Implementation:**

1. **One Task at a Time:** Implement tasks sequentially to maintain focus
2. **Test Immediately:** Run tests after each task completion
3. **Commit Frequently:** Commit after each task with descriptive message
4. **Review AI Code:** Always review generated code before accepting
5. **Update Documentation:** Keep comments and docs in sync with code

---

### Phase 6: Validation (`/speckit.clarify`, `/speckit.analyze`, `/speckit.checklist`)

**Purpose:** Quality assurance and refinement

**Validation Commands:**

#### `/speckit.clarify`
Ask AI to explain or clarify implementation decisions

```bash
/speckit.clarify Why did we use bcrypt with 12 rounds instead of 10?

AI: Bcrypt rounds determine computational cost. The constitution specifies
security as a top priority. 12 rounds provides strong protection against
brute-force attacks while maintaining reasonable performance (<200ms per hash).
This aligns with the performance goal of <500ms for registration.
```

#### `/speckit.analyze`
Request AI analysis of implementation quality

```bash
/speckit.analyze auth module security

AI: Security Analysis of Auth Module:

Strengths:
✓ Password hashing with bcrypt (12 rounds)
✓ JWT with RS256 algorithm
✓ HTTP-only cookies prevent XSS
✓ Rate limiting implemented
✓ Input validation with Zod

Potential Improvements:
⚠ Consider adding CAPTCHA after 3 failed login attempts
⚠ Implement account lockout notification emails
⚠ Add audit logging for security events
⚠ Consider implementing 2FA for high-risk users

Constitution Alignment: 95%
Specification Coverage: 100%
```

#### `/speckit.checklist`
Generate quality assurance checklist

```bash
/speckit.checklist pre-deployment

AI: Pre-Deployment Checklist:

Security:
- [ ] All environment variables in .env.example
- [ ] No secrets committed to repository
- [ ] HTTPS enforced in production
- [ ] CORS configured for production domain
- [ ] Rate limiting active
- [ ] SQL injection tests pass
- [ ] XSS prevention verified

Performance:
- [ ] Database indexes created
- [ ] API response times <200ms (95th percentile)
- [ ] Frontend bundle <200KB gzipped
- [ ] Lighthouse score >90

Testing:
- [ ] Unit test coverage >95%
- [ ] Integration tests pass
- [ ] E2E tests pass
- [ ] Manual QA complete

Documentation:
- [ ] README updated
- [ ] API documentation current
- [ ] Deployment guide complete
- [ ] Changelog updated
```

---

## Slash Commands Reference

### Core Commands

| Command | Purpose | Usage |
|---------|---------|-------|
| `/speckit.constitution` | Create project governance | Define principles and constraints |
| `/speckit.specify` | Write specifications | Detail requirements and user stories |
| `/speckit.plan` | Plan implementation | Document architecture and tech stack |
| `/speckit.tasks` | Generate task list | Break down into actionable items |
| `/speckit.implement` | Execute development | Build specific tasks |
| `/speckit.clarify` | Get explanations | Understand implementation decisions |
| `/speckit.analyze` | Request analysis | Review code quality and alignment |
| `/speckit.checklist` | Generate QA lists | Pre-deployment validation |

### CLI Commands

| Command | Description | Options |
|---------|-------------|---------|
| `specify init <name>` | Initialize new project | `--ai`, `--script`, `--force`, `--no-git`, `--debug` |
| `specify check` | Verify system requirements | None |
| `specify --version` | Show version | None |
| `specify --help` | Display help | None |

**CLI Options Explained:**

- `--ai [agent]` - Specify AI agent (claude, copilot, cursor, windsurf, gemini, qwen)
- `--script [sh|ps]` - Generate shell script (bash or PowerShell)
- `--force` - Overwrite existing directory
- `--no-git` - Skip git initialization
- `--debug` - Enable debug logging

---

## File Structure & Organization

### `.specify/` Directory

```
.specify/
├── memory/
│   ├── constitution.md        # Project principles
│   ├── specifications/
│   │   ├── feature-1.md      # Feature specs
│   │   ├── feature-2.md
│   │   └── ...
│   ├── plans/
│   │   ├── architecture.md   # Tech decisions
│   │   └── implementation.md
│   └── tasks/
│       ├── current-sprint.md # Active tasks
│       └── backlog.md        # Future tasks
├── templates/
│   ├── spec-template.md      # Spec template
│   └── task-template.md      # Task template
└── config.yml                # Spec-kit configuration
```

### Memory Management

**Purpose of Memory:**
- Maintains project context across sessions
- Enables AI to understand project-specific patterns
- Preserves architectural decisions
- Tracks progress and history

**What Gets Stored:**
- Constitution (project governance)
- Specifications (feature requirements)
- Plans (technical architecture)
- Tasks (implementation breakdown)
- Decisions (ADRs - Architecture Decision Records)

**Memory Best Practices:**
1. Keep memory files up-to-date
2. Review memory before major changes
3. Clean up completed tasks
4. Document important decisions
5. Use meaningful file names

---

## Practical Examples

### Example 1: Simple Todo App

**Step 1: Initialize**
```bash
specify init todo-app --ai claude
cd todo-app
```

**Step 2: Constitution**
```bash
# In Claude Code
/speckit.constitution
```

```markdown
# Todo App Constitution

## Principles
1. Simplicity: One feature at a time
2. Offline-first: Works without internet
3. Privacy: No cloud sync, local storage only

## Tech Stack
- Frontend: React + TypeScript + Tailwind
- Storage: LocalStorage
- No backend required

## Code Standards
- TypeScript strict mode
- Functional components only
- TailwindCSS for styling (no custom CSS)
```

**Step 3: Specify**
```bash
/speckit.specify
```

```markdown
# Todo App Specification

## User Stories

### Add Todo
As a user, I want to add a new todo item so that I can track tasks.

Acceptance Criteria:
- Input field for todo text
- Add button or Enter key to submit
- Todo appears in list immediately
- Input clears after adding

### Complete Todo
As a user, I want to mark todos as complete so that I can track progress.

Acceptance Criteria:
- Checkbox next to each todo
- Clicking checkbox toggles complete state
- Completed todos show strikethrough text
- State persists in localStorage

### Delete Todo
As a user, I want to delete todos so that I can remove completed or unwanted items.

Acceptance Criteria:
- Delete button (X) next to each todo
- Clicking delete removes todo immediately
- No confirmation needed (keep it simple)
```

**Step 4: Plan**
```bash
/speckit.plan
```

**Step 5: Tasks**
```bash
/speckit.tasks
```

**Step 6: Implement**
```bash
/speckit.implement TASK-001
# Continue for each task
```

---

### Example 2: Team Project - Blog Platform

**Multi-Person Workflow:**

**Developer 1 (Lead):**
```bash
# Initialize and set up constitution
specify init team-blog
cd team-blog
# In AI agent
/speckit.constitution
# Define team principles, code standards, git workflow

# Commit and push
git add .specify/
git commit -m "docs: establish project constitution"
git push origin main
```

**Developer 2:**
```bash
# Clone and review
git clone repo-url team-blog
cd team-blog
# Read .specify/memory/constitution.md
# Create feature spec
# In AI agent
/speckit.specify
# Write spec for user authentication feature

# Commit
git add .specify/memory/specifications/auth.md
git commit -m "docs: add authentication specification"
git push origin main
```

**Developer 3:**
```bash
# Pull latest
git pull origin main
# Review specs and create plan
# In AI agent
/speckit.plan
# Generate implementation plan for auth

# Commit plan
git add .specify/memory/plans/
git commit -m "docs: add authentication implementation plan"
git push origin main
```

**Developer 2 (Implementation):**
```bash
# Create feature branch
git checkout -b feature/auth

# Implement tasks
# In AI agent
/speckit.tasks  # Generate task list
/speckit.implement AUTH-001
# ... implement each task

# Commit and PR
git add src/
git commit -m "feat: implement user authentication"
git push origin feature/auth
# Create PR referencing specification
```

---

## Integration with AI Tools

### Claude Code Integration

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# In project directory
claude-code

# Use slash commands
/speckit.constitution
/speckit.specify
# etc.
```

### Cursor Integration

1. Open project in Cursor
2. Use Cmd/Ctrl + K for AI inline
3. Use Cmd/Ctrl + L for AI chat
4. Enter slash commands in chat:
   ```
   /speckit.specify
   ```

### GitHub Copilot Integration

```bash
# Install Copilot CLI
gh extension install github/gh-copilot

# Use copilot
gh copilot suggest "initialize spec-kit in this project"

# Use slash commands in supported environments
```

### Windsurf Integration

1. Open project in Windsurf
2. Open AI panel (Cmd/Ctrl + Shift + P → "AI: Open Panel")
3. Use slash commands:
   ```
   /speckit.plan
   ```

### Qwen Code Integration

```bash
# Configure Qwen Code with spec-kit
qwen-code config --spec-kit-enable

# Use in code
# Slash commands available in editor
```

---

## Best Practices

### Constitution Writing

**Do:**
✅ Be specific about technology choices
✅ Include measurable goals (performance targets, coverage %)
✅ Document security requirements clearly
✅ Reference external standards (WCAG, OWASP)
✅ Keep it concise (1-2 pages maximum)

**Don't:**
❌ Be too prescriptive about implementation details
❌ Include tasks or features (those go in specs)
❌ Use vague language ("should be fast")
❌ Contradict yourself
❌ Over-engineer for current needs

### Specification Writing

**Do:**
✅ Use "As a [user], I want [goal], so that [benefit]" format
✅ Include acceptance criteria for every story
✅ Document edge cases and error scenarios
✅ Specify API contracts and data schemas
✅ Reference constitution constraints

**Don't:**
❌ Specify implementation details (how to code it)
❌ Mix multiple features in one spec
❌ Write specs without user perspective
❌ Omit non-functional requirements
❌ Create specs without team review

### Planning Tips

**Do:**
✅ Choose technologies from constitution
✅ Document architecture decisions and rationale
✅ Create clear file structure
✅ Plan for testing from the start
✅ Estimate time and resources
✅ Identify risks and mitigation

**Don't:**
❌ Contradict the constitution
❌ Plan without considering spec requirements
❌ Skip testing strategy
❌ Over-complicate architecture
❌ Plan in isolation (get team feedback)

### Task Management

**Do:**
✅ Break down to 2-4 hour tasks
✅ Assign clear priorities (High/Medium/Low)
✅ Document dependencies between tasks
✅ Include acceptance criteria for each task
✅ Estimate time for each task
✅ Group related tasks together

**Don't:**
❌ Create massive multi-day tasks
❌ Skip dependency documentation
❌ Forget to assign priorities
❌ Create tasks without clear outcomes
❌ Over-specify implementation in task description

---

## Common Workflows

### Workflow 1: Solo Developer, New Project

```bash
Day 1: Planning
1. specify init my-project
2. /speckit.constitution (1 hour)
3. /speckit.specify (2-3 hours)
4. git commit -m "docs: initial constitution and specs"

Day 2: Architecture
1. /speckit.plan (3-4 hours)
2. /speckit.tasks (1 hour)
3. Review and refine tasks
4. git commit -m "docs: implementation plan and tasks"

Day 3-7: Development
1. /speckit.implement TASK-001
2. Implement, test, commit
3. Repeat for each task
4. git commit -m "feat: [description]" (after each task)

Day 8: Testing & Validation
1. /speckit.analyze (review quality)
2. /speckit.checklist (pre-deployment)
3. Run full test suite
4. Deploy

Day 9+: Iteration
1. New features: start with /speckit.specify
2. Maintain memory files
3. Keep constitution updated
```

### Workflow 2: Team Project

```bash
Week 1: Foundation
Lead: Initialize project, create constitution
Team: Review and provide feedback
Lead: Finalize constitution
All: git pull, read constitution

Week 2: Planning
Feature Owners: Create specifications for assigned features
Team: Review specs in pull requests
Lead: /speckit.plan for architecture
Team: Review and approve plan

Week 3: Task Breakdown
Lead: /speckit.tasks for all features
Team: Review task breakdown
All: Assign tasks to developers

Week 4+: Implementation
Developers:
  - Create feature branches
  - /speckit.implement TASK-XXX
  - Regular commits
  - Open PRs with spec references
Reviewers:
  - Check against constitution
  - Verify spec requirements met
  - /speckit.analyze for quality review
```

### Workflow 3: Adding Feature to Existing Project

```bash
Step 1: Specification
1. /speckit.specify
2. Write new feature specification
3. git add .specify/memory/specifications/new-feature.md
4. git commit -m "docs: add new feature specification"
5. Create PR for spec review

Step 2: Planning (if needed)
1. /speckit.plan (update architecture)
2. Document integration with existing code
3. Commit plan updates

Step 3: Tasks
1. /speckit.tasks (for new feature)
2. Review task dependencies with existing code
3. Commit task breakdown

Step 4: Implementation
1. Create feature branch
2. /speckit.implement for each task
3. Write tests (reference existing patterns)
4. Regular commits
5. Create PR linking to specification

Step 5: Review & Merge
1. Team reviews against spec
2. /speckit.analyze for quality check
3. Merge to main
4. Update memory files if needed
```

---

## Troubleshooting

### Common Issues

**Issue 1: "specify: command not found"**

**Solution:**
```bash
# Check if uv tools directory is in PATH
echo $PATH | grep uv

# If not, add to PATH
# macOS/Linux (.bashrc or .zshrc)
export PATH="$HOME/.local/bin:$PATH"

# Windows (PowerShell)
$env:PATH += ";$env:USERPROFILE\.local\bin"

# Or reinstall
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git --force
```

**Issue 2: AI agent doesn't recognize slash commands**

**Solutions:**
- Ensure you're using supported AI agent
- Update AI agent to latest version
- For Claude Code: ensure project has `.specify/` directory
- For Cursor: check if spec-kit extension installed
- Try typing command manually in chat

**Issue 3: Memory files not updating**

**Solutions:**
```bash
# Check .specify directory exists
ls -la .specify/

# If missing, reinitialize
specify init . --force

# Verify git tracking
git status .specify/

# If not tracked, add explicitly
git add .specify/
git commit -m "chore: track spec-kit memory"
```

**Issue 4: Task implementation deviates from specification**

**Solutions:**
- Use `/speckit.analyze` to check alignment
- Reference constitution explicitly: "Following constitution principle #3..."
- Break task into smaller subtasks
- Clarify spec if ambiguous:
  ```bash
  /speckit.clarify [specific question about spec]
  ```

**Issue 5: Overwhelming number of tasks**

**Solutions:**
- Use priority levels: focus on High priority first
- Group tasks into sprints/milestones
- Move low-priority tasks to backlog
- Simplify specification if overengineered

**Issue 6: Team members not following spec-kit workflow**

**Solutions:**
- Add workflow to constitution
- Create team onboarding guide in README
- Use PR templates requiring spec reference
- Regular team syncs to review memory files

---

## Additional Resources

### Official Documentation
- **GitHub Repository:** [github.com/github/spec-kit](https://github.com/github/spec-kit)
- **Contributing Guide:** [CONTRIBUTING.md](https://github.com/github/spec-kit/blob/main/CONTRIBUTING.md)
- **Support:** [SUPPORT.md](https://github.com/github/spec-kit/blob/main/SUPPORT.md)

### Community
- **Discussions:** [GitHub Discussions](https://github.com/github/spec-kit/discussions)
- **Issues:** [Bug Reports & Feature Requests](https://github.com/github/spec-kit/issues)
- **Pull Requests:** [Contribute to Spec-Kit](https://github.com/github/spec-kit/pulls)

### Related Tools
- **Claude Code:** [anthropic.com/claude-code](https://www.anthropic.com/claude-code)
- **GitHub Copilot:** [github.com/features/copilot](https://github.com/features/copilot)
- **Cursor:** [cursor.sh](https://cursor.sh)
- **Windsurf:** [codeium.com/windsurf](https://codeium.com/windsurf)

### Learning Resources
- Vibe Coding Thursday: Milwaukee Tech Community Events
- Spec-driven development articles and tutorials
- AI-assisted development best practices

---

## Quick Reference Card

### Essential Commands
```bash
# Initialize
specify init <project-name>

# Workflow
/speckit.constitution    # Step 1: Principles
/speckit.specify        # Step 2: Requirements
/speckit.plan           # Step 3: Architecture
/speckit.tasks          # Step 4: Breakdown
/speckit.implement      # Step 5: Build
/speckit.analyze        # Step 6: Validate

# Utilities
specify check           # Verify setup
/speckit.clarify        # Ask questions
/speckit.checklist      # QA lists
```

### File Locations
```
.specify/memory/constitution.md      # Project principles
.specify/memory/specifications/      # Feature specs
.specify/memory/plans/              # Architecture
.specify/memory/tasks/              # Task breakdown
```

### Best Practices
1. Constitution first, always
2. Specs before code
3. One task at a time
4. Commit frequently
5. Review AI outputs
6. Keep memory updated

---

**Last Updated:** October 2025
**Version:** Based on Spec-Kit latest release
**Maintainer:** Milwaukee Vibe Coding Thursday Community

**Contributions Welcome!** Submit examples, tips, and improvements via PR.
