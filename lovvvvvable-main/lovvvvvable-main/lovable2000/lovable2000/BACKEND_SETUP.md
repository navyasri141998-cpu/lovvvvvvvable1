# Backend Setup Instructions

## Overview
The Jibi backend requires external cloud services to function. The frontend is fully operational in Replit, but to enable the full AI-powered code generation features, you'll need to set up the following services.

## Required Services

### 1. Beam Cloud Platform
Beam provides the cloud infrastructure for:
- AI agent hosting
- Sandboxed code execution environments
- Real-time WebSocket communication

**Setup Steps:**
1. Sign up at https://beam.cloud
2. Install Beam CLI: `pip install beam-sdk`
3. Login: `beam login`
4. Get your API token from https://platform.beam.cloud/settings/api-keys

### 2. OpenAI API
Required for AI-powered code generation.

**Setup Steps:**
1. Create account at https://platform.openai.com
2. Generate API key at https://platform.openai.com/api-keys
3. Add to Beam secrets: `beam secret create OPENAI_API_KEY 'your-openai-api-key'`

### 3. Deploy Backend Agent

Once you have Beam configured:

```bash
beam serve src/agent.py:handler
```

This will output a WebSocket URL that you'll need for the frontend.

### 4. Configure Frontend Environment

Create `frontend/.env` with:

```env
VITE_BEAM_WS_URL=wss://your-agent-url-from-beam.beam.cloud
VITE_CLOUD_TOKEN=your-beam-token
```

### 5. Restart Frontend

After configuring the environment variables, restart the frontend workflow to enable full functionality.

## Architecture

### Components:
- **Frontend** (Replit) → User interface, runs standalone
- **Backend Agent** (Beam Cloud) → AI code generation, requires Beam
- **Sandbox** (Beam Cloud) → Isolated React app execution
- **AI Service** (OpenAI) → Natural language processing

### Data Flow:
```
User Input → Frontend → WebSocket → Beam Agent → OpenAI → Code Generation
                                  ↓
                              Sandbox Environment → Live Preview
```

## Current Status

✅ **Working in Replit:**
- Frontend UI with full routing
- Dark theme interface
- Component library and styling
- Static pages and navigation

⚠️ **Requires External Setup:**
- AI-powered code generation
- Real-time WebSocket communication
- Sandboxed code execution
- Live app preview functionality

## Alternative: Frontend-Only Mode

The frontend can demonstrate the UI/UX without backend functionality:
- Browse the landing page
- View the elegant dark theme design
- Navigate between routes
- Experience the user interface

For full functionality, follow the backend setup steps above.

## Cost Considerations

- **Beam**: Free tier available, pay-as-you-go for additional usage
- **OpenAI**: Pay per API call, costs vary by model (GPT-4 recommended)

## Support

For issues with:
- **Replit Setup**: This environment is fully configured
- **Beam Setup**: Visit https://docs.beam.cloud
- **OpenAI Setup**: Visit https://platform.openai.com/docs
