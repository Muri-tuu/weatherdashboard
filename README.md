# weatherdashboard
Build a premium, minimalistic Weather Dashboard application with the following specifications:

## Tech Stack
- React 18+ with TypeScript
- Tailwind CSS
- Framer Motion for animations
- Recharts or Chart.js for data visualization
- React Query for API caching
- OpenWeatherMap API (free tier)
- Lucide React icons

## Design Philosophy
- Apple Weather-inspired aesthetic
- Glassmorphism elements with subtle blur
- Dynamic backgrounds that change based on weather/time of day
- Color palette: Deep blue (#1E3A5F) to purple (#4A1D6A) gradients, white text, accent colors per weather type
- Typography: SF Pro Display style (Inter as fallback)

## Core Features

### 1. Location Management
- Geolocation API for current location detection
- Search bar with autocomplete (city names)
- Save multiple locations (localStorage)
- Quick-switch between saved locations

### 2. Current Weather Hero
- Large temperature display with "feels like"
- Weather condition icon (animated SVG/Lottie)
- High/Low temperatures
- Location name and current time
- Brief condition description ("Partly Cloudy")
- Dynamic background gradient based on:
  - Time of day (dawn, day, dusk, night)
  - Weather condition (sunny, cloudy, rainy, stormy, snowy)

### 3. Hourly Forecast
- Horizontal scrollable strip
- 24-hour forecast
- Each hour shows: time, icon, temperature
- Precipitation probability bars
- Current hour highlighted

### 4. 7-Day Forecast
- Vertical list/cards
- Each day: Day name, condition icon, high/low temps
- Precipitation chance
- Expandable for more details
- Visual temperature range bars

### 5. Weather Details Grid
- Glassmorphic cards in 2x3 or 3x2 grid:
  - **UV Index**: Gauge with severity color (low/moderate/high/extreme)
  - **Wind**: Speed, direction with compass visual, gusts
  - **Humidity**: Percentage with dew point
  - **Visibility**: Distance in km/miles
  - **Pressure**: hPa with trend arrow (rising/falling)
  - **Sunrise/Sunset**: Times with arc visualization showing current position

### 6. Air Quality Index (if available)
- AQI number with color-coded severity
- Pollutant breakdown (PM2.5, PM10, O3, NO2)
- Health recommendations

### 7. Precipitation Radar/Map (Optional Premium)
- Embedded map showing rain/cloud movement
- Playable timeline for next 2 hours

### 8. Weather Alerts
- Banner for severe weather warnings
- Expandable details
- Color-coded by severity

## Interactive Features

### Charts & Visualizations
- Temperature trend line chart (24h or 7d)
- Precipitation bar chart
- Wind speed area chart
- Smooth animations on data load
- Hover tooltips with exact values

### Settings
- Temperature unit toggle (°C/°F)
- Wind speed unit (km/h, mph, m/s, knots)
- Pressure unit (hPa, inHg, mmHg)
- 12/24 hour time format
- Theme toggle (auto/light/dark)
- Notification preferences

## UI/UX Details

### Animations
- Weather icons: Subtle looping animations (sun rays rotating, rain falling, clouds drifting)
- Number transitions: Count-up animation on temperature changes
- Card hover: Subtle lift and glow
- Page transitions: Fade and slide
- Pull-to-refresh on mobile
- Skeleton loaders during fetch

### Responsive Design
- Mobile: Single column, swipeable sections
- Tablet: 2-column grid
- Desktop: Full dashboard layout

### Dark/Light Mode
- Auto-detect system preference
- Manual toggle
- Smooth transition between modes

## Data Handling
- React Query for caching (5-minute stale time)
- Optimistic updates for location changes
- Offline support with last-fetched data
- Error states with retry buttons
- Loading skeletons

## Performance
- Lazy load charts
- Debounced search input
- Memoized components
- Service worker for offline capability

## File Structure
/src
  /components
    /weather (CurrentWeather, HourlyForecast, DailyForecast, WeatherDetails)
    /charts (TemperatureChart, PrecipitationChart)
    /ui (Card, GlassCard, Toggle, SearchInput, WeatherIcon)
  /hooks (useWeather, useGeolocation, useLocalStorage)
  /api (weatherApi.ts, types.ts)
  /utils (formatters, unitConverters, weatherConditions)
  /context (SettingsContext, LocationContext)
  /assets/icons (animated weather SVGs)

## API Integration
- OpenWeatherMap One Call API 3.0
- Endpoints needed:
  - Current weather
  - Hourly forecast (48h)
  - Daily forecast (8 days)
  - Weather alerts
- API key stored in .env
- Rate limiting awareness

Include comprehensive README, environment setup guide, and deploy to Vercel with proper API key handling.
