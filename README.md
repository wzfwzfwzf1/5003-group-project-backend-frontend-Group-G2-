# 5003-group-project-backend-frontend-Group-G2-
Hong Kong Airport Route Advisor - Group Project

📋 Project Overview
This is a data-driven web application for analyzing and predicting safety ratings and comfort levels of popular tourist flight routes departing from Hong Kong International Airport. The system integrates aviation safety data, weather information, and airline statistics to provide travelers with comprehensive ratings to help them choose better flights.

Key Features:

Data-driven route safety assessment

Multi-dimensional comfort analysis

Weather impact evaluation

Real-time data processing

Interactive visualization


Project Structure
text
airroute-advisor/
├── backend/                 # Node.js + Express Backend
│   ├── server.js           # Main server file with RESTful API
│   ├── package.json        # Backend dependencies and configuration
│   └── data/               # JSON data files exported from MySQL database
│       ├── airlines.json               ← Exported from `airlines` table
│       ├── airports.json               ← Exported from `airports` table
│       ├── flights.json                ← Exported from `flights` table
│       ├── safety_ratings.json         ← Exported from `safety_ratings` table
│       ├── comfort_reviews.json        ← Exported from `comfort_reviews` table
│       ├── weather.json                ← Exported from `weather` table
│       ├── airline_summary.json        ← Exported from `airline_summary` table
│       ├── route_summary.json          ← Exported from `route_summary` table
│       └── route_monthly_summary.json  ← Exported from `route_monthly_summary` table
├── frontend/               # Pure HTML/CSS/JS Frontend
│   ├── index.html          # Main application page with responsive design
│   ├── style.css           # Modern styling with gradient effects
│   └── app.js              # Frontend logic with dynamic data loading
└── README.md               # This documentation file


Data Export Process:
Database Setup: MySQL database created using the provided schema.sql

Data Population: Real aviation data inserted into the 9 tables

JSON Export: Each table exported using MySQL's JSON export functionality

Data Validation: Exported JSON files validated against schema constraints

Quick Start Guide
Prerequisites
Node.js (v14 or higher)

Web browser (Chrome, Firefox, Safari, or Edge)

Internet connection for external libraries (if any)

Installation Steps
Step 1: Prepare the Environment
bash
# Clone or download the project
git clone <repository-url>
cd airroute-advisor
Step 2: Set Up Backend
bash
cd backend
npm install
Step 3: Start the Backend Server
bash
npm start
# Server starts on http://localhost:3000
Step 4: Access the Application
Open your web browser

Navigate to http://localhost:3000

The application will load automatically

🔧 Technical Architecture
Backend Implementation
Framework: Node.js + Express.js

API Design: RESTful architecture

Data Handling: JSON file-based data storage

CORS: Enabled for cross-origin requests

Port: Default 3000

Frontend Implementation
Technology: Pure HTML5, CSS3, Vanilla JavaScript

Design: Responsive with mobile-first approach

Charts: Custom bar charts using CSS gradients

Interactivity: Event-driven user interface

Styling: Modern CSS with gradients and animations

Data Flow Architecture
text
User Interface → HTTP Request → Express Router → Data Processing → JSON Response → UI Rendering
      ↑                                                                              ↓
      └─────────────── User Interaction ←────────── Dynamic Updates ←───────────────┘
📱 Key Features
1. Intelligent Route Search
Destination filtering with deduplication

Monthly trend analysis

Multiple sorting options (safety, comfort, composite)

Real-time results display

2. Comprehensive Scoring System
Safety Score: Based on historical safety records

Comfort Score: Derived from passenger reviews

Composite Score: Weighted combination (60% safety, 40% comfort)

Weather Impact: Environmental factors consideration

3. Data Visualization
Interactive bar charts for airline comparison

Color-coded scoring system

Responsive design for all screen sizes

Detailed route information panels

4. User Experience
Intuitive filtering interface

Quick search suggestions

Detailed modal views

Loading states and error handling

🔍 API Endpoints
The backend provides the following RESTful API endpoints:

Endpoint	Method	Description	Parameters
/api/destinations	GET	Get all unique destinations	None
/api/airlines	GET	Get airline list	None
/api/popular-destinations	GET	Get popular destinations	limit (optional)
/api/routes	GET	Search routes	destination, month, sort, limit
/api/routes/:airline/:destination	GET	Get route details	airline, destination
/api/stats	GET	Get system statistics	None
Example API Calls:
bash
# Get all destinations
GET http://localhost:3000/api/destinations

# Search routes to Tokyo
GET http://localhost:3000/api/routes?destination=HND&sort=safety_score

# Get route details
GET http://localhost:3000/api/routes/CX/HND
🎯 Use Cases
For Travelers
Compare airlines for specific routes

Choose safest travel options

Select most comfortable flights

Plan travel based on weather conditions

For Airlines
Benchmark performance against competitors

Identify improvement areas

Understand customer satisfaction

Analyze seasonal trends

For Researchers
Access structured aviation data

Study safety-comfort correlations

Analyze weather impact on travel

Examine airline performance metrics

Academic Context
This project demonstrates:

Database Design: From SQL schema to application data

Full-Stack Development: Frontend + Backend integration

Data Processing: JSON manipulation and filtering

User Interface Design: Responsive and intuitive design

API Development: RESTful service creation

Learning Outcomes:
Understanding relational database design

Implementing CRUD operations with JSON

Building responsive web interfaces

Creating data visualization components

Developing RESTful APIs
