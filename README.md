# Smart India Hackathon Workshop

## Date:

18/09/2026

## Register Number:

212224040267

## Name:

**RAMASRI K**

## Problem Title

**SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations**

## Problem Description

Railway stations are complex environments containing many facilities such as platforms, ticket counters, restrooms, waiting halls, food courts, lifts, stairs and entrances. Passengers who are unfamiliar with a large railway station may face difficulties in finding the correct facility or reaching their destination on time.

The problem is to develop a smart navigation system that helps passengers locate railway station facilities and provides clear directions within the station premises. The system should support different types of passengers, including people with disabilities and visually impaired users.

The proposed solution should provide interactive maps, real-time route information, accessibility options, voice guidance and support for multiple platforms such as mobile applications and digital kiosks.

## Problem Creator's Organization

**Ministry of Railways**

---

# Idea

## TrackEase – Intelligent Railway Station Navigation & Accessibility System

TrackEase is a smart indoor navigation system designed to help railway passengers find facilities and navigate easily inside railway stations.

The system provides a digital map of the railway station containing platforms, ticket counters, restrooms, waiting areas, food courts, lifts, stairs, entrances and other important locations.

Passengers can search for a destination and receive a suitable route from their current location. QR checkpoints placed at important locations can be scanned to identify the passenger's current position.

TrackEase also provides accessibility-aware navigation. Passengers who require an accessible route can select the accessibility option, allowing the system to prioritize lifts, ramps and accessible pathways while avoiding stairs whenever possible.

The system can be accessed through a mobile/web application as well as touchscreen kiosks installed inside railway stations.

## Key Features

* Interactive railway station map
* Facility search
* QR-based location identification
* Indoor route calculation
* Step-by-step navigation
* Accessibility-friendly route planning
* Voice-guided navigation
* Digital kiosk support
* Real-time route updates
* Facility information
* Temporary route blocking
* Station alerts
* Administrator dashboard

## Unique Approach

Unlike a basic map-based navigation system, TrackEase represents the railway station as a network of connected locations and pathways.

Important locations are represented as nodes, while walkable paths are represented as connections between nodes.

The navigation engine calculates a suitable route based on:

* Distance
* Path availability
* Accessibility requirements
* Route restrictions
* User navigation preference

For example, a normal passenger may receive:

```text
Entrance → Stairs → Footbridge → Platform 2
```

A passenger requiring an accessible route may receive:

```text
Entrance → Lift → Footbridge → Platform 2
```

This allows the same station map to provide different routes based on passenger requirements.

---

# Proposed Solution / Architecture Diagram

## Proposed Solution

TrackEase consists of five major components:

### 1. Passenger Application

The passenger application allows users to:

* Search facilities
* View the station map
* Scan QR checkpoints
* Select destinations
* Generate routes
* Follow step-by-step navigation
* Receive station alerts

### 2. QR Location Module

QR codes are placed at selected locations such as:

* Station entrances
* Platform entrances
* Main corridors
* Ticket counters
* Waiting areas
* Important junctions

When a passenger scans a QR code, the system identifies the corresponding location and uses it as the starting point for navigation.

### 3. Navigation Engine

The railway station is represented as a graph.

```text
Node = Railway station location

Edge = Walkable pathway

Weight = Travel distance or movement cost
```

The navigation engine can use Dijkstra's Algorithm or A* to calculate a route between two locations.

### 4. Accessibility Module

The accessibility module identifies routes containing:

* Lifts
* Ramps
* Accessible entrances
* Suitable pathways

When the user selects an accessibility-friendly route, the navigation engine avoids unsuitable paths such as stairs whenever an alternative is available.

### 5. Administrator Dashboard

Station administrators can:

* Add facilities
* Update facility information
* Modify station map data
* Block unavailable pathways
* Restore blocked pathways
* Update accessibility information
* Publish station alerts

---

## Architecture Diagram

```text
                         ┌─────────────────────┐
                         │      PASSENGER      │
                         └──────────┬──────────┘
                                    │
                 ┌──────────────────┼──────────────────┐
                 │                  │                  │
                 ▼                  ▼                  ▼
          ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
          │ Mobile App  │    │  Web App    │    │ Kiosk App   │
          └──────┬──────┘    └──────┬──────┘    └──────┬──────┘
                 │                  │                  │
                 └──────────────────┼──────────────────┘
                                    ▼
                         ┌─────────────────────┐
                         │    TrackEase API    │
                         └──────────┬──────────┘
                                    │
               ┌────────────────────┼────────────────────┐
               │                    │                    │
               ▼                    ▼                    ▼
       ┌──────────────┐     ┌───────────────┐    ┌──────────────┐
       │ QR Location  │     │ Navigation    │    │ Facility     │
       │ Service      │     │ Engine        │    │ Service      │
       └──────┬───────┘     └───────┬───────┘    └──────┬───────┘
              │                     │                   │
              └─────────────────────┼───────────────────┘
                                    ▼
                         ┌─────────────────────┐
                         │  Station Database   │
                         └──────────┬──────────┘
                                    │
                     ┌──────────────┴──────────────┐
                     ▼                             ▼
             ┌───────────────┐             ┌───────────────┐
             │ Station Map   │             │ Live Updates  │
             │ Data          │             │ & Alerts      │
             └───────────────┘             └───────┬───────┘
                                                   │
                                                   ▼
                                         ┌──────────────────┐
                                         │ Admin Dashboard  │
                                         └──────────────────┘
```

---

# Use Cases

## Actors

1. Passenger
2. Wheelchair User
3. Visually Impaired Passenger
4. Station Administrator
5. Railway Information System

## Use Case Diagram

```text
                  ┌─────────────────────────────────────┐
                  │             TrackEase               │
                  │                                     │
                  │  ┌───────────────────────────────┐  │
Passenger ────────┼─►│ Search Facility               │  │
                  │  └───────────────────────────────┘  │
                  │                                     │
Passenger ────────┼─► View Station Map                  │
                  │                                     │
Passenger ────────┼─► Scan QR Checkpoint                │
                  │                                     │
Passenger ────────┼─► Select Destination                │
                  │                                     │
Passenger ────────┼─► Find Route                        │
                  │                                     │
Passenger ────────┼─► Start Navigation                  │
                  │                                     │
Passenger ────────┼─► Receive Alerts                    │
                  │                                     │
Wheelchair User ──┼─► Request Accessible Route          │
                  │                                     │
Visually Impaired ┼─► Voice Navigation                  │
Passenger         │                                     │
                  │                                     │
Administrator ────┼─► Add / Update Facility             │
                  │                                     │
Administrator ────┼─► Update Station Map                │
                  │                                     │
Administrator ────┼─► Block / Unblock Route             │
                  │                                     │
Administrator ────┼─► Publish Station Alert             │
                  │                                     │
Railway System ───┼─► Provide Station Information       │
                  │                                     │
                  └─────────────────────────────────────┘
```

## Use Case Description

### 1. Search Facility

The passenger searches for a required facility such as a platform, restroom, ticket counter, lift, food court or waiting area.

### 2. View Station Map

The passenger can view an interactive map showing important locations and pathways within the railway station.

### 3. Scan QR Checkpoint

The passenger scans a QR code placed at a station checkpoint. The system identifies the corresponding location and uses it as the starting point.

### 4. Select Destination

The passenger selects the facility or location they want to reach.

### 5. Find Route

The navigation engine calculates a suitable route between the current location and the selected destination.

### 6. Accessible Route

Wheelchair users and passengers requiring accessibility support can request a route that prioritizes lifts, ramps and accessible pathways.

### 7. Voice Navigation

The system provides voice instructions to assist visually impaired passengers during navigation.

### 8. Receive Alerts

Passengers can receive notifications about blocked pathways, changed facility locations and important station announcements.

### 9. Update Facility

Administrators can add new facilities or modify existing facility information.

### 10. Block / Unblock Route

Administrators can temporarily block a pathway when it is unavailable due to maintenance, construction or other conditions.

### 11. Publish Alert

Administrators can publish important information and alerts for passengers.

---

# Technology Stack

## Frontend

* React.js
* HTML5
* CSS3
* JavaScript
* React Router

## Backend

* Node.js
* Express.js
* REST API

## Database

* MongoDB
* Mongoose

## Navigation

* Dijkstra's Algorithm
* A* Algorithm
* Graph-based route representation

## Map Visualization

* Three.js
* Interactive 2D/3D station map

## Accessibility

* Web Speech API
* Text-to-Speech
* Accessible user interface

## QR Technology

* QR Code Generator
* QR Code Scanner

## Development Tools

* Visual Studio Code
* Git
* GitHub
* Postman

---

# Dependencies

```text
Node.js
npm
React
React Router
Express.js
MongoDB
Mongoose
Axios
Three.js
QR Code Scanner
QR Code Generator
Web Speech API
Git
GitHub
Postman
```

---

# System Workflow

```text
             Passenger Enters Station
                       │
                       ▼
                Scan QR Checkpoint
                       │
                       ▼
              Current Location Found
                       │
                       ▼
                Search Destination
                       │
                       ▼
             Select Route Preference
                       │
              ┌────────┴────────┐
              │                 │
              ▼                 ▼
        Normal Route      Accessible Route
              │                 │
              └────────┬────────┘
                       ▼
                Route Calculation
                       │
                       ▼
             Step-by-Step Navigation
                       │
                       ▼
                  Destination
```

---

# Advantages

* Helps passengers navigate large railway stations.
* Reduces confusion while searching for facilities.
* Provides location-based indoor navigation.
* Supports accessibility-friendly routes.
* Provides voice-based navigation.
* Supports mobile applications and digital kiosks.
* QR checkpoints provide a simple indoor location mechanism.
* Administrators can update station information.
* Blocked pathways can be removed from future route calculations.
* The system can be expanded to multiple railway stations.

---

# Innovation

The main innovation of TrackEase is the combination of **QR-assisted indoor positioning and accessibility-aware route planning**.

Instead of depending completely on GPS, QR checkpoints can provide known location points inside a railway station.

The navigation engine can also consider passenger requirements while calculating routes.

For example:

```text
Shortest Route
        ↓
Entrance → Stairs → Platform

Accessible Route
        ↓
Entrance → Lift → Footbridge → Platform
```

This makes the navigation system more suitable for passengers with different mobility requirements.

---

# Future Enhancements

* Bluetooth Beacon-based indoor positioning
* Real-time crowd-density monitoring
* AI-based congestion prediction
* Augmented Reality navigation
* Multilingual voice guidance
* Emergency evacuation navigation
* Integration with railway ticketing applications
* Live train information integration
* Smart wearable support
* Offline station maps

---

# Submission Evaluation

## Submission 1

**Repository:** [PASTE FIRST STUDENT GITHUB LINK]

### Evaluation

**Problem Understanding:**
The submission addresses the difficulty of navigating railway station facilities and identifies the need for an indoor navigation solution.

**Proposed Solution:**
The solution provides a digital approach for helping passengers identify facilities and navigate within the railway station.

**Technology Stack:**
The submission uses software technologies suitable for developing a navigation-based application.

**Innovation:**
The submission presents features intended to improve passenger navigation and accessibility.

**Accessibility:**
Accessibility features are considered for passengers who may require additional navigation support.

**Strengths:**

* Addresses the given SIH problem.
* Focuses on railway station navigation.
* Provides a technology-based solution.
* Includes navigation-related features.

**Limitations:**

* Some implementation details may require further development.
* Real-time station updates can require additional infrastructure.

**My Observation:**
The submission provides a relevant approach to the railway station navigation problem. It helped me understand different ways of designing a solution for indoor passenger navigation.

---

# Submission 2

**Repository:** [PASTE SECOND STUDENT GITHUB LINK]

### Evaluation

**Problem Understanding:**
The submission identifies the challenges faced by passengers while locating facilities and destinations inside railway stations.

**Proposed Solution:**
The proposed system provides a digital navigation approach for helping passengers reach required locations.

**Technology Stack:**
The technologies selected are suitable for developing a web/mobile-based navigation solution.

**Innovation:**
The submission includes features that can improve the passenger experience and accessibility.

**Accessibility:**
The solution considers the requirements of passengers with different accessibility needs.

**Strengths:**

* Relevant to the SIH problem.
* Provides a structured navigation concept.
* Focuses on passenger convenience.
* Can be extended with additional features.

**Limitations:**

* Accurate indoor positioning can be challenging.
* Real-time updates require reliable station data.

**My Observation:**
The submission provides useful ideas for solving indoor railway station navigation challenges. The evaluation helped identify important requirements such as accurate location information, accessibility and real-time updates.

---

# TrackEase vs Existing Approaches

TrackEase focuses specifically on combining:

* QR-based indoor location identification
* Graph-based navigation
* Accessibility-aware routing
* Voice guidance
* Facility discovery
* Administrator-controlled updates

The combination of these features forms the proposed TrackEase solution for SIH 1710.

---

# Conclusion

TrackEase – Intelligent Railway Station Navigation & Accessibility System is designed to make railway station navigation easier, faster and more accessible.

The system combines interactive station maps, QR-assisted location identification, graph-based route calculation, accessibility-aware navigation, voice guidance and administrator-controlled updates.

By supporting mobile applications, web interfaces and digital kiosks, TrackEase can provide passengers with a convenient way to locate railway facilities and reach their destinations inside complex railway stations.

The proposed system can be further enhanced with Bluetooth beacons, real-time crowd monitoring, AI-based route optimization and augmented reality navigation.

---

# Project Structure

```text
TrackEase/
│
├── README.md
│
├── diagrams/
│   ├── proposed-solution.png
│   └── use-case-diagram.png
│
├── docs/
│   ├── solution.md
│   ├── workflow.md
│   └── accessibility.md
│
├── evaluation/
│   ├── submission-1.md
│   └── submission-2.md
│
├── frontend/
│
├── backend/
│
├── database/
│
├── sample-data/
│
└── .gitignore
```
