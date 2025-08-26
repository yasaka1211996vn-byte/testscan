# Overview

This is an Ethereum Token Balance Scanner application built as a full-stack web application. The primary purpose is to allow users to input multiple private keys (up to ~1000) and scan their corresponding Ethereum wallet addresses for ERC-20 token balances. The application displays results in a dynamic table format with features for filtering, selecting, and exporting data. All private key processing and balance scanning occurs client-side for security.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Components**: shadcn/ui component library built on top of Radix UI primitives
- **Styling**: TailwindCSS with custom design tokens and CSS variables
- **State Management**: Custom React hooks with localStorage persistence for user preferences
- **Table Management**: TanStack Table for dynamic data display with sorting, filtering, and selection
- **Client-side Processing**: All wallet operations (private key validation, address derivation, balance scanning) happen in the browser using ethers.js

## Backend Architecture
- **Server Framework**: Express.js with TypeScript
- **Development Setup**: Vite middleware integration for hot module replacement
- **API Structure**: RESTful routes with `/api` prefix (currently minimal implementation)
- **Storage Interface**: Abstract storage layer with in-memory implementation (extensible to database)

## Data Storage Solutions
- **Client Storage**: localStorage for user preferences (exception lists, removed columns, API keys)
- **Schema Validation**: Zod schemas for type-safe data validation
- **Database Ready**: Drizzle ORM configuration with PostgreSQL dialect (Neon database integration)

## Authentication and Authorization
- **Current State**: No authentication system implemented
- **Security Model**: All sensitive operations (private keys) remain client-side only
- **API Security**: Basic Express middleware for request logging and error handling

## External Dependencies

### Blockchain Integration
- **Primary**: Alchemy API for token balance queries and metadata retrieval
- **Fallback**: Direct RPC calls via ethers.js with multicall support
- **Network**: Ethereum mainnet with configurable RPC endpoints

### Third-party Services
- **Neon Database**: PostgreSQL serverless database (configured but not actively used)
- **Replit**: Development environment integration with cartographer plugin

### Key Libraries
- **ethers.js**: Ethereum wallet operations and blockchain interaction
- **TanStack Query**: Data fetching and caching (minimal usage currently)
- **Radix UI**: Accessible component primitives
- **date-fns**: Date manipulation utilities
- **class-variance-authority**: Type-safe component variants

### Development Tools
- **TypeScript**: Full type coverage across frontend and backend
- **ESLint/Prettier**: Code quality and formatting (configured via components.json)
- **Drizzle Kit**: Database migrations and schema management
- **PostCSS**: CSS processing with Autoprefixer

The application follows a security-first approach where private keys never leave the client browser, ensuring user funds remain safe while providing comprehensive token balance analysis capabilities.