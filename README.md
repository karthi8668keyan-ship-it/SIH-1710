# Smart India Hackathon Workshop
# Date:
## Register Number:
## Name:
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## Problem Description
Background: Railway stations are complex environments with numerous facilities and locations such as ticket counters, platforms, restrooms, food courts, and waiting areas. Passengers often face difficulties in navigating these spaces, especially in large or unfamiliar stations. Efficient and user-friendly navigation systems are crucial for improving passenger experience, reducing congestion, and ensuring timely travel connections. Description: The problem involves developing a comprehensive navigation solution for railway stations that assists passengers in locating various facilities and destinations within the station premises. This includes creating detailed maps, providing real-time directions, and integrating features such as accessibility options for individuals with disabilities. The solution should be intuitive, easy to use, and accessible via multiple platforms, including mobile devices and digital kiosks. Key challenges include updating navigation information in real-time, ensuring accuracy, and accommodating the diverse needs of all passengers. Expected Solution: The expected solution is a multi-platform navigation system that provides detailed, real-time directions to all facilities and locations within a railway station. This system should include: A mobile application with 3D interactive maps and step-by-step navigation. Digital kiosks located throughout the station with touch-screen interfaces. Voice-guided navigation for visually impaired passengers. Regular updates to reflect changes in station layout and facility locations. Integration with existing railway apps and services for seamless user experience. The solution should enhance the overall passenger experience by reducing confusion, saving time, and improving accessibility within the station.

## Problem Creater's Organization
Ministry of Railway

## Idea
NaviRail 360: AR-Powered Smart Wayfinding Ecosystem
NaviRail 360 is a highly accurate, multi-platform indoor navigation ecosystem designed to eliminate passenger confusion in dense railway stations. Since traditional GPS fails indoors, NaviRail 360 leverages a hybrid positioning system using Bluetooth Low Energy (BLE) Beacons and Augmented Reality (AR) spatial mapping.

Passengers can interact with touch-screen digital kiosks to instantly visualize 3D station maps and scan a QR code to hand the route off to their smartphone. Once on mobile, users can activate "AR View" to see floating digital arrows overlaying their real-world camera view, guiding them step-by-step to their exact platform, food court, or restroom. The system features a core "Accessibility Engine" providing haptic/voice feedback for the visually impaired and step-free routes for wheelchair users.

## Proposed Solution / Architecture Diagram
<img width="1024" height="1536" alt="e8a7e4ff-14c4-400a-947b-ec25e0b0385a" src="https://github.com/user-attachments/assets/40d52b69-74b8-4ba6-a24b-21e38091b400" />


## Use Cases
AR-Guided Passenger Routing: A passenger looking for Platform 6 opens their camera; AR arrows appear on the floor of their screen, guiding them through crowds to the exact location.

Frictionless Kiosk-to-Mobile Handoff: A user plans a route on a public touch-screen kiosk. A QR code is generated on the screen. The user scans it, and the exact navigation session instantly transfers to their mobile browser without downloading an app.

Wheelchair & Stroller Accessibility: A "Step-Free" toggle automatically re-routes the passenger around escalators and staircases, providing a path strictly utilizing ramps and elevators.

Visually Impaired Assistance: Integrates Voice Guidance and Haptic Feedback (vibrations) to tell users exactly when to walk straight, turn, or stop.

Dynamic Congestion & Maintenance Rerouting: If an escalator breaks down, station admins mark it as "Closed" on the dashboard. The routing engine instantly recalculates paths for all active users to avoid that bottleneck.

## Technology Stack
Frontend (Mobile): React Native (allows building for both iOS and Android), ViroReact or ARCore/ARKit for the Augmented Reality overlays.

Frontend (Kiosk & Admin): React.js, packaged as a lightweight PWA for high performance on touchscreen hardware.

Backend: Node.js (Express) for the main API and user management, with a Python microservice to execute the complex graph-theory pathfinding algorithms (A* or Dijkstra's).

Database: PostgreSQL (with PostGIS extension for spatial mapping) for permanent layout data, and Redis for high-speed caching of live train platforms and temporary facility closures.

Mapping/UI: Mapbox GL JS for rendering the 3D isometric base map of the station.

## Dependencies
1. Hardware Requirements: Bluetooth Low Energy (BLE) beacons (e.g., Estimote) installed every 15-20 meters across the station ceilings/walls to triangulate indoor positioning.

2. Design Assets: Official CAD layouts or blueprints of the station from the Ministry of Railways to digitize into node-graph maps.

3. Software APIs: Google Text-to-Speech (TTS) API for voice navigation, and integration with IRCTC/NTES APIs to automatically link real-time train arrivals to specific platform nodes.
