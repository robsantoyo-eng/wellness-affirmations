# Setup Guide

## Quick Start (Without Docker)

### Backend Setup
```bash
cd backend
npm install
cp .env.example .env
npm start
```

Server runs on `http://localhost:5000`

### Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env
npm run dev
```

App runs on `http://localhost:5173`

## Docker Setup

Build and run with Docker Compose:

```bash
docker-compose up
```

This will start:
- Backend: `http://localhost:5000`
- Frontend: `http://localhost:5173`

## Project Structure

```
wellness-affirmations/
├── backend/
│   ├── routes/
│   │   ├── affirmations.js
│   │   └── reminders.js
│   ├── data/
│   │   └── affirmations.json
│   ├── server.js
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── AffirmationCard.jsx
│   │   │   ├── ReminderForm.jsx
│   │   │   └── ReminderList.jsx
│   │   ├── App.jsx
│   │   ├── api.js
│   │   └── main.jsx
│   ├── package.json
│   ├── vite.config.js
│   └── .env.example
└── docker-compose.yml
```

## Available API Endpoints

### Affirmations
- `GET /api/affirmations` - Get all affirmations
- `GET /api/affirmations/daily` - Get today's affirmation
- `GET /api/affirmations/random` - Get random affirmation
- `GET /api/affirmations/category/:category` - Get affirmations by category

### Reminders
- `GET /api/reminders` - Get all reminders
- `POST /api/reminders/set` - Create new reminder
- `DELETE /api/reminders/:id` - Delete reminder

## Technologies Used

- **Frontend**: React 18, Vite, Tailwind CSS
- **Backend**: Express.js, Node.js
- **Database**: JSON files (ready for MongoDB upgrade)
- **Notifications**: Browser Notifications API
- **Containerization**: Docker & Docker Compose

## Next Steps

1. Add database (MongoDB/PostgreSQL)
2. Implement user authentication
3. Add push notifications service
4. Create mobile app
5. Deploy to production

## Troubleshooting

**Port already in use:**
```bash
# Change ports in .env or docker-compose.yml
```

**CORS errors:**
- Make sure `FRONTEND_URL` in backend `.env` matches your frontend URL

**API not responding:**
- Check that backend is running on port 5000
- Verify `VITE_API_URL` in frontend `.env` points to correct backend

## Support

For issues or questions, open an issue on GitHub!
