# Jibi - AI-Powered Web Application Builder

## Overview
Jibi is an innovative AI-powered web application builder that transforms natural language descriptions into stunning web applications. Built with React, TypeScript, and Python, it features an elegant dark theme interface and leverages AI for intelligent code generation.

## Project Structure

### Frontend (`/frontend`)
- **Technology Stack**: React 19, TypeScript, Vite, Tailwind CSS, styled-components
- **Port**: 5000 (configured for Replit environment)
- **Features**: 
  - Modern dark theme UI with glass-morphism effects
  - React Router for navigation
  - shadcn/ui component library
  - Real-time communication via WebSocket

### Backend (`/src`)
- **Technology Stack**: Python 3.12, BAML (AI integration), Beam (cloud services)
- **Components**:
  - AI Agent for code generation (agent.py)
  - Sandbox environment tools (tools.py)
  - BAML prompts configuration (baml_src/)

## Current Setup Status

### ✅ Working
- Frontend running on port 5000
- All dependencies installed (Python + Node.js)
- Vite configured for Replit environment
- Dark theme UI with responsive design
- Routing and navigation

### ⚠️ External Dependencies Required
The backend requires external cloud services that need to be configured:

1. **Beam Cloud Service**: For AI agent hosting and sandbox environments
   - Sign up at https://beam.cloud
   - Get API tokens
   - Deploy agent: `beam serve src/agent.py:handler`

2. **OpenAI API**: For AI-powered code generation
   - Get API key from https://platform.openai.com
   - Configure in Beam: `beam secret create OPENAI_API_KEY 'your-key'`

3. **Frontend Environment Variables** (`frontend/.env`):
   ```env
   VITE_BEAM_WS_URL=your-websocket-url-from-beam
   VITE_CLOUD_TOKEN=your-cloud-token
   ```

## Development Workflow

### Running the Frontend
The frontend is automatically running via the workflow system on port 5000.
- To restart: Use the Replit workflow controls
- Hot reload is enabled for instant updates

### Making Changes
- **Frontend**: Edit files in `frontend/src/` - changes auto-reload
- **Backend**: Edit `src/agent.py` or `src/tools.py` - requires Beam redeployment
- **AI Prompts**: Edit `baml_src/build.baml` and run `make generate`

## Key Features

### Design System
- Deep black canvas (#0a0a0a) for reduced eye strain
- Subtle gradients and glass-morphism effects
- Premium typography with perfect spacing
- Smooth 60fps animations

### Architecture
- Microservices design with isolated concerns
- Real-time WebSocket communication
- Sandboxed code execution environment
- Context-aware AI code generation

## Project Branding
All references to "Lovable" have been renamed to "Jibi":
- Code references updated
- Asset files renamed (jibi-demo.gif)
- Configuration files updated
- Sandbox names changed

## Notes
- The project is set up for Replit with proper host configuration (0.0.0.0:5000)
- Backend functionality requires external Beam cloud service setup
- Frontend works standalone without backend for UI demonstration
