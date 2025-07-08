# FlavorFusion - Recipe Discovery Platform

## Overview

FlavorFusion is a full-stack recipe discovery and management platform built with a modern tech stack. The application allows users to browse, search, and discover recipes from various cuisines and categories, with features tailored to different lifestyle needs (healthy eating, quick meals, protein-rich, etc.).

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with custom design tokens and variables
- **State Management**: TanStack Query (React Query) for server state management
- **Build Tool**: Vite with custom configuration for development and production

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (@neondatabase/serverless)
- **API Pattern**: RESTful API design
- **Session Management**: PostgreSQL-based sessions (connect-pg-simple)

### Development Architecture
- **Monorepo Structure**: Shared types and schemas across client/server
- **Hot Reload**: Vite middleware integration for development
- **Build Process**: Separate client (Vite) and server (esbuild) builds

## Key Components

### Database Schema (`shared/schema.ts`)
- **Users Table**: Authentication and user management
- **Recipes Table**: Comprehensive recipe data including nutritional flags, ratings, and metadata
- **Categories Table**: Recipe categorization with emojis and descriptions
- **Zod Integration**: Runtime validation using drizzle-zod

### Storage Layer (`server/storage.ts`)
- **Interface-based Design**: `IStorage` interface for data operations
- **In-Memory Implementation**: `MemStorage` class for development/demo
- **Recipe Operations**: CRUD operations, search, filtering by category/tags
- **User Management**: User creation and authentication helpers

### Frontend Pages
- **Home Page**: Hero section, featured recipes, lifestyle categories
- **Recipes Page**: Browse all recipes with search and filtering
- **Recipe Detail**: Individual recipe view with full details
- **Categories**: Browse recipes by cuisine categories
- **My Recipes**: Personal recipe management (placeholder)

### UI Component System
- **Design System**: Custom color palette with warm-orange, golden-yellow, fresh-green themes
- **Responsive Design**: Mobile-first approach with breakpoint-based layouts
- **Accessibility**: Radix UI primitives ensure ARIA compliance
- **Custom Components**: Recipe cards, category cards, navigation, footer

## Data Flow

1. **Client Request**: User interactions trigger API calls via TanStack Query
2. **Server Processing**: Express routes handle requests and interact with storage layer
3. **Database Operations**: Storage interface abstracts database operations
4. **Response Caching**: TanStack Query handles client-side caching and synchronization
5. **UI Updates**: React components re-render based on query state changes

### Search and Filtering Flow
- Search queries are handled via URL parameters
- Server-side filtering by category, tags, and search terms
- Client-side filtering for cuisine type and cooking time
- Real-time search suggestions and category-based navigation

## External Dependencies

### Core Dependencies
- **Database**: Neon PostgreSQL with Drizzle ORM
- **UI Framework**: Radix UI component primitives
- **State Management**: TanStack Query for server state
- **Validation**: Zod for runtime type checking
- **Styling**: Tailwind CSS with PostCSS processing

### Development Dependencies
- **Build Tools**: Vite, esbuild, TypeScript
- **Code Quality**: ESLint configuration (implied)
- **Development Experience**: Replit-specific plugins and hot reload

### External Services
- **Database Hosting**: Neon Database (PostgreSQL-compatible)
- **Asset Management**: Image URLs (external hosting assumed)
- **Fonts**: Google Fonts (Poppins, Inter)

## Deployment Strategy

### Production Build
- **Client Build**: Vite builds static assets to `dist/public`
- **Server Build**: esbuild bundles server code to `dist/index.js`
- **Environment**: Node.js production server with static file serving

### Development Environment
- **Hot Reload**: Vite dev server integrated with Express
- **Database**: Neon PostgreSQL with connection pooling
- **Environment Variables**: `DATABASE_URL` for database connection

### Database Migration
- **Schema Management**: Drizzle Kit for database migrations
- **Migration Files**: Generated to `./migrations` directory
- **Deployment**: `db:push` command for schema synchronization

## Changelog

```
Changelog:
- July 08, 2025. Initial setup
- July 08, 2025. Completed user authentication system with bcrypt password hashing and session management
- July 08, 2025. Implemented visitor tracking for website analytics
- July 08, 2025. Integrated Google AdSense for monetization with banner, sidebar, and in-content ad components
- July 08, 2025. Added authentication UI components (login/register dialogs) with form validation
- July 08, 2025. Created protected My Recipes page with save/unsave functionality
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```