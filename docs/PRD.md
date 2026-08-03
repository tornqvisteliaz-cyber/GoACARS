# Product Requirements Document

**Project Name:** GoACARS  
**Version:** 1.0  
**Status:** Draft  
**Owner:** GoACARS Development Team  

**Platform:**  
Windows Desktop, Windows Service, Web Dashboard  

**Target Users:**  
Virtual Airlines, Flight Simulator Pilots, Flight Operations Staff  

**Supported Simulators:**  
- Microsoft Flight Simulator 2024  
- Microsoft Flight Simulator 2020  

**Connection Method:**  
Microsoft SimConnect SDK  

## Goal

GoACARS is a modern ACARS and live flight tracking platform for virtual airlines. It connects directly to Microsoft Flight Simulator through SimConnect, records every flight in real time, uploads telemetry to the GoACARS server, and provides live tracking, pilot statistics, flight logs, and administrative management.

## Core Objectives

- One click connection to MSFS.
- Automatic SimConnect detection.
- Real time aircraft tracking.
- Reliable ACARS logging.
- Fleet management.
- Pilot management.
- Live map.
- Flight replay.
- Admin control panel.
- Fast and lightweight.

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

**Responsibilities**
- Authentication
- Receive telemetry
- Store flights
- Calculate statistics
- Live websocket updates
- Admin API

### Database

Stores
- Users
- Pilots
- Flights
- Aircraft
- Flight plans
- Events
- Airlines
- Roles
- Logs

### Web Dashboard

**Responsibilities**
- Live map
- Statistics
- Pilot pages
- Admin pages
- Fleet pages

## Pilot Features

### Authentication
- Login
- Remember me
- JWT authentication
- Refresh tokens

### Dashboard
Shows
- Hours flown
- Flights completed
- Current rank
- Last flights
- Flight time
- Landing rate
- Flight score

### Flight Planning
Pilot selects
- Flight Number
- Aircraft
- Departure
- Arrival
- Callsign
- Route
- Cruise altitude
- Fuel
- Remarks

**Import**
- SimBrief

## Flight Lifecycle

### Preflight
**Requirements**
- Aircraft on ground
- Parking brake
- Engine state
- Current airport

### Flight Started
Triggered when
- Pushback starts
- Parking brake released
- Taxi begins

### Taxi
Track
- Taxi time
- Taxi distance

### Takeoff
Record
- Rotation speed
- Takeoff runway
- Time
- Wind
- Heading

### Cruise
Live updates every second

Transmit
- Latitude
- Longitude
- Altitude
- Ground Speed
- IAS
- Heading
- Vertical Speed
- Fuel Remaining
- Fuel Burn
- Outside Temperature
- Aircraft Type
- Engine Status
- Autopilot

### Landing
Capture
- Landing rate
- Touchdown speed
- Runway
- Landing time
- Weather

### Shutdown
Flight automatically ends after
- Engines off
- Parking brake
- Ground speed 0

### Flight Report
Automatically generated
- Flight time
- Block time
- Air time
- Taxi time
- Fuel used
- Landing rate
- Distance
- Violations
- Score
- Route
- Map
- Replay

## SimConnect Data

**Read**
- Aircraft position
- Altitude
- Ground speed
- IAS
- Heading
- Pitch
- Bank
- Latitude
- Longitude
- Vertical speed
- Flaps
- Gear
- Spoilers
- Throttle
- Parking brake
- Lights
- Fuel
- Aircraft title
- Tail number
- Engine RPM
- Outside temperature
- Wind
- Pressure
- Simulation rate
- Paused state
- Crash state

## Live Flight Tracker

Interactive world map

**Features**
- Live aircraft
- Search pilot
- Search callsign
- Filter aircraft
- Filter airline
- Filter altitude
- Filter airport
- View route
- View flight plan
- View ETA

### Aircraft Card
Displays
- Aircraft image
- Aircraft type
- Registration
- Pilot
- Flight number
- Departure
- Arrival
- ETA
- Altitude
- Ground speed
- Heading
- Distance remaining
- Current status

### Map Features
- OpenStreetMap
- Google Maps
- Dark mode
- Satellite
- Auto refresh
- Smooth aircraft movement

## Replay

Replay every completed flight
- Timeline slider
- Pause
- Play
- Speed control
- Camera follow
- Export

## Statistics

### Pilot
- Hours
- Flights
- Average landing rate
- Longest flight
- Shortest flight
- Top aircraft
- Top airports

### Airline
- Total flights
- Total pilots
- Average flight time
- Aircraft utilization
- Popular routes

### Leaderboard
- Monthly
- Weekly
- All time

## Admin Panel

### Authentication
- Separate admin login
- Role based permissions
- Two factor authentication

### Admin Roles
- Owner
- Developer
- Administrator
- Operations Manager
- Fleet Manager
- Moderator
- Support

### Permissions
- Manage users
- Manage aircraft
- Manage flights
- Delete flights
- Suspend pilots
- Edit statistics
- Manage airlines
- Manage API keys
- View logs
- Broadcast messages
- Settings

### Dashboard
Widgets
- Flights online
- Pilots online
- Server status
- Recent flights
- Errors
- CPU
- RAM
- API requests

### User Management
- Create users
- Delete users
- Reset passwords
- Assign ranks
- Assign airlines
- Suspend accounts

### Aircraft Management
- Add aircraft
- Delete aircraft
- Assign aircraft
- Aircraft status
- Fleet statistics

### Flight Management
- Approve flights
- Reject flights
- Delete reports
- Edit reports
- Manual PIREPs

### Announcement System
- Create announcements
- Priority
- Banner
- Popup
- Maintenance notices

### Notifications
- Desktop
- Website
- Discord Webhook
- Email

## REST API

**Endpoints**
- `POST /login`
- `POST /flight/start`
- `POST /flight/update`
- `POST /flight/end`
- `GET /pilot`
- `GET /flight`
- `GET /leaderboard`
- `GET /live`
- `POST /admin/user`
- `POST /admin/aircraft`

## Security

- HTTPS
- JWT
- Password hashing
- Rate limiting
- IP logging
- Audit logs
- Encrypted communication

## Technology Stack

### Desktop
- C#
- WPF
- SimConnect SDK

### Backend
- ASP.NET Core
- SignalR
- Entity Framework
- PostgreSQL
- Redis

### Frontend
- React
- Next.js
- Tailwind CSS
- Leaflet

### Infrastructure
- Docker
- NGINX
- Cloudflare
- AWS or Hetzner

## Performance Targets

- Desktop RAM: Below 150 MB
- CPU: Below 2%
- Live updates: 1 second
- Flight upload: Below 2 seconds
- Dashboard load: Below 1 second

## Future Features

- AI flight scoring
- Voice ATC logging
- VATSIM integration
- IVAO integration
- Discord Rich Presence
- Shared cockpit
- Company economy
- Maintenance system
- Passenger simulation
- Mobile app
- Achievements
- Multi airline support
- Marketplace API
- Plugin SDK

## Success Metrics

- 99.9% uptime
- Under 1 second live tracking latency
- 95% successful flight uploads
- Support for over 10,000 simultaneous live flights
- Modern UI with minimal resource usage
- Automatic SimConnect connection without manual configuration
