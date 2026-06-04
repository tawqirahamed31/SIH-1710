# Smart India Hackathon Workshop
# Date:
## Register Number:212225240166
## Name: Tawqir Ahamed Sayeed L
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## Problem Description
Background: Railway stations are complex environments with numerous facilities and locations such as ticket counters, platforms, restrooms, food courts, and waiting areas. Passengers often face difficulties in navigating these spaces, especially in large or unfamiliar stations. Efficient and user-friendly navigation systems are crucial for improving passenger experience, reducing congestion, and ensuring timely travel connections. Description: The problem involves developing a comprehensive navigation solution for railway stations that assists passengers in locating various facilities and destinations within the station premises. This includes creating detailed maps, providing real-time directions, and integrating features such as accessibility options for individuals with disabilities. The solution should be intuitive, easy to use, and accessible via multiple platforms, including mobile devices and digital kiosks. Key challenges include updating navigation information in real-time, ensuring accuracy, and accommodating the diverse needs of all passengers. Expected Solution: The expected solution is a multi-platform navigation system that provides detailed, real-time directions to all facilities and locations within a railway station. This system should include: A mobile application with 3D interactive maps and step-by-step navigation. Digital kiosks located throughout the station with touch-screen interfaces. Voice-guided navigation for visually impaired passengers. Regular updates to reflect changes in station layout and facility locations. Integration with existing railway apps and services for seamless user experience. The solution should enhance the overall passenger experience by reducing confusion, saving time, and improving accessibility within the station.

## Problem Creater's Organization
Ministry of Railway

## Idea

RailNav AI is an intelligent indoor navigation platform for railway stations. Unlike existing solutions that rely on fixed beacon hardware, RailNav uses Visual Positioning System (VPS) — the phone camera identifies the passenger's location by matching live frames against a pre-indexed station image database. This requires zero infrastructure changes to existing stations.

Passengers enter their PNR at entry and the system proactively routes them: "Your train leaves in 22 min from Platform 7. Coach S4 is at position 3 from the front." The engine routes around live crowd density estimated via lightweight pose detection on CCTV feeds, and works fully offline — critical in stations with poor connectivity.

## Proposed Solution / Architecture Diagram
Passenger Mobile App
Flutter app with 3D station maps, step-by-step navigation, voice guidance, AR overlay, and offline routing. PNR input auto-triggers proactive guidance.

Visual Positioning Engine
Phone camera matches frames against a pre-indexed station image DB. No beacons or NFC tags required. Falls back to QR scan at entry for cold start.

Route Engine
Graph-based pathfinding (A*) on the station floor graph. Weighted by real-time crowd density from CCTV pose estimation. Accessibility-aware (lifts, ramps).

Digital Kiosks
Touch-screen kiosks at entrances and concourses running the same route engine. QR code printed for the route to continue on mobile

Crowd Intelligence
YOLOv8-nano or MediaPipe on CCTV frames estimates zone-wise crowd density. Feeds live into the routing weights — dense zones get higher path cost.

Emergency Mode
On fire/security alert, system overrides all routes with evacuation paths to the nearest safe exit. Pushed as high-priority notification to all active sessions.

<img width="1081" height="641" alt="railnav-architecture" src="https://github.com/user-attachments/assets/f36ec3e9-ca02-479a-9296-612be2165941" />

## Use Cases
<img width="1125" height="768" alt="usecase" src="https://github.com/user-attachments/assets/2a96ad3c-23fd-4fc4-b090-0aea158e7819" />



## Technology Stack
Kiosk / Web:
React.js
Next.js
Three.js
Mapbox GL

Backend:
Node.js + Express
Socket.io (realtime)
PostgreSQL
Redis (cache)

AI / ML:
YOLOv8-nano (crowd)
MediaPipe (pose)
VPS image indexing
Google STT / TTS
NLLB (translation)

Navigation Engine:
A* pathfinding
Dijkstra (fallback)
Graph DB (Neo4j)
NTES API (trains)

Mobile App:
Flutter
Three.js (3D maps)
Mapbox GL
flutter_tts
speech_to_text

## Dependencies

Mapping service- 30 days

Data collection- 50 days

budget- rs.1,50,000
