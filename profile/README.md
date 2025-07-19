# Chat-App-Jkalush Organization 💬

Welcome to the **Chat-App-Jkalush** organization! This is the home of a modern, real-time chat application built with cutting-edge web technologies.

## 🚀 About This Organization

This organization houses a complete full-stack chat application ecosystem, featuring:

- **Real-time messaging** with WebSocket technology
- **Type-safe development** across the entire stack
- **Modern web architecture** with Angular and NestJS
- **Scalable and maintainable** codebase with organized namespace structure

## 📦 Repository Structure

This is a **monorepo** containing all components of the chat application:

```
chatApp/
├── backend/           # NestJS backend server
├── frontend/          # Angular frontend application
├── common/            # Shared TypeScript types and constants
└── readme.md          # This file
```

## 🛠️ Technology Stack

| Layer         | Technology           | Purpose                                 |
| ------------- | -------------------- | --------------------------------------- |
| Frontend      | Angular + TypeScript | User interface and client-side logic    |
| Backend       | NestJS + TypeScript  | Server-side API and business logic      |
| Shared        | TypeScript           | Common types, interfaces, and constants |
| Communication | Socket.IO            | Real-time bidirectional messaging       |
| Database      | MongoDB + Mongoose   | Data persistence                        |
| Development   | ESLint + Prettier    | Code quality and formatting             |

## 🚀 Quick Start

### Prerequisites

- Node.js (v16+ recommended)
- npm or yarn package manager
- MongoDB (local or cloud instance)
- Git

### Clone and Setup

```bash
# Clone the repository
git clone https://github.com/Chat-App-Jkalush/chatApp.git
cd chatApp

# Install backend dependencies
cd backend && npm install

# Install frontend dependencies
cd ../frontend && npm install

# Install shared component dependencies
cd ../common && npm install
```

### Environment Setup

Create environment files for the backend:

```bash
# backend/.env
MONGODB_URI=mongodb://localhost:27017/chatapp
JWT_SECRET=your-secret-key-here
```

### Development

```bash
# Terminal 1: Start backend server
cd backend && npm run start:dev

# Terminal 2: Start frontend application
cd frontend && npm start
```

The application will be available at:

- **Frontend**: http://localhost:4200
- **Backend**: http://localhost:3002

## ✨ Features

- 💬 **Real-time messaging** - Instant communication using Socket.IO
- 🔐 **User authentication** - Secure login and session management with JWT
- 👥 **Contact management** - Add, remove, and manage contacts
- 🏠 **Chat rooms** - Create and join group chats
- 💭 **Direct messages** - Private conversations between users
- 📱 **Responsive design** - Works seamlessly on desktop and mobile
- 🎯 **Type-safe development** - Full TypeScript support across the stack
- 🚀 **Fast and scalable** - Optimized for performance and growth
- 📦 **Modular architecture** - Clean separation of concerns

## 🏗️ Architecture Overview

### Monorepo Structure

```
┌─────────────────────┐     ┌─────────────────────┐
│   frontend/         │────▶│   backend/          │
│   (Angular)         │     │   (NestJS)          │
│                     │     │                     │
│ ┌─────────────────┐ │     │ ┌─────────────────┐ │
│ │  Components     │ │     │ │  Controllers    │ │
│ │  Services       │ │     │ │  Services       │ │
│ │  Pages          │ │     │ │  Modules        │ │
│ │  API Services   │ │     │ │  Gateways       │ │
│ └─────────────────┘ │     │ └─────────────────┘ │
└─────────────────────┘     └─────────────────────┘
         │                           │
         └───────────────────────────┘
                     │
         ┌─────────────────────┐
         │   common/           │
         │   (Shared Types)    │
         │                     │
         │ ┌─────────────────┐ │
         │ │  DTOs           │ │
         │ │  ROs            │ │
         │ │  Constants      │ │
         │ │  Enums          │ │
         │ └─────────────────┘ │
         └─────────────────────┘
```

### Backend Architecture

```
backend/src/
├── modules/
│   ├── auth/              # Authentication & authorization
│   ├── user/              # User management
│   ├── chat/              # Chat functionality & WebSocket
│   ├── message/           # Message handling
│   ├── contact/           # Contact management
│   └── userCookie/        # User session management
├── database/
│   └── schemas/           # MongoDB schemas
├── constants/             # Backend-specific constants
└── main.ts               # Application entry point
```

### Frontend Architecture

```
frontend/src/app/
├── components/
│   ├── home/              # Main chat interface
│   │   ├── navbar/        # Navigation components
│   │   └── child components/
│   │       ├── chats/     # Chat list
│   │       ├── contacts/  # Contact management
│   │       └── show-chat/ # Chat display
│   ├── login-page/        # Authentication
│   ├── register/          # User registration
│   └── not-found/         # 404 page
├── api/                   # API service layer
├── services/              # Business logic services
├── guards/                # Route guards
└── models/                # Frontend models
```

## 🔧 Shared Types Architecture

The `common/` directory contains organized, type-safe shared components:

### DTOs (Data Transfer Objects)

```typescript
import { CommonDto } from "common";

// Usage examples:
CommonDto.UserDto.RegisterDto;
CommonDto.ChatDto.CreateChatDto;
CommonDto.MessageDto.CreateMessageDto;
CommonDto.ContactDto.CreateContactDto;
```

### ROs (Response Objects)

```typescript
import { CommonRo } from "common";

// Usage examples:
CommonRo.UserRo.UserResponse;
CommonRo.ChatRo.ChatRo;
CommonRo.MessageRo.MessageResponse;
```

### Constants

```typescript
import { CommonConstants } from "common";

// Usage examples:
CommonConstants.GatewayConstants.DEFAULT_PORT;
CommonConstants.GatewayConstants.EVENTS.NEW_MESSAGE;
CommonConstants.CookiesConstants.EXPERATION_TIME_STRING;
```

## 🚀 Key Features Implementation

### Real-time Communication

- **WebSocket Gateway**: Socket.IO implementation for real-time messaging
- **Event-driven Architecture**: Structured events for different message types
- **Online Status**: Real-time user presence tracking

### Authentication System

- **JWT Tokens**: Secure session management
- **Cookie-based Storage**: HttpOnly cookies for security
- **Route Guards**: Protected routes in Angular

### Database Design

- **MongoDB**: NoSQL database for flexible data storage
- **Mongoose Schemas**: Type-safe database models
- **Indexed Fields**: Optimized queries for performance

## 📊 Development Guidelines

### Code Organization

- **Namespaces**: Organized constants, DTOs, and ROs using TypeScript namespaces
- **Type Safety**: 100% TypeScript coverage with proper typing
- **Modular Structure**: Clean separation of concerns

### Best Practices

- **Interface over Classes**: Use interfaces for data contracts (DTOs, ROs)
- **Classes for Behavior**: Use classes for services and controllers
- **Single Responsibility**: Each module has a clear, focused purpose
- **Dependency Injection**: Proper DI throughout the application

### Code Quality

- **ESLint**: Code linting and style enforcement
- **Prettier**: Consistent code formatting
- **TypeScript Strict Mode**: Maximum type safety

## 🚀 Deployment

### Development

```bash
# Backend
cd backend && npm run start:dev

# Frontend
cd frontend && npm start
```

### Production

```bash
# Build frontend
cd frontend && npm run build

# Build backend
cd backend && npm run build

# Start production
cd backend && npm run start:prod
```

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'feat: add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Development Guidelines

- Follow TypeScript best practices
- Use the established namespace structure for shared types
- Write tests for new features
- Use conventional commit messages
- Ensure code passes ESLint and Prettier checks

## 📊 Project Stats

- **Languages**: TypeScript, HTML, SCSS
- **Frameworks**: Angular 17, NestJS
- **Architecture**: Monorepo with organized shared components
- **Real-time**: Socket.IO-based communication
- **Type Safety**: 100% TypeScript coverage with strict mode
- **Database**: MongoDB with Mongoose ODM

## 👨‍💻 Author

**Jonathan Kalush**

- GitHub: [@kalush666](https://github.com/kalush666)
- Organization: [Chat-App-Jkalush](https://github.com/Chat-App-Jkalush)

## 📄 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- Angular team for the excellent frontend framework
- NestJS team for the powerful backend framework
- Socket.IO team for real-time communication
- TypeScript team for enabling type-safe JavaScript development
- MongoDB team for the flexible database solution
- Open source community for continuous inspiration

---

## Recent Updates

### v2.0 - Major Refactoring (Latest)

- ✅ **Organized Constants**: All constants now use namespace structure
- ✅ **Type-Safe DTOs**: All DTOs organized with proper TypeScript interfaces
- ✅ **Structured ROs**: All Response Objects use consistent interface patterns
- ✅ **Single Import Pattern**: Clean imports from shared modules
- ✅ **Removed `any` Types**: Full type safety across the application
- ✅ **Monorepo Structure**: Organized project layout for better maintainability

### Key Improvements

- **Better Organization**: All related types are logically grouped
- **Type Safety**: Full TypeScript support with proper typing
- **Maintainability**: Easier to find and manage types in one place
- **IntelliSense**: Better IDE support with autocomplete
- **Consistency**: Uniform structure across the entire application

The application is now production-ready with a clean, organized, and type-safe architecture! 🚀
