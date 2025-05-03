# VibeTravels

[![Node.js Version](https://img.shields.io/badge/node-23.5.0-green.svg)](https://nodejs.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Table of Contents

- [Project Description](#project-description)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Available Scripts](#available-scripts)
- [Project Scope](#project-scope)
- [Project Status](#project-status)
- [License](#license)

## Project Description

VibeTravels is a web application that transforms simplified travel notes into detailed trip plans using artificial intelligence. The application is primarily designed for young individual users or groups of friends planning domestic and international trips.

Key features include:

- User profile management with travel preferences
- AI-powered trip planning
- Note management for travel ideas
- Detailed itinerary generation
- PDF export functionality
- Rating system for generated plans

## Tech Stack

### Frontend

- [Astro](https://astro.build/) - Modern static site builder
- [React 19](https://react.dev/) - UI library
- [TypeScript 5](https://www.typescriptlang.org/) - Type-safe JavaScript
- [Tailwind CSS 4](https://tailwindcss.com/) - Utility-first CSS framework
- [Shadcn/ui](https://ui.shadcn.com/) - UI component library

### Backend

- [Supabase](https://supabase.com/) - Backend as a Service

### AI Integration

- Integration with Anthropic AI through openrouter.ai

### CI/CD and Hosting

- GitHub Actions for CI/CD
- DigitalOcean for Docker container hosting

## Getting Started

### Prerequisites

- Node.js 23.5.0 (see `.nvmrc`)
- npm or yarn package manager

### Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/vibe-travels.git
cd vibe-travels
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables:
   Create a `.env` file in the root directory and add the necessary environment variables.

4. Start the development server:

```bash
npm run dev
```

The application will be available at `http://localhost:3000`

## Available Scripts

- `npm run dev` - Start the development server
- `npm run build` - Build the application for production
- `npm run preview` - Preview the production build locally
- `npm run lint` - Run ESLint
- `npm run lint:fix` - Fix ESLint issues
- `npm run format` - Format code with Prettier

## Project Scope

### MVP Features

- User account system with basic authentication
- User profile with basic travel preferences
- Travel note management (CRUD operations)
- Detailed trip preferences input
- AI-powered trip plan generation
- Plan editing and PDF export
- Rating system for generated plans
- Support for domestic and international trips
- Plans up to 7 days
- Time zone changes consideration

### Out of Scope (Future Features)

- Plan sharing between accounts
- Rich media handling
- Advanced time and logistics planning
- Detailed currency conversion
- Custom photo and note additions
- Plan version history
- Premium subscriptions
- Booking system integrations

## Project Status

The project is currently in development. The MVP version will be free to use, with a prepared but inactive page showcasing future subscription models.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
