This project is the frontend for ConversAI, an NLP-powered conversational assistant designed to deliver intelligent, context-aware chat experiences. Built using Next.js, React, and TypeScript, it integrates with an advanced NLP backend for natural language understanding, response generation, and user intent recognition.

🧢 Getting Started

This project uses pnpm as the package manager via Corepack. Corepack automatically manages package managers without requiring global installations.

For architecture, conventions, data fetching, feature flags, design system usage, state management, and PR process, see CONTRIBUTING.md.

⚙️ Prerequisites

Node.js 16.10+ installed

Corepack (included with Node.js by default)

🚀 Setup
1. Enable Corepack

Run this once on your system:

corepack enable

2. Install Dependencies
pnpm i

3. Start the Development Server
Running Frontend & Backend Separately

If you are actively developing, run the backend first:

# on `conversai_platform`
docker compose --profile local up deps_backend -d
# on `conversai_platform/backend`
poetry run app


Then start the frontend:

# on `conversai_platform/frontend`
pnpm dev


Open http://localhost:3000
 in your browser to view the chatbot.
If the server starts on http://localhost:3001
, it means the frontend is already running via Docker — stop the container or run docker compose down.

You can start editing the chat UI by modifying app/page.tsx. The page will auto-update as you edit.

🐳 Running Both Frontend and Backend via Docker
# on `conversai_platform`
docker compose up -d


This spins up both frontend and backend via Docker on port 3000.

🔁 Subsequent Runs

For later development sessions, simply run:

pnpm dev


If new dependencies are added, re-install them:

pnpm i

🧩 Available Scripts
Command	Description
pnpm dev	Start development server
pnpm build	Build for production
pnpm start	Start production server
pnpm lint	Run ESLint and Prettier checks
pnpm format	Format code with Prettier
pnpm types	Run TypeScript type checking
pnpm test	Run Playwright tests
pnpm test-ui	Run Playwright tests with UI
pnpm fetch:openapi	Fetch OpenAPI spec from backend
pnpm generate:api-client	Generate API client from OpenAPI spec
pnpm generate:api	Fetch OpenAPI spec and generate API client

This project uses next/font to automatically optimize and load Inter, a custom Google Font.

🔄 Data Fetching

See CONTRIBUTING.md for guidelines on generated API hooks, SSR + hydration patterns, and usage examples.
You typically don’t need to run OpenAPI commands unless adding or modifying backend endpoints.

🚩 Feature Flags

Feature flag usage patterns, local mocks, and adding new flags are documented in CONTRIBUTING.md.

🧱 Storybook

Storybook provides a development environment to build, test, and document UI components in isolation.

Purpose in Development

Component Development: Build and test components independently.

Visual Testing: Detect visual regressions early.

Documentation: Auto-generate component documentation.

Collaboration: Share live component previews for team feedback.

Usage

Start Storybook:

pnpm storybook


Access it at http://localhost:6006
.

Build static Storybook:

pnpm build-storybook


Run Storybook tests:

pnpm test-storybook


Write .stories.tsx files alongside your components to define their various states and interactions.

🧠 Tech Stack
Core Framework & Language

Next.js – React framework with App Router

React – UI library for dynamic interfaces

TypeScript – Typed JavaScript for improved reliability

Styling & UI Components

Tailwind CSS – Utility-first styling

shadcn/ui – Reusable UI components built with Radix UI and Tailwind

Radix UI – Accessible headless UI components

Phosphor Icons – Icon set

Framer Motion – Smooth UI animations

Development & Testing

Storybook – Component documentation

Playwright – End-to-end testing

ESLint & Prettier – Code linting and formatting

Backend & Services

Supabase – Database, Auth, and Storage

Sentry – Error monitoring and performance tracking

Package Management

pnpm – Fast, efficient package manager

Corepack – Manages package managers automatically

Additional Libraries

React Hook Form – Easy form management

Zod – Type-safe schema validation

React Table – Headless table component

React Flow – Node-based diagram interactions

React Query – Data fetching and caching

React Query DevTools – Debugging tool
