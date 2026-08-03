# GoACARS

**Modern ACARS and live flight tracking platform for virtual airlines.**

GoACARS connects directly to Microsoft Flight Simulator (2020 & 2024) through the SimConnect SDK. It records every flight in real time, uploads telemetry to the GoACARS server, and provides live tracking, pilot statistics, flight logs, and administrative management.

## Platforms

- **Windows Desktop Client** (WPF)
- **Windows Service**
- **Web Dashboard** (React / Next.js)

## Target Users

- Virtual Airlines
- Flight Simulator Pilots
- Flight Operations Staff

## Supported Simulators

- Microsoft Flight Simulator 2024
- Microsoft Flight Simulator 2020

## Core Objectives

- One-click connection to MSFS
- Automatic SimConnect detection
- Real-time aircraft tracking
- Reliable ACARS logging
- Fleet management
- Pilot management
- Live map
- Flight replay
- Admin control panel
- Fast and lightweight

## System Architecture

### Desktop Client
Runs on the pilot's PC.

**Responsibilities**
- Connect to SimConnect
- Detect aircraft
- Detect departure
- Send live data
- Monitor landing
- Upload flight report
- Handle reconnects

### Backend API
- Authentication
- Receive telemetry
- Store flights
- Calculate statistics
- Live WebSocket updates (SignalR)
- Admin API

### Database
Stores: Users, Pilots, Flights, Aircraft, Flight plans, Events, Airlines, Roles, Logs

### Web Dashboard
- Live map
- Statistics
- Pilot pages
- Admin pages
- Fleet pages

## Technology Stack

| Layer          | Technology                              |
|----------------|-----------------------------------------|
| Desktop        | C# / WPF / SimConnect SDK               |
| Backend        | ASP.NET Core / SignalR / Entity Framework |
| Database       | PostgreSQL + Redis                      |
| Frontend       | React / Next.js / Tailwind CSS / Leaflet |
| Infrastructure | Docker / NGINX / Cloudflare / AWS or Hetzner |

## Performance Targets

- Desktop RAM: < 150 MB
- CPU: < 2%
- Live updates: 1 second
- Flight upload: < 2 seconds
- Dashboard load: < 1 second

## Success Metrics

- 99.9% uptime
- Under 1 second live tracking latency
- 95% successful flight uploads
- Support for 10,000+ simultaneous live flights
- Modern UI with minimal resource usage
- Automatic SimConnect connection without manual configuration

## Project Structure (planned)

```
GoACARS/
├── docs/                 # Product Requirements, design docs
├── src/
│   ├── Desktop/          # WPF client + Windows Service
│   ├── Backend/          # ASP.NET Core API
│   └── Frontend/         # Next.js dashboard
├── docker/               # Docker compose & configs
└── README.md
```

## Status

**Version:** 1.0  
**Status:** Draft  
**Owner:** GoACARS Development Team

See [docs/PRD.md](docs/PRD.md) for the full Product Requirements Document.

## License

TBD
