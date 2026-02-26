# Eye-sight Detection using Computer Vision

A web application that uses computer vision to detect and analyze eye characteristics, including fatigue detection, gaze tracking, and real-time analysis.

## Features
- 👁️ Real-time eye detection and tracking
- 😴 Eye fatigue detection
- 📊 Detailed analysis reports
- 🎯 Gaze direction estimation
- 📈 Eye movement statistics
- 💾 Data persistence

## Tech Stack
- **Frontend**: React.js + Tailwind CSS
- **Backend**: Flask (Python)
- **Computer Vision**: OpenCV + MediaPipe
- **Database**: SQLite/PostgreSQL
- **Containerization**: Docker & Docker Compose

## Project Structure
```
Tabassum-/
├── backend/                 # Flask backend with CV logic
│   ├── app.py              # Main Flask application
│   ├── eye_detector.py     # Eye detection algorithms
│   ├── requirements.txt    # Python dependencies
│   └── Dockerfile          # Backend Docker config
├── frontend/               # React frontend
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── services/       # API services
│   │   └── App.jsx         # Main app component
│   ├── package.json        # Node dependencies
│   └── Dockerfile          # Frontend Docker config
├── docker-compose.yml      # Docker Compose setup
├── README.md              # This file
└── SETUP.md               # Setup instructions
```

## Quick Start

### Using Docker Compose (Recommended)
```bash
docker-compose up
```

### Manual Setup
```bash
# Backend setup
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py

# Frontend setup (in a new terminal)
cd frontend
npm install
npm start
```

## Access the Application
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- API Documentation: http://localhost:5000/api/docs

## API Endpoints

### Eye Detection
- `POST /api/detect` - Analyze frame for eye detection
- `GET /api/status` - Get current detection status
- `GET /api/history` - Retrieve detection history

### Reports
- `GET /api/report` - Generate analysis report
- `GET /api/stats` - Get eye movement statistics

## Features in Detail

### Real-time Eye Detection
- Detects eyes using MediaPipe Face Mesh
- Tracks eye center and iris position
- Estimates gaze direction

### Fatigue Detection
- Monitors eye closure duration
- Tracks blink frequency
- Calculates fatigue score
- Alerts user when fatigue detected

### Data Analysis
- Records eye movement patterns
- Generates detailed reports
- Provides statistical insights
- Export analysis as CSV/PDF

## Requirements
- Python 3.8+
- Node.js 14+
- Webcam/Camera device
- Modern web browser (Chrome, Firefox, Safari, Edge)

## Installation

See [SETUP.md](SETUP.md) for detailed setup instructions.

## Usage

1. **Start the application**:
   ```bash
   docker-compose up
   ```

2. **Open browser** and navigate to `http://localhost:3000`

3. **Allow camera access** when prompted

4. **Start detection** by clicking the "Start Monitoring" button

5. **View results** in real-time on the dashboard

6. **Generate reports** for detailed analysis

## Configuration

Create a `.env` file in both `backend/` and `frontend/` directories:

### Backend (.env)
```
FLASK_ENV=development
FLASK_DEBUG=True
PORT=5000
DATABASE_URL=sqlite:///eye_detection.db
```

### Frontend (.env)
```
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENV=development
```

## Troubleshooting

### Camera not working
- Check browser permissions for camera access
- Ensure no other application is using the camera
- Try refreshing the page

### Backend connection issues
- Verify Flask server is running on port 5000
- Check firewall settings
- Review browser console for CORS errors

### Performance issues
- Reduce frame processing rate
- Lower video resolution
- Check system CPU/memory usage

## Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Authors
- **Tabassum** - Initial work

## Acknowledgments
- OpenCV for computer vision capabilities
- MediaPipe for face and hand detection
- React community for excellent documentation
- Flask community for lightweight web framework
