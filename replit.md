# WeatherWise - AI-Powered Weather Prediction Application

## Overview

WeatherWise is a full-stack web application designed for the NASA Space Apps Challenge project "Will it Rain on My Parade?". The application provides intelligent weather forecasting using AI models (ARIMA and LSTM) to predict rainfall probability for specific locations and time periods. It offers three core features: current weather data retrieval, location-based weather search with forecasting, and route-based weather analysis for travel planning.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side is built using React with TypeScript, following a component-based architecture. The UI leverages shadcn/ui components for consistent design patterns and Tailwind CSS for styling. The application uses Wouter for client-side routing and TanStack Query for efficient data fetching and state management. Interactive visualizations are implemented using Plotly.js for weather charts and data presentation.

### Backend Architecture
The server is built on Express.js with TypeScript, providing RESTful API endpoints for weather data operations. The application implements a modular routing system with middleware for request logging and error handling. Weather data is fetched from the OpenWeatherMap API and processed for both current conditions and forecasting.

### Data Storage Solutions
The application uses a PostgreSQL database managed through Drizzle ORM with type-safe schema definitions. The database stores weather data, route weather information, and ML predictions. For development and prototyping, an in-memory storage implementation provides the same interface as the database layer, allowing for flexible deployment scenarios.

### Database Schema Design
Three main entities are defined:
- `weatherData`: Stores current and historical weather information including temperature, humidity, pressure, wind data, and precipitation metrics
- `routeWeather`: Contains route-specific weather analysis with waypoint data and overall rain probability assessments  
- `mlPredictions`: Houses AI-generated predictions with confidence scores from both ARIMA and LSTM models

### API Integration Strategy
The backend integrates with OpenWeatherMap's Current Weather and Forecast APIs to retrieve real-time weather data. The system supports both location-name queries and coordinate-based requests for geolocation functionality. API responses are normalized and stored locally to reduce external API calls and improve response times.

### Machine Learning Implementation
The application includes simplified implementations of ARIMA (time series forecasting) and LSTM (neural network) models for rain prediction. These models analyze historical weather patterns to generate probability scores and confidence ratings. The ML prediction system combines multiple model outputs to provide comprehensive rainfall forecasting.

### Development and Build Process
The project uses Vite for fast development builds and hot module replacement. The build process compiles both frontend React code and backend Node.js code for production deployment. TypeScript configuration ensures type safety across the entire codebase with shared schemas between client and server.

## External Dependencies

### Weather Data Provider
- **OpenWeatherMap API**: Primary source for current weather conditions and forecast data
- Requires API key configuration via environment variables
- Supports both city-name and coordinate-based queries

### Database Infrastructure  
- **PostgreSQL**: Production database for persistent data storage
- **Neon Database**: Serverless PostgreSQL provider for cloud deployment
- **Drizzle ORM**: Type-safe database queries and migrations

### UI Component Libraries
- **Radix UI**: Headless component primitives for accessibility and functionality
- **shadcn/ui**: Pre-built component library built on Radix UI
- **Tailwind CSS**: Utility-first CSS framework for styling

### Data Visualization
- **Plotly.js**: Interactive charting library for weather data visualization
- Loaded dynamically to optimize initial bundle size

### Development Tools
- **Replit**: Primary development and deployment platform
- **Vite**: Build tool and development server
- **TypeScript**: Type safety across frontend and backend code

### Frontend State Management
- **TanStack Query**: Server state management and data fetching
- **React Hook Form**: Form validation and management

### Geolocation Services
- **Browser Geolocation API**: Used for detecting user's current location
- Integrated with weather API for location-based forecasts