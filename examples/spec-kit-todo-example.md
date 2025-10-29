# Spec-Kit Todo App Example

> Complete walkthrough of building a todo application with GitHub Spec-Kit

**Time to Complete:** 2-3 hours
**Difficulty:** Beginner
**AI Tool:** Claude Code (or any supported agent)

---

## Prerequisites

- `uv` package manager installed
- Git initialized
- AI coding agent (Claude Code, Cursor, Windsurf, etc.)
- Basic understanding of React and TypeScript

---

## Step 1: Installation & Initialization

```bash
# Install spec-kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Verify installation
specify check

# Initialize project
specify init todo-app --ai claude
cd todo-app

# Should create:
# .specify/
# ├── memory/
# ├── templates/
# └── config.yml
```

---

## Step 2: Establish Constitution

Open your AI agent (Claude Code CLI or Cursor):

```bash
# In Claude Code
claude-code

# Use slash command
/speckit.constitution
```

**AI Prompt Conversation:**

```
AI: I'll help you establish the project constitution. Let's define the core principles and constraints for your todo app.

What are the main principles for this project?

You:
1. Simplicity: Keep it simple, one feature at a time
2. Offline-first: Works without internet connection
3. Privacy: No cloud sync, all data stays local
4. Accessibility: WCAG 2.1 AA compliance

AI: Excellent. What technology stack should we use?

You:
- Frontend: React 18 with TypeScript
- State: React Context + useReducer
- Storage: Browser LocalStorage
- Styling: Tailwind CSS
- No backend required

AI: What are your code standards and requirements?

You:
- TypeScript strict mode enabled
- Functional components only (no class components)
- Custom CSS forbidden (Tailwind only)
- 80%+ test coverage with Jest
- ESLint + Prettier enforcement
```

**Generated Constitution** (`.specify/memory/constitution.md`):

```markdown
# Todo App Constitution

## Core Principles

1. **Simplicity**: Build one feature at a time, avoid complexity
2. **Offline-First**: Application works entirely offline, no internet required
3. **Privacy**: All data stored locally, no cloud sync or analytics
4. **Accessibility**: WCAG 2.1 AA compliance minimum for all features

## Technology Stack

### Frontend
- **Framework**: React 18 with TypeScript
- **State Management**: React Context API + useReducer
- **Data Persistence**: Browser LocalStorage
- **Styling**: Tailwind CSS only (no custom CSS files)
- **Testing**: Jest + React Testing Library

### Backend
- **None**: Fully client-side application

## Code Standards

- **TypeScript**: Strict mode enabled, no `any` types
- **Components**: Functional components only, no class components
- **Styling**: Tailwind utility classes only, no custom CSS
- **Test Coverage**: Minimum 80% code coverage
- **Linting**: ESLint + Prettier enforcement on commit

## Performance Requirements

- Initial load: <1 second
- User interactions: <100ms response time
- Bundle size: <150KB gzipped

## Security

- Input sanitization to prevent XSS
- LocalStorage encryption for sensitive operations
- CSP headers in production

## Accessibility Standards

- Keyboard navigation support for all features
- Screen reader compatible
- ARIA labels where appropriate
- Color contrast ratio >= 4.5:1
```

---

## Step 3: Create Specification

```bash
/speckit.specify
```

**AI Prompt Conversation:**

```
AI: Let's define the features for your todo app. What user stories should we include?

You: I need three main features:
1. Add new todos
2. Mark todos as complete/incomplete
3. Delete todos

AI: Perfect. Let me help you write detailed user stories with acceptance criteria.
```

**Generated Specification** (`.specify/memory/specifications/todo-features.md`):

```markdown
# Todo App Feature Specification

## Overview

A simple, offline-first todo list application that allows users to track tasks with add, complete, and delete functionality.

## User Stories

### Story 1: Add Todo
**As a** user
**I want to** add a new todo item
**So that** I can track tasks I need to complete

**Acceptance Criteria:**
- Input field visible at top of todo list
- "Add" button or Enter key submits new todo
- Todo text minimum 1 character, maximum 280 characters
- New todo appears at top of list
- Input field clears after adding
- Focus returns to input field after adding
- Empty input shows validation error
- Duplicate todos are allowed

**Edge Cases:**
- Very long todo text (280 char limit)
- Special characters in todo text
- Whitespace-only input (rejected)
- Adding todo while list is empty

### Story 2: Complete Todo
**As a** user
**I want to** mark todos as complete or incomplete
**So that** I can track my progress

**Acceptance Criteria:**
- Checkbox appears next to each todo
- Clicking checkbox toggles complete state
- Completed todos show strikethrough text
- Completed todos visually distinct (opacity/color)
- State persists in LocalStorage
- Keyboard accessible (Space key toggles)

**Edge Cases:**
- Rapidly toggling completion state
- Completing last incomplete todo
- Un-completing completed todo

### Story 3: Delete Todo
**As a** user
**I want to** delete todos
**So that** I can remove completed or unwanted items

**Acceptance Criteria:**
- Delete button (X icon) appears on hover
- Clicking delete removes todo immediately
- No confirmation dialog (keeps it simple)
- Deleted todos removed from LocalStorage
- Keyboard accessible (Delete key when focused)
- Visual feedback on hover

**Edge Cases:**
- Deleting last todo in list
- Deleting while list is empty (N/A)
- Rapid deletion of multiple todos
- Deleting currently focused todo

## Technical Requirements

### Data Model

```typescript
interface Todo {
  id: string; // UUID
  text: string; // 1-280 characters
  completed: boolean;
  createdAt: number; // Unix timestamp
}
```

### LocalStorage Schema

```typescript
// Key: "todos"
// Value: JSON string of Todo[]
localStorage.setItem('todos', JSON.stringify(todos));
```

### Component Structure

```
App
├── TodoInput (add new todos)
├── TodoList (display all todos)
│   └── TodoItem (individual todo)
│       ├── Checkbox (toggle complete)
│       ├── Text (todo content)
│       └── DeleteButton (remove todo)
└── TodoStats (optional: count, completed/total)
```

## Non-Functional Requirements

- Load todos from LocalStorage on mount
- Save todos to LocalStorage on every change
- Debounce LocalStorage writes (300ms)
- Accessible to screen readers
- Keyboard navigation support
- Mobile responsive (down to 320px width)

## Out of Scope (Future Iterations)

- Editing existing todos
- Categories or tags
- Due dates
- Priority levels
- Search/filter functionality
- Cloud sync
```

---

## Step 4: Plan Implementation

```bash
/speckit.plan
```

**Generated Plan** (`.specify/memory/plans/implementation.md`):

```markdown
# Todo App Implementation Plan

## Technology Setup

### Project Structure

```
todo-app/
├── src/
│   ├── components/
│   │   ├── TodoInput.tsx
│   │   ├── TodoList.tsx
│   │   ├── TodoItem.tsx
│   │   └── TodoStats.tsx
│   ├── hooks/
│   │   └── useTodos.ts
│   ├── types/
│   │   └── todo.ts
│   ├── utils/
│   │   └── storage.ts
│   ├── App.tsx
│   └── index.tsx
├── tests/
│   ├── components/
│   └── hooks/
├── tailwind.config.js
├── tsconfig.json
└── package.json
```

### Dependencies

```json
{
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "uuid": "^9.0.0"
  },
  "devDependencies": {
    "@types/react": "^18.2.0",
    "@types/uuid": "^9.0.0",
    "typescript": "^5.0.0",
    "vite": "^5.0.0",
    "tailwindcss": "^3.4.0",
    "@testing-library/react": "^14.0.0",
    "@testing-library/jest-dom": "^6.0.0",
    "jest": "^29.0.0",
    "eslint": "^8.0.0",
    "prettier": "^3.0.0"
  }
}
```

## Implementation Strategy

### Phase 1: Core Data Layer
1. Create TypeScript types
2. Implement LocalStorage utilities
3. Create useTodos hook for state management

### Phase 2: Component Development
1. Build TodoInput component
2. Build TodoItem component
3. Build TodoList component
4. Build TodoStats component (optional)

### Phase 3: App Integration
1. Wire up components in App.tsx
2. Implement LocalStorage persistence
3. Add keyboard shortcuts

### Phase 4: Styling & Accessibility
1. Apply Tailwind styles
2. Add ARIA labels
3. Test keyboard navigation
4. Test screen reader compatibility

### Phase 5: Testing
1. Unit tests for utils and hooks
2. Component tests for all components
3. Integration test for full flow
4. Accessibility testing

## State Management Architecture

### useTodos Hook

```typescript
interface TodoState {
  todos: Todo[];
  addTodo: (text: string) => void;
  toggleTodo: (id: string) => void;
  deleteTodo: (id: string) => void;
}

function useTodos(): TodoState {
  // Implementation using useReducer + useEffect for persistence
}
```

### Reducer Actions

```typescript
type TodoAction =
  | { type: 'ADD'; payload: { text: string } }
  | { type: 'TOGGLE'; payload: { id: string } }
  | { type: 'DELETE'; payload: { id: string } }
  | { type: 'LOAD'; payload: { todos: Todo[] } };
```

## Error Handling

- LocalStorage quota exceeded: Show warning, oldest todos removed
- LocalStorage unavailable: Warn user, use in-memory state
- Invalid stored data: Clear and start fresh

## Testing Strategy

### Unit Tests
- `storage.ts`: saveTodos, loadTodos, clearTodos
- `useTodos`: All actions and state updates

### Component Tests
- TodoInput: Renders, validates input, calls addTodo
- TodoItem: Displays todo, toggles, deletes
- TodoList: Renders list, empty state
- TodoStats: Displays correct counts

### Integration Tests
- Add todo → appears in list → persists
- Toggle todo → updates visually → persists
- Delete todo → removes from list → persists

## Performance Optimizations

- Debounce LocalStorage writes (300ms)
- useMemo for computed values (completed count)
- useCallback for stable function references
- React.memo for TodoItem to prevent unnecessary re-renders

## Accessibility Implementation

- Semantic HTML (main, section, button)
- ARIA labels for all interactive elements
- Focus management (auto-focus input after actions)
- Keyboard shortcuts:
  - Enter: Add todo
  - Space: Toggle checkbox
  - Delete: Remove focused todo
  - Tab: Navigate between items
```

---

## Step 5: Generate Tasks

```bash
/speckit.tasks
```

**Generated Tasks** (`.specify/memory/tasks/implementation-tasks.md`):

```markdown
# Todo App Implementation Tasks

## Phase 1: Project Setup & Types (1 hour)

- [ ] **TASK-001**: Initialize Vite + React + TypeScript project
  - Priority: High
  - Estimate: 15 minutes
  - Command: `npm create vite@latest . -- --template react-ts`
  - Acceptance: Project runs with `npm run dev`

- [ ] **TASK-002**: Install and configure Tailwind CSS
  - Priority: High
  - Estimate: 15 minutes
  - Dependencies: TASK-001
  - Acceptance: Tailwind classes work in components

- [ ] **TASK-003**: Create TypeScript types
  - Priority: High
  - Estimate: 15 minutes
  - File: `src/types/todo.ts`
  - Acceptance: Todo interface defined with id, text, completed, createdAt

- [ ] **TASK-004**: Set up ESLint and Prettier
  - Priority: Medium
  - Estimate: 15 minutes
  - Acceptance: `npm run lint` passes, Prettier formats on save

## Phase 2: Storage & State (2 hours)

- [ ] **TASK-005**: Implement LocalStorage utilities
  - Priority: High
  - Estimate: 30 minutes
  - Dependencies: TASK-003
  - File: `src/utils/storage.ts`
  - Acceptance: saveTodos, loadTodos, clearTodos functions work

- [ ] **TASK-006**: Create useTodos hook with useReducer
  - Priority: High
  - Estimate: 1 hour
  - Dependencies: TASK-003, TASK-005
  - File: `src/hooks/useTodos.ts`
  - Acceptance: All CRUD operations work, state persists

- [ ] **TASK-007**: Write tests for storage utilities
  - Priority: High
  - Estimate: 30 minutes
  - Dependencies: TASK-005
  - Coverage: >90%

## Phase 3: Components (3 hours)

- [ ] **TASK-008**: Create TodoInput component
  - Priority: High
  - Estimate: 45 minutes
  - Dependencies: TASK-006
  - File: `src/components/TodoInput.tsx`
  - Acceptance: Renders input, validates, calls addTodo, clears on submit

- [ ] **TASK-009**: Create TodoItem component
  - Priority: High
  - Estimate: 45 minutes
  - Dependencies: TASK-006
  - File: `src/components/TodoItem.tsx`
  - Acceptance: Displays todo, checkbox works, delete button works

- [ ] **TASK-010**: Create TodoList component
  - Priority: High
  - Estimate: 30 minutes
  - Dependencies: TASK-009
  - File: `src/components/TodoList.tsx`
  - Acceptance: Renders list of TodoItems, shows empty state

- [ ] **TASK-011**: Create TodoStats component (optional)
  - Priority: Low
  - Estimate: 30 minutes
  - Dependencies: TASK-006
  - File: `src/components/TodoStats.tsx`
  - Acceptance: Shows total and completed count

- [ ] **TASK-012**: Wire components in App.tsx
  - Priority: High
  - Estimate: 30 minutes
  - Dependencies: TASK-008, TASK-010
  - File: `src/App.tsx`
  - Acceptance: Full app works, persistence active

## Phase 4: Styling & Polish (2 hours)

- [ ] **TASK-013**: Apply Tailwind styling to TodoInput
  - Priority: Medium
  - Estimate: 30 minutes
  - Dependencies: TASK-008
  - Acceptance: Matches design, responsive

- [ ] **TASK-014**: Apply Tailwind styling to TodoItem
  - Priority: Medium
  - Estimate: 30 minutes
  - Dependencies: TASK-009
  - Acceptance: Strikethrough on complete, hover states

- [ ] **TASK-015**: Apply Tailwind styling to TodoList
  - Priority: Medium
  - Estimate: 30 minutes
  - Dependencies: TASK-010
  - Acceptance: List layout, empty state styled

- [ ] **TASK-016**: Add keyboard shortcuts
  - Priority: Medium
  - Estimate: 30 minutes
  - Dependencies: TASK-012
  - Acceptance: Enter, Space, Delete keys work

## Phase 5: Accessibility (1 hour)

- [ ] **TASK-017**: Add ARIA labels to all interactive elements
  - Priority: High
  - Estimate: 30 minutes
  - Acceptance: Screen reader announces all actions

- [ ] **TASK-018**: Implement focus management
  - Priority: Medium
  - Estimate: 30 minutes
  - Acceptance: Focus returns to input after actions

## Phase 6: Testing (2 hours)

- [ ] **TASK-019**: Write component tests for TodoInput
  - Priority: High
  - Estimate: 30 minutes
  - Coverage: >80%

- [ ] **TASK-020**: Write component tests for TodoItem
  - Priority: High
  - Estimate: 30 minutes
  - Coverage: >80%

- [ ] **TASK-021**: Write component tests for TodoList
  - Priority: High
  - Estimate: 30 minutes
  - Coverage: >80%

- [ ] **TASK-022**: Write integration tests
  - Priority: High
  - Estimate: 30 minutes
  - Acceptance: Full user flow tested

## Total Estimate: 11 hours (1.5 days)
```

---

## Step 6: Implement Tasks

```bash
# Implement tasks one by one
/speckit.implement TASK-001
```

**Example Implementation:**

```
AI: I'll implement TASK-001: Initialize Vite + React + TypeScript project

[Runs commands]
npm create vite@latest . -- --template react-ts
npm install

[Verifies]
Starting dev server...
✓ Project initialized successfully
✓ Dev server running at http://localhost:5173

Task TASK-001 complete. Proceed to TASK-002?

You: Yes, continue

AI: Implementing TASK-002: Install and configure Tailwind CSS
[Continues...]
```

**Continue for all tasks sequentially**

---

## Step 7: Testing & Validation

```bash
# Analyze implementation
/speckit.analyze

# Generate QA checklist
/speckit.checklist
```

**Example Analysis:**

```
AI: Implementation Analysis:

Constitution Alignment: 100%
✓ TypeScript strict mode enabled
✓ Functional components only
✓ Tailwind CSS for all styling
✓ LocalStorage for persistence
✓ No backend dependencies

Specification Coverage: 100%
✓ All user stories implemented
✓ All acceptance criteria met
✓ Edge cases handled

Test Coverage: 85%
✓ Exceeds 80% requirement

Performance:
✓ Initial load: 0.8s (target: <1s)
✓ Interaction response: 45ms (target: <100ms)
✓ Bundle size: 142KB gzipped (target: <150KB)

Accessibility:
✓ ARIA labels present
✓ Keyboard navigation works
✓ Screen reader compatible
✓ Color contrast: 5.2:1 (target: >=4.5:1)

Recommendations:
- Add error boundary for production
- Consider adding undo functionality
- Document keyboard shortcuts in UI
```

---

## Final Result

**Running Application:**

```bash
npm run dev
# Opens http://localhost:5173

# Features:
# - Add todo with input field
# - Check boxes to mark complete
# - X button to delete
# - Persists in LocalStorage
# - Fully keyboard accessible
# - Screen reader compatible
```

**File Structure:**

```
todo-app/
├── .specify/
│   └── memory/
│       ├── constitution.md
│       ├── specifications/
│       ├── plans/
│       └── tasks/
├── src/
│   ├── components/
│   │   ├── TodoInput.tsx
│   │   ├── TodoList.tsx
│   │   └── TodoItem.tsx
│   ├── hooks/
│   │   └── useTodos.ts
│   ├── types/
│   │   └── todo.ts
│   ├── utils/
│   │   └── storage.ts
│   └── App.tsx
└── tests/
```

---

## Next Steps

1. **Deploy** to Vercel/Netlify
2. **Add Features** (editing, categories, due dates)
3. **Share** with Vibe Coding Thursday community
4. **Learn** from the spec-kit memory files

---

## Key Takeaways

✅ **Spec-Kit Benefits:**
- Systematic development process
- AI maintains consistency
- Built-in documentation
- Easy team collaboration

✅ **Best Practices:**
- Constitution prevents scope creep
- Specifications guide implementation
- Tasks break down complexity
- Validation ensures quality

✅ **Time Saved:**
- No architectural debates
- Consistent code patterns
- Comprehensive testing from start
- Documentation generated automatically

---

**Total Time:** 2-3 hours from zero to deployed todo app!
**Learn More:** [Complete Spec-Kit Guide](../docs/SPEC-KIT-GUIDE.md)
