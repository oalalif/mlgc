# MLGC - Frontend Application

A responsive web application for skin disease classification, built with modern web technologies and designed for optimal user experience.

## 🎨 Features

- **Drag & Drop Interface**: Intuitive image upload with drag and drop support
- **Real-time Feedback**: Live preview of uploaded images
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Prediction Results**: Clear display of classification results
- **History Tracking**: View previous predictions
- **Progressive Web App**: Works offline after first load
- **Accessibility**: Built with WCAG 2.1 standards

## 🏗 Project Structure

```
frontend/
├── public/                 # Static files
│   ├── favicon.png         # Browser tab icon
│   └── index.html          # Main HTML file
├── src/
│   ├── images/            # Image assets
│   │   ├── bg.png         # Background image
│   │   └── waiting.svg    # Loading animation
│   │
│   ├── scripts/           # JavaScript modules
│   │   ├── api.js        # API service layer
│   │   ├── main.js       # Main application logic
│   │   └── utils.js      # Utility functions
│   │
│   └── styles/            # CSS stylesheets
│       ├── styles.css    # Main styles
│       └── responsive.css # Responsive design
├── .gitignore            # Git ignore rules
├── app.yaml             # Google App Engine config
└── package.json         # Project configuration
```

## 🚀 Quick Start

### Prerequisites

- Node.js v14+ and npm
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/mlgc.git
   cd mlgc
   git checkout frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn
   ```

3. **Configure environment**
   Create a `.env` file in the root directory:
   ```env
   VITE_API_URL=http://localhost:8080  # Backend API URL
   VITE_APP_NAME=MLGC
   VITE_APP_VERSION=1.0.0
   ```

### Development

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🎯 Key Components

### `index.html`
- Main HTML5 document
- Semantic structure
- Meta tags for SEO
- PWA manifest and service worker registration

### `main.js`
Core application logic including:
- Drag and drop handlers
- File upload functionality
- API communication
- UI state management
- Error handling

### `api.js`
Handles all API communication:
- File uploads
- Prediction requests
- History retrieval
- Error handling and retries

### `styles/`
- Mobile-first CSS approach
- CSS Custom Properties for theming
- Responsive breakpoints
- Animation and transition effects

## 🌐 Browser Support

- Chrome (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)
- Edge (latest 2 versions)
- Mobile Safari (iOS 12+)
- Chrome for Android

## 📱 Responsive Breakpoints

- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

## 🧪 Testing

```bash
# Run unit tests
npm test

# Run tests in watch mode
npm test:watch

# Generate coverage report
npm run test:coverage
```

## 🛠 Build & Deployment

### Building for Production
```bash
npm run build
```

### Deploying to Google App Engine
```bash
gcloud app deploy app.yaml --project=your-project-id
```

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| VITE_API_URL | http://localhost:8080 | Backend API URL |
| VITE_APP_NAME | MLGC | Application name |
| VITE_APP_VERSION | 1.0.0 | Application version |

## 🚨 Error Handling

- Network errors
- Invalid file types
- Server errors
- Timeout handling
- User-friendly error messages

## 📈 Performance Optimization

- Code splitting
- Lazy loading
- Image optimization
- Caching strategies
- Bundle size monitoring

## 🔒 Security Considerations

- Input sanitization
- CORS configuration
- Content Security Policy (CSP)
- XSS protection
- Secure headers

## 🤝 Contributing

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Modern web standards and APIs
- Open source community
- Browser vendors for their developer tools
