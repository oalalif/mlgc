# MLGC - Backend Service

A high-performance Node.js backend service for skin disease classification using TensorFlow.js, built with Hapi.js and integrated with Google Cloud services.

## 🏗️ System Architecture

```
mlgc-backend/
├── src/
│   ├── config/           # Configuration management
│   ├── exceptions/       # Custom error classes
│   ├── server/           # Server configuration and routes
│   └── services/         # Core business logic
│       ├── firestore-service.js    # Database operations
│       ├── inferenceService.js     # ML model inference
│       ├── loadModel.js            # Model loading and caching
│       └── storage-services.js     # File storage operations
├── .dockerignore         # Docker ignore rules
├── .gitignore            # Git ignore rules
├── Dockerfile            # Container configuration
└── package.json          # Project dependencies and scripts
```

## 🚀 Features

- **RESTful API** with Hapi.js framework
- **Machine Learning Integration** using TensorFlow.js
- **File Storage** with Google Cloud Storage
- **NoSQL Database** with Firestore
- **Docker** containerization
- **Environment-based** configuration
- **Error Handling** with custom exceptions
- **Input Validation** for all endpoints

## 🛠️ Prerequisites

- Node.js v14+
- npm or yarn
- Google Cloud Platform account
- Docker (for containerization)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/mlgc.git
   cd mlgc
   git checkout backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   # Server Configuration
   PORT=8080
   NODE_ENV=development
   
   # Google Cloud Configuration
   GOOGLE_APPLICATION_CREDENTIALS=path/to/your/service-account.json
   PROJECT_ID=your-project-id
   BUCKET_NAME=your-bucket-name
   COLLECTION_NAME=your-collection-name
   MODEL_PATH=path/to/your/model
   ```

## 🚦 API Endpoints

### `POST /predict`
Upload and classify a skin image

**Request**
```http
POST /predict
Content-Type: multipart/form-data
```

**Parameters**
- `image` (required): Image file to classify

**Response**
```json
{
  "status": "success",
  "prediction": {
    "class": "melanoma",
    "confidence": 0.92,
    "timestamp": "2025-05-30T16:30:00Z"
  }
}
```

### `GET /predict/histories`
Get prediction history

**Request**
```http
GET /predict/histories
```

**Response**
```json
{
  "status": "success",
  "data": [
    {
      "id": "abc123",
      "imageUrl": "https://storage.googleapis.com/...",
      "prediction": "melanoma",
      "confidence": 0.92,
      "timestamp": "2025-05-30T16:30:00Z"
    }
  ]
}
```

## 🐳 Docker Deployment

### Build the Docker image
```bash
docker build -t mlgc-backend .
```

### Run the container
```bash
docker run -p 8080:8080 --env-file .env mlgc-backend
```

## 🧪 Testing

### Run unit tests
```bash
npm test
```

### Run with debug logs
```bash
DEBUG=mlgc:* npm start
```

## 🔍 Code Structure Details

### Services

#### `inferenceService.js`
Handles all machine learning model operations including:
- Loading the TensorFlow.js model
- Preprocessing input images
- Running predictions
- Post-processing results

#### `firestore-service.js`
Manages all Firestore database operations:
- Storing prediction results
- Retrieving prediction history
- Managing user data

#### `storage-services.js`
Handles file storage operations:
- Uploading images to Google Cloud Storage
- Generating signed URLs
- Managing file lifecycle

## 📊 Performance Considerations

- **Model Caching**: The ML model is loaded once at startup and cached
- **Connection Pooling**: Database connections are pooled for better performance
- **Asynchronous Processing**: Heavy operations are handled asynchronously
- **Request Validation**: Input validation before processing

## 🔒 Security

- **Input Sanitization**: All user inputs are sanitized
- **Authentication**: JWT-based authentication (coming soon)
- **CORS**: Configured to allow requests only from trusted domains
- **Rate Limiting**: Implemented to prevent abuse

## 📈 Monitoring & Logging

- **Winston** for structured logging
- **Google Cloud Logging** integration
- **Error tracking** with Stackdriver

## 🤝 Contributing

1. Create a feature branch (`git checkout -b feature/AmazingFeature`)
2. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
3. Push to the branch (`git push origin feature/AmazingFeature`)
4. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- TensorFlow.js team for the machine learning framework
- Hapi.js team for the Node.js framework
- Google Cloud Platform for their infrastructure services
