# Image Annotator

A web-based image annotation tool with AI-powered object detection using YOLOv8.

## Quick Install

### Prerequisites
- **Python 3.8+**
- **Node.js 16+**

### Backend Setup

```bash
# Navigate to backend
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Install the optional YOLO inference stack for local inference
pip install -r requirements-inference.txt

# Run migrations
python manage.py migrate

# Start server
python manage.py runserver
```

Server runs on: `http://localhost:8000`

Vercel installs only `requirements.txt` to stay within its function-size limit.
The rest of the API remains available there, but the inference endpoint responds
with HTTP 503 unless inference is deployed separately on a host that can install
`requirements-inference.txt`.

### Frontend Setup

```bash
# Navigate to frontend
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

Frontend runs on: `http://localhost:5173`

### Environment Configuration

1. Create `.env` file in backend directory:
```env
DEBUG=false
SECRET_KEY=<your-secret-key>
ALLOWED_HOSTS=localhost,127.0.0.1
CORS_ALLOWED_ORIGINS=http://localhost:3000,http://localhost:5173
```

2. Generate a secure SECRET_KEY:
```bash
python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
```

## Full Documentation

For complete documentation, architecture details, and feature guides, please visit the [**docs** folder](docs/README.md).

### Quick Links
- [Day 1: Project Setup](docs/day1.md) - Architecture and initial setup
- [Day 2: Core Features](docs/day2.md) - API endpoints and models
- [Day 3: UI Implementation](docs/day3.md) - React components and canvas
- [Day 4: Security](docs/day4.md) - Security hardening and configuration
- [Day 5: Inference](docs/day5.md) - YOLOv8 integration and deployment

## Features

- Image upload and management
- Interactive annotation canvas
- AI-powered object detection (YOLOv8)
- YOLO dataset export
- Production-ready security
- Comprehensive test coverage

## Useful Resources

- [Quick Reference](docs/QUICK_REFERENCE.md) - Commands and API endpoints
- [Security Configuration](docs/SECURITY_CONFIGURATION.md) - Deployment security
- [Complete Documentation](docs/complete_documentation.md) - Versions, structure, and workflows
- [Inference Guide](docs/INFERENCE_DEPLOYMENT_GUIDE.md) - YOLOv8 setup
- [Testing Guide](docs/YOLO_TESTING_GUIDE.md) - Test procedures

## License

Created as an educational project for image annotation and object detection.

---

**Need detailed information?** → Check the [docs folder](docs/README.md)
# image-annotation
