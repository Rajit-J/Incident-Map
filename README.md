# Incident Map

A browser-based incident map with an optional Node.js API for persistence and real-time updates. The frontend can run in local/demo mode without the backend.

## Features

- Interactive Leaflet map and incident markers.
- Browser geolocation, incident filtering, and search.
- Optional Express API, Socket.IO updates, and MongoDB persistence.

Map tiles and geocoding rely on external providers. Review their usage policies and attribution requirements before deployment. Ask for location permission only when needed and explain how location is handled.

## Technology

- Frontend: HTML, CSS, and JavaScript
- Backend: Node.js, Express, Socket.IO, and Mongoose
- Database: MongoDB (optional)

## Run locally on Windows

### Frontend

Open PowerShell:

```powershell
cd D:\MyProjects\Incident-Map\incident-reporter\frontend
py -m http.server 5175 --bind 127.0.0.1
```

Open [http://127.0.0.1:5175](http://127.0.0.1:5175). Stop with **Ctrl+C**.

### Optional backend

In a second PowerShell window:

```powershell
cd D:\MyProjects\Incident-Map\incident-reporter\backend
npm install
$env:PORT = "3001"
npm start
```

Check [http://127.0.0.1:3001/health](http://127.0.0.1:3001/health). Stop with **Ctrl+C**. Configure `MONGO_URI` in a local environment file if you want database persistence; do not commit credentials or `.env` files.

## Limitations and privacy

Without MongoDB, backend data does not persist. Demo incidents are not verified reports of real events. Geolocation and third-party map services have privacy implications; do not treat this prototype as an emergency-response service.

## Before publishing

Exclude `node_modules`, local databases, logs, and environment files. Confirm team permissions and external map/geocoding terms. No license is included; confirm ownership before adding one.
