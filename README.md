# MLGC - Skin Disease Classification

A machine learning-based web application for classifying skin conditions using TensorFlow.js and Node.js.

## 📁 Project Structure

```
mlgc/
├── backend/                  # Node.js backend service
│   ├── src/
│   │   ├── config/         # Configuration files
│   │   ├── exceptions/       # Custom error classes
│   │   ├── server/          # Server setup and routes
│   │   └── services/        # Business logic and ML services
│   └── package.json         # Backend dependencies
│
└── frontend/               # Web frontend
    ├── public/              # Static files
    ├── src/
    │   ├── images/         # Image assets
    │   ├── scripts/         # Frontend JavaScript
    │   └── styles/          # CSS stylesheets
    └── package.json         # Frontend dependencies
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v14+)
- npm or yarn
- TensorFlow.js
- Google Cloud Firestore (for data storage)
- Google Cloud Storage (for file storage)

### Installation

1. **Backend Setup**
   ```bash
   cd backend
   npm install
   cp .env.example .env
   # Update .env with your configuration
   ```

2. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   ```

3. **Environment Variables**
   Create a `.env` file in the backend directory with the following variables:
   ```
   PORT=8080
   PROJECT_ID=your-gcp-project-id
   BUCKET_NAME=your-gcs-bucket-name
   COLLECTION_NAME=your-firestore-collection
   MODEL_PATH=path-to-your-model
   ```

## 🛠 Development

### Backend Development
```bash
cd backend
npm run start:dev  # Development with hot-reload
# or
npm start         # Production start
```

### Frontend Development
```bash
cd frontend
npm start  # Starts development server
```

## 🌐 API Endpoints

### Backend API
- `POST /predict` - Upload and classify a skin image
  - Accepts: `multipart/form-data` with `skinFile` field
  - Returns: Prediction results

- `GET /predict/histories` - Get prediction history
  - Returns: List of previous predictions

## 🔧 Technologies Used

### Backend
- Node.js with Hapi.js
- TensorFlow.js for machine learning
- Google Cloud Firestore (NoSQL database)
- Google Cloud Storage (File storage)

### Frontend
- Vanilla JavaScript
- HTML5 & CSS3
- Responsive design
- Drag & drop file upload

## 📊 Features

- **Image Classification**: Upload skin images for ML-based analysis
- **Responsive UI**: Works on desktop and mobile devices
- **Prediction History**: View previous predictions
- **Real-time Feedback**: Visual feedback during processing
- **Error Handling**: Comprehensive error messages and validation

## 🔍 Model Information

The application uses a pre-trained TensorFlow.js model for skin disease classification. The model is loaded from the specified `MODEL_PATH` in the environment variables.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📚 Resources

- [TensorFlow.js Documentation](https://www.tensorflow.org/js)
- [Hapi.js Documentation](https://hapi.dev/)
- [Google Cloud Firestore](https://firebase.google.com/docs/firestore)
- [Google Cloud Storage](https://cloud.google.com/storage)

## 🙏 Acknowledgments

- TensorFlow.js team for the machine learning framework
- Hapi.js team for the Node.js framework
- Google Cloud Platform for hosting and storage solutions
