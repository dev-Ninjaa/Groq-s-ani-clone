# yori AI - AI Assistant with Voice Capabilities

A modern, refactored AI assistant application featuring voice interaction, text-to-speech, and speech-to-text capabilities.

## 🚀 Features

- **Voice Interaction**: Real-time speech-to-text using AssemblyAI
- **AI Responses**: Powered by Google Gemini API
- **Text-to-Speech**: Natural voice synthesis using Murf AI
- **Video Background**: Dynamic video playback with crossfading
- **Chat Interface**: Modern, responsive chat UI
- **Configuration Management**: Easy API key management and persistence

## 🏗️ Architecture

The application has been refactored with a clean, modular architecture:

```
app/
├── config/           # Configuration and constants
│   ├── constants.js  # Application constants and configuration
│   ├── env.js        # Environment configuration loader
│   └── env.runtime.js # Runtime environment variables
├── controllers/      # Application controllers
│   └── AppController.js # Main application orchestrator
├── interfaces/       # UI interfaces
│   ├── chat.js       # Chat interface implementation
│   └── chatStyle.css # Chat interface styles
├── managers/         # Feature managers
│   ├── AudioManager.js    # Audio recording and playback
│   ├── ConfigManager.js   # Configuration and API key management
│   └── VideoManager.js    # Video playback and crossfading
├── services/         # External service integrations
│   ├── assemblyai-stt.js  # AssemblyAI speech-to-text
│   └── murf-tts.js        # Murf AI text-to-speech
├── utils/            # Utility functions
│   └── logger.js     # Centralized logging system
├── core.js           # yori AI core logic
└── main.js           # Application entry point
```

## 🛠️ Setup

### Prerequisites

- Node.js (v16 or higher)
- Modern web browser with microphone support
- API keys for:
  - Google Gemini API
  - AssemblyAI API
  - Murf AI API

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd chori-2.0
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API keys**
   
   Create a `.env` file in the root directory:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   MURF_API_KEY=your_murf_api_key_here
   ASSEMBLYAI_API_KEY=your_assemblyai_api_key_here
   ```

4. **Generate runtime configuration**
   ```bash
   npm run prestart
   ```

5. **Start the development server**
   ```bash
   npm start
   ```

6. **Open your browser**
   Navigate to `http://localhost:8080`

## 🔧 Configuration

### API Keys

The application supports three main API services:

- **Gemini API**: For AI responses and conversation
- **AssemblyAI**: For speech-to-text conversion
- **Murf AI**: For text-to-speech synthesis

API keys can be configured through:
- Environment variables (`.env` file)
- Configuration panel in the UI
- Browser localStorage (persistent)

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GEMINI_API_KEY` | Google Gemini API key | Yes |
| `MURF_API_KEY` | Murf AI API key | Yes |
| `ASSEMBLYAI_API_KEY` | AssemblyAI API key | Yes |

## 📁 Project Structure

### Core Components

- **AppController**: Main application orchestrator
- **AudioManager**: Handles microphone recording and audio playback
- **VideoManager**: Manages video playback and crossfading
- **ConfigManager**: Handles configuration and API key management
- **ChatInterface**: Provides the chat UI functionality

### Services

- **AssemblyAI STT**: Real-time speech-to-text using WebSocket
- **Murf TTS**: Text-to-speech synthesis
- **Gemini API**: AI conversation and responses

### Utilities

- **Logger**: Centralized logging with debug mode support
- **Constants**: Application-wide configuration constants

## 🎯 Usage

### Voice Interaction

1. Click the microphone button to start recording
2. Speak your message
3. Click again to stop recording
4. yori will process your speech and respond

### Text Chat

1. Open the chat interface
2. Type your message in the input field
3. Press Enter or click Send
4. yori will respond with text and voice

### Configuration

1. Click the configuration button (gear icon)
2. Enter your API keys
3. Click Save for each service
4. The status indicators will show configuration status

## 🔍 Debugging

### Debug Mode

Enable debug mode by:
- Adding `?debug=true` to the URL
- Setting `localStorage.setItem('yori_debug', 'true')`
- Running on localhost (auto-enabled)

### Console Access

The application exposes debugging information:
```javascript
// Get application status
window.yoriAI.getStatus()

// Get application controller
window.yoriAI.getController()

// Access logger
window.yoriAI.logger
```

## 🧪 Testing

Run the test suite:
```bash
# Run all tests
npm run test:all

# Run API tests only
npm run test:api

# Run runtime tests only
npm run test:run
```

## 📦 Build and Deployment

### Development
```bash
npm start
```

### Production
The application is designed to run as a static web application. Deploy the entire directory to any static hosting service.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the ISC License.

## 🐛 Troubleshooting

### Common Issues

1. **Microphone not working**
   - Check browser permissions
   - Ensure HTTPS (required for microphone access)
   - Verify microphone is not in use by other applications

2. **API key errors**
   - Verify API keys are correct
   - Check API key permissions and quotas
   - Ensure proper format for each service

3. **Audio playback issues**
   - Check browser audio settings
   - Verify TTS service is configured
   - Check network connectivity

### Support

For issues and questions:
- Check the browser console for error messages
- Enable debug mode for detailed logging
- Review API service documentation

## 🔄 Changelog

### v2.0.0 (Refactored)
- Complete architecture refactor
- Modular design with managers and controllers
- Improved error handling and logging
- Better configuration management
- Enhanced debugging capabilities
- Cleaner code organization

### v1.0.0 (Original)
- Initial release with basic functionality
- Voice interaction capabilities
- Chat interface
- Video background
