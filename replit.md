# Overview

FahemYasta is an educational platform designed for Thanawya Amma (Egyptian high school) students. The application provides two main features: a study section where students can browse, upload, and view note packages for various subjects, and an AI chat assistant to help with academic questions. The platform supports bilingual interaction (Arabic and English) and covers core subjects including chemistry, physics, mathematics, biology, geography, history, Arabic, and English.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The client is built using **React** with **TypeScript** and follows a component-based architecture:

- **Routing**: Uses `wouter` for lightweight client-side routing with three main routes: welcome page, study section, and AI chat
- **UI Framework**: Built with **shadcn/ui** components providing a consistent design system with Radix UI primitives
- **Styling**: **Tailwind CSS** with CSS variables for theming and responsive design
- **State Management**: **TanStack Query** (React Query) for server state management, caching, and data fetching
- **Form Handling**: **React Hook Form** with **Zod** validation for type-safe form management

## Backend Architecture

The server follows an **Express.js** REST API architecture:

- **Framework**: Express.js with TypeScript for type safety
- **File Structure**: Modular design with separate routing, storage, and utility modules
- **Development Setup**: Vite integration for hot module replacement and development tooling
- **File Uploads**: Multer middleware for handling multipart form data with file validation

## Data Storage Solutions

The application uses a **PostgreSQL** database with **Drizzle ORM**:

- **Schema Design**: Two main entities - note packages and chat messages
- **ORM**: Drizzle ORM provides type-safe database operations and schema management
- **Migration System**: Drizzle Kit handles database migrations and schema evolution
- **Development Fallback**: In-memory storage implementation for development/testing scenarios

## Authentication and Authorization

Currently, the application appears to use a simple session-based approach:

- **Session Management**: Express session handling with `connect-pg-simple` for PostgreSQL session store
- **No Complex Auth**: No JWT or OAuth implementation visible, suggesting basic session authentication

## File Management

The system handles file uploads for educational materials:

- **Upload Processing**: Multer handles file uploads with size limits (10MB) and type restrictions (images, PDFs)
- **File Storage**: Local file system storage with unique filename generation
- **File Validation**: Type checking for allowed formats (JPEG, PNG, GIF, PDF)

# External Dependencies

## Database Services
- **Neon Database**: PostgreSQL hosting service (`@neondatabase/serverless`)
- **Drizzle ORM**: Database toolkit and ORM for TypeScript

## UI and Design
- **Radix UI**: Comprehensive collection of accessible UI primitives
- **Tailwind CSS**: Utility-first CSS framework
- **shadcn/ui**: Pre-built component library built on Radix UI

## Development Tools
- **Vite**: Build tool and development server with HMR
- **Replit Integration**: Development environment integration with specific plugins

## File Processing
- **Multer**: Middleware for handling multipart/form-data for file uploads

## Utility Libraries
- **date-fns**: Date manipulation and formatting
- **clsx** and **class-variance-authority**: Conditional CSS class handling
- **Zod**: Runtime type validation and schema validation

The architecture prioritizes developer experience with TypeScript throughout the stack, modern React patterns, and a clean separation between client and server concerns.