# Plugin Search Application

## Overview

A full-stack web application for searching and discovering Minecraft plugins from multiple sources (Spigot and Modrinth). The application features a modern React frontend with shadcn/ui components and an Express backend with PostgreSQL database integration. Users can search, filter, and browse plugins with advanced filtering options including platform, version compatibility, categories, and sorting preferences.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on Radix UI primitives with Tailwind CSS for styling
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Theme System**: Custom theme provider supporting light/dark modes with CSS variables
- **Component Structure**: Modular component architecture with separate UI components, business logic components, and page components

### Backend Architecture
- **Framework**: Express.js with TypeScript running on Node.js
- **API Design**: RESTful API with `/api/plugins/search` endpoint for plugin discovery
- **Data Layer**: Abstract storage interface (`IStorage`) with in-memory implementation (`MemStorage`) allowing for easy database integration
- **External API Integration**: Aggregates data from multiple plugin sources (Spigot and Modrinth APIs)
- **Development Setup**: Vite integration for hot module replacement and development server

### Database Schema
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Tables**: 
  - `plugins` table storing plugin metadata (id, name, description, author, platform, downloads, rating, versions, categories, URLs)
  - `search_queries` table for analytics and tracking user search behavior
- **Schema Validation**: Zod schemas for type-safe data validation and API contracts

### Authentication and Authorization
- Currently no authentication system implemented
- Session management infrastructure present with `connect-pg-simple` for future implementation

### Styling and Design System
- **CSS Framework**: Tailwind CSS with custom design tokens
- **Component Library**: Comprehensive shadcn/ui component library including forms, dialogs, cards, navigation, and data display components
- **Typography**: Custom font stack with Inter, DM Sans, Fira Code, and Geist Mono
- **Responsive Design**: Mobile-first approach with custom mobile detection hooks

## External Dependencies

### Core Technologies
- **Database**: PostgreSQL with Neon serverless driver (`@neondatabase/serverless`)
- **ORM**: Drizzle ORM for database operations and migrations
- **UI Components**: Radix UI primitives for accessible component foundations
- **Styling**: Tailwind CSS with PostCSS processing

### Third-party APIs
- **Modrinth API**: For fetching Minecraft mod/plugin data
- **Spigot API**: For Spigot plugin marketplace data
- External API response schemas defined with Zod for type safety

### Development Tools
- **Build System**: Vite with React plugin and TypeScript support
- **Code Quality**: ESBuild for production builds
- **Development Environment**: Replit-specific plugins for development experience
- **Asset Management**: Custom path aliases and asset resolution

### Runtime Dependencies
- **HTTP Client**: Native fetch API for external API calls
- **Date Handling**: date-fns library for date manipulation and formatting
- **State Management**: TanStack Query for server state caching and synchronization
- **Form Handling**: React Hook Form with Hookform resolvers for validation
- **Carousel/Slider**: Embla Carousel for image/content carousels