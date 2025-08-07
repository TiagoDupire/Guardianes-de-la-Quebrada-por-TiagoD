# Peruvian Medicinal Plants Educational Game

## Overview

This is a full-stack educational game application focused on teaching users about Peruvian medicinal plants. The application features a level-based progression system where players learn about different plants native to Peru through interactive gameplay. Built with React frontend, Express backend, and PostgreSQL database using Drizzle ORM.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **UI Framework**: Tailwind CSS with Radix UI components (shadcn/ui)
- **State Management**: React hooks with custom game state management
- **Data Fetching**: TanStack Query (React Query) for server state management
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **API Structure**: RESTful API with `/api` prefix routing
- **Middleware**: Express middleware for JSON parsing, CORS, and request logging
- **Development**: Hot module replacement via Vite integration

### Database Architecture
- **Database**: PostgreSQL (configured for Neon Database)
- **ORM**: Drizzle ORM with TypeScript schema definitions
- **Migrations**: Drizzle Kit for schema management
- **Connection**: @neondatabase/serverless for database connectivity

## Key Components

### Game System
The application implements a 5-level educational progression:

1. **Level 1 (Environmental Cleanup)**: Interactive cleanup game to protect plant ecosystems
2. **Level 2 (Muña Cultivation)**: Learn about cultivating the aromatic Andean plant Muña
3. **Level 3 (Chachacoma Care)**: High-altitude plant care simulation
4. **Level 4 (Kculli Cultivation)**: Purple corn cultivation from the Colca Valley
5. **Level 5 (Final Exam)**: Knowledge assessment quiz

### State Management
- Custom React hooks for game state persistence
- Level-specific state objects with completion tracking
- Progress saving across browser sessions
- Unlock system based on level completion

### UI Components
- Responsive design using Tailwind CSS grid and flexbox
- Custom Peru-themed color palette
- Interactive game elements with hover states and animations
- Toast notifications for user feedback
- Modal dialogs for game information

## Data Flow

1. **Game Initialization**: Load saved game state from localStorage or initialize default state
2. **Level Selection**: Main menu displays available levels based on completion status
3. **Gameplay**: Each level manages its own state through custom hooks
4. **Progress Tracking**: Completion status updates global game state
5. **Persistence**: Game state automatically saves to localStorage

## External Dependencies

### Core Dependencies
- **React Ecosystem**: React, React DOM, React Query for frontend functionality
- **UI Libraries**: Radix UI primitives for accessible components
- **Styling**: Tailwind CSS for utility-first styling, class-variance-authority for component variants
- **Database**: Drizzle ORM, Neon Database serverless driver
- **Validation**: Zod for schema validation, drizzle-zod for ORM integration
- **Utilities**: clsx for conditional styling, date-fns for date operations

### Development Dependencies
- **Build Tools**: Vite with React plugin, esbuild for backend bundling
- **TypeScript**: Full TypeScript support across frontend and backend
- **Development Features**: Replit-specific plugins for development environment integration

## Deployment Strategy

### Development Environment
- Vite dev server for frontend with hot module replacement
- Express server with TypeScript execution via tsx
- Environment variables for database connection
- Replit-specific development banner and cartographer integration

### Production Build
1. **Frontend**: Vite builds React application to static assets in `dist/public`
2. **Backend**: esbuild bundles Express server to `dist/index.js`
3. **Database**: Drizzle migrations applied via `db:push` command
4. **Serving**: Express serves both API routes and static frontend assets

### File Structure
- `client/`: Frontend React application
- `server/`: Backend Express application  
- `shared/`: Shared TypeScript schemas and types
- `attached_assets/`: Game content and educational materials
- Root-level configuration files for build tools and database

The application uses a monorepo structure with clear separation between client and server code, while sharing common schemas and types through the `shared/` directory.