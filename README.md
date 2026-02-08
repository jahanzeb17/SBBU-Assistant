# ⚡ Quick Commands Reference

## 🚀 Setup (One-Time)

```bash
# Create React app
npx create-react-app agentic-rag-ui
cd agentic-rag-ui

# Install dependencies
npm install axios lucide-react

# Copy all provided files to their locations
# (See UI_SETUP_GUIDE.md for file list)

# Add to package.json
"proxy": "http://localhost:8000"
```

## 🏃 Running the Application

### Terminal 1: Backend

```bash
cd /path/to/backend
python main.py
```

Backend runs at: `http://localhost:8000`

### Terminal 2: Frontend

```bash
cd agentic-rag-ui
npm start
```

Frontend opens at: `http://localhost:3000`

## 📁 File Creation Checklist

Copy these files in order:

```bash
# Public
public/index.html

# Source root
src/index.js
src/index.css
src/App.jsx
src/App.css

# Services
src/services/api.js

# Hooks
src/hooks/useChat.js

# Components
src/components/Sidebar.jsx
src/components/ChatArea.jsx
src/components/MessageBubble.jsx
src/components/UploadModal.jsx
src/components/DocumentList.jsx
```

## 🧪 Quick Test Commands

```bash
# Test backend health
curl http://localhost:8000/health

# List documents
curl http://localhost:8000/list-docs

# Upload document
curl -X POST http://localhost:8000/upload-doc \
  -F "file=@test.pdf"

# Send chat message
curl -X POST http://localhost:8000/chat \
  -H "Content-Type: application/json" \
  -d '{"question": "What is in my document?"}'
```

## 🔧 Development Commands

```bash
# Start dev server
npm start

# Build for production
npm run build

# Run tests
npm test

# Serve production build
npx serve -s build
```

## 🐛 Debug Commands

```bash
# Check Node version
node --version

# Check npm version
npm --version

# Clear npm cache
npm cache clean --force

# Reinstall dependencies
rm -rf node_modules package-lock.json
npm install

# Check for missing dependencies
npm ls
```

## 📦 Production Deployment

```bash
# Build optimized version
npm run build

# Test build locally
npx serve -s build -p 3000

# Deploy (example with Netlify)
npm install -g netlify-cli
netlify deploy --prod --dir=build
```

## 🔄 Update Commands

```bash
# Update React
npm update react react-dom

# Update all dependencies
npm update

# Check outdated packages
npm outdated

# Install specific version
npm install axios@^1.6.2
```

## 🎨 Customization Quick Edits

### Change Colors
```bash
# Edit: src/App.css
# Lines: 12-20 (CSS variables)
```

### Change API URL
```bash
# Edit: src/services/api.js
# Line: 3
```

### Change Default Model
```bash
# Edit: src/services/api.js
# Line: 11
```

## 📝 Common npm Scripts

```json
{
  "start": "react-scripts start",      // Dev server
  "build": "react-scripts build",      // Production build
  "test": "react-scripts test",        // Run tests
  "eject": "react-scripts eject"       // Eject from CRA
}
```

## 🔍 Folder Structure Verification

```bash
# Check if all files exist
ls -la public/
ls -la src/
ls -la src/components/
ls -la src/services/
ls -la src/hooks/

# Count files
find src -type f | wc -l
# Should be: 11 files
```

## ⚙️ Environment Setup

```bash
# Create .env file
cat > .env << EOL
REACT_APP_API_URL=http://localhost:8000
REACT_APP_ENV=development
EOL

# Use in code
process.env.REACT_APP_API_URL
```

## 🌐 Browser Commands

```javascript
// Open browser console (F12) and run:

// Check localStorage
localStorage.getItem('chat_sessions')

// Clear sessions
localStorage.removeItem('chat_sessions')

// Check API calls
// Network tab → Filter: XHR

// React DevTools
// Components tab → Select component
```

## 🚦 Startup Sequence

```bash
# 1. Terminal 1
cd backend-folder
python main.py
# Wait for: "Application startup complete"

# 2. Terminal 2
cd agentic-rag-ui
npm start
# Wait for: "Compiled successfully!"

# 3. Browser opens automatically
# URL: http://localhost:3000
```

## 🛑 Shutdown Commands

```bash
# Stop frontend (Terminal 2)
Ctrl + C

# Stop backend (Terminal 1)
Ctrl + C

# Kill stuck processes
# Mac/Linux
lsof -ti:3000 | xargs kill -9
lsof -ti:8000 | xargs kill -9

# Windows
netstat -ano | findstr :3000
taskkill /PID <PID> /F
```

## 📊 Monitor Commands

```bash
# Watch backend logs
tail -f app.log

# Watch React build
npm start | tee build.log

# Monitor API calls
curl -w "@curl-format.txt" http://localhost:8000/health
```

## 🎯 Quick Fixes

### Fix: Port 3000 in use
```bash
# Use different port
PORT=3001 npm start
```

### Fix: Module not found
```bash
npm install
```

### Fix: Styles not loading
```bash
# Clear cache and restart
rm -rf node_modules/.cache
npm start
```

### Fix: CORS error
```bash
# Add proxy to package.json
"proxy": "http://localhost:8000"
```

## 📚 Useful Links

- **React DevTools**: Chrome/Firefox extension
- **API Testing**: http://localhost:8000/docs
- **Frontend**: http://localhost:3000
- **Build Output**: ./build folder

---

## ✅ Complete Startup Checklist

```bash
□ Backend running (port 8000)
□ Frontend running (port 3000)
□ No console errors
□ Can upload documents
□ Can send messages
□ Sessions persist
□ Tool indicators show
```

**Ready to go!** 🚀
