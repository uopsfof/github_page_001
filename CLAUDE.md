# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an interactive treasure hunt game built with React, TypeScript, and Vite. Players click on treasure chests to discover if they contain treasure (+$100) or skeletons (-$50). The game features smooth animations using Framer Motion and a polished UI with Radix UI components and Tailwind CSS.

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (runs on http://localhost:3000)
npm run dev

# Build for production
npm run build
```

## Project Architecture

### Core Structure
- **src/App.tsx**: Main game component containing all game logic, state management, and UI
- **src/main.tsx**: Application entry point
- **src/index.css**: Global styles and Tailwind CSS imports

### Game Logic
The game state is managed through React hooks in App.tsx:
- `boxes`: Array of Box objects with id, isOpen, and hasTreasure properties
- `score`: Current player score
- `gameEnded`: Boolean indicating if game is complete

### Asset Organization
- **src/assets/**: Game images (treasure chests in various states, key cursor icon)
- **src/audios/**: Sound effects for chest opening events
- **src/components/ui/**: Reusable UI components built with Radix UI primitives

### Technology Stack
- **React 18** with TypeScript
- **Vite** for build tooling and development server
- **Framer Motion** for animations and transitions
- **Radix UI** components for accessible UI primitives
- **Tailwind CSS** for styling
- **Extensive alias configuration** in vite.config.ts for all dependencies

### Key Features
- Animated treasure chest opening with 3D flip effects
- Sound effects integration (chest_open.mp3, chest_open_with_evil_laugh.mp3)
- Responsive design with grid layouts
- Game state persistence within session
- Score tracking with positive/negative feedback

### Development Notes
- Uses SWC React plugin for fast compilation
- Build output goes to `build/` directory
- Development server auto-opens browser
- All Radix UI components have version-specific aliases configured
- Audio files are imported as modules and can be played programmatically
- Always add comments on the top of every new function in one line to summarize the usage and Must document the inputs and output parameters