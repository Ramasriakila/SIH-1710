Smart India Hackathon Workshop

Date: 18/09/2026
Register Number: 212224040267
Name: RAMASRI K

Problem Title

SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations

Problem Creator's Organization

Ministry of Railways

Idea / Proposed Solution

We propose a Smart Railway Station Indoor Navigation System that helps passengers easily find platforms, ticket counters, restrooms, food courts, waiting halls, lifts, escalators and other facilities.

The system uses interactive 2D/3D maps, indoor positioning, QR codes, voice guidance and accessibility features to provide step-by-step navigation. Passengers can select their destination through a mobile application or digital kiosk and receive the shortest and most suitable route.

The system can also provide accessible routes for wheelchair users and visually impaired passengers. Station authorities can update facility locations and routes whenever the station layout changes.

Architecture Diagram
             Passenger
                 │
        ┌────────┴────────┐
        │                 │
   Mobile App        Digital Kiosk
        │                 │
        └────────┬────────┘
                 │
        Navigation Interface
                 │
        ┌────────┴────────┐
        │                 │
  Indoor Positioning   Station Map DB
        │                 │
        └────────┬────────┘
                 │
        Route Calculation
        (A* / Dijkstra)
                 │
        ┌────────┴────────┐
        │                 │
   Visual Guidance    Voice Guidance
        │                 │
        └────────┬────────┘
                 │
       Railway Station
       Facilities & Routes
Use Cases
Passenger searches for a platform.
Passenger finds ticket counters.
Navigation to restrooms and waiting halls.
Finding food courts and shops.
Finding lifts and escalators.
Providing wheelchair-accessible routes.
Providing voice navigation for visually impaired users.
Helping passengers find the shortest route between two locations.
Updating facility locations when the station layout changes.
Providing navigation through mobile apps and digital kiosks.
Technology Stack
Component	Technology
Mobile Application	Flutter / React Native
Frontend	HTML, CSS, JavaScript / React
Backend	Python Django / Node.js
Database	PostgreSQL / MySQL
Maps	2D/3D Indoor Maps
Navigation Algorithm	A* / Dijkstra
Indoor Positioning	QR / BLE / Wi-Fi
Voice Guidance	Text-to-Speech
API	REST API
Cloud	Firebase / AWS
Kiosk	Touch-screen Web Application
Dependencies
Digital map of the railway station
Accurate facility and location database
Indoor positioning infrastructure such as BLE/Wi-Fi/QR
Mobile application or web interface
Backend server and database
Internet/local network connectivity
Text-to-speech service for voice navigation
Regular station-layout and facility updates
Digital kiosk hardware with touch screen
Integration APIs for existing railway services
