# Posture Tracker Application

## Overview
A full-stack health monitoring application that tracks posture warnings and provides AI-powered health predictions. The system combines real-time posture monitoring with predictive analytics to help users maintain better spinal health. Features include warning history tracking, health prediction dashboards, and comprehensive posture statistics. All data calculations are based on real uploaded warning images with no demo/example data.

## User Preferences
Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **UI Framework**: Radix UI components with shadcn/ui styling system
- **Styling**: Tailwind CSS with custom health-themed color variables
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Build Tool**: Vite with custom configuration for monorepo structure

The frontend follows a component-based architecture with reusable UI components. The application uses a custom design system with health-specific color schemes (health-blue, health-red, health-amber, health-green) for consistent visual feedback.

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **API Design**: RESTful endpoints for posture data retrieval
- **Development**: Hot module replacement with Vite middleware integration
- **Error Handling**: Centralized error middleware with structured JSON responses
- **Logging**: Custom request/response logging with performance metrics

The backend implements a clean separation between routing logic and data storage, making it easy to swap storage implementations.

### Data Storage Solutions
- **Database**: PostgreSQL with Drizzle ORM
- **Connection**: Neon Database serverless PostgreSQL
- **Schema Management**: Type-safe schema definitions with Drizzle-Zod integration
- **Development Mode**: In-memory storage implementation for rapid development
- **Migrations**: Drizzle Kit for database schema migrations

The storage layer uses an interface-based design pattern, allowing for both production database storage and development in-memory storage without code changes.

### Authentication and Authorization
- **Current State**: Demo user system for development
- **Session Management**: PostgreSQL session store ready for implementation
- **User Model**: Basic username/password structure in place
- **Future Ready**: Architecture supports full authentication implementation

### API Structure
The application exposes three main endpoints:
- `GET /api/warnings` - Retrieves posture warning history with filtering
- `GET /api/health-prediction` - Returns AI-generated health predictions and risk assessments
- `GET /api/stats` - Provides comprehensive posture statistics and metrics

All endpoints support optional userId parameter and return structured JSON responses with proper error handling.

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL connection for production database
- **drizzle-orm**: Type-safe SQL query builder and ORM
- **drizzle-kit**: Database migration and schema management tools

### UI and Styling
- **@radix-ui/***: Comprehensive set of headless UI components for accessibility
- **tailwindcss**: Utility-first CSS framework with custom health theme
- **class-variance-authority**: Component variant management
- **lucide-react**: Consistent icon library

### Development Tools
- **@tanstack/react-query**: Server state management and caching
- **@hookform/resolvers**: Form validation with Zod integration
- **wouter**: Lightweight routing solution
- **date-fns**: Date manipulation and formatting utilities

### Build and Development
- **vite**: Fast build tool with HMR support
- **tsx**: TypeScript execution for development server
- **esbuild**: Fast JavaScript bundler for production builds
- **@replit/vite-plugin-runtime-error-modal**: Development error overlay
- **@replit/vite-plugin-cartographer**: Replit-specific development enhancements

The application is designed to be deployed on Replit with seamless development-to-production workflow, using environment-based configuration for database connections and build processes.