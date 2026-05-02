# 🌤️ Weather Dashboard

A beautiful, responsive weather dashboard that fetches real-time data from OpenWeatherMap API.

## ✨ Features

- 🌍 **Search by City** - Find weather for any location
- 📍 **Geolocation** - One-click current location weather
- 🌡️ **Current Weather** - Temperature, humidity, wind speed, UV index, and more
- 📊 **Air Quality Index** - PM2.5, PM10, O₃, NO₂ levels
- 📅 **5-Day Forecast** - Daily min/max temperatures and conditions
- ⏰ **24-Hour Forecast** - Hourly breakdown with precipitation chance
- 💾 **Smart Caching** - 10-minute cache to reduce API calls
- 📱 **Fully Responsive** - Works on mobile, tablet, and desktop
- ♿ **Accessible** - ARIA labels and semantic HTML
- ⚡ **Performance Optimized** - Lazy loading and efficient rendering

## 🚀 Quick Start

### 1. Get API Key

1. Visit [OpenWeatherMap](https://openweathermap.org/api)
2. Sign up for a free account
3. Generate a free API key
4. Copy the key

### 2. Configure API Key

Edit `src/config.js` and replace the `WEATHER_API_KEY`:

```javascript
const CONFIG = {
  WEATHER_API_KEY: 'your_api_key_here', // ← Replace this
  // ... rest of config
};
```

### 3. Open in Browser

```bash
# Simply open the file
open index.html

# Or use a local server
python -m http.server 8000
# Then visit http://localhost:8000
```

## 📁 Project Structure

```
weather-dashboard/
├── index.html           # Main HTML structure
├── src/
│   ├── config.js        # API configuration
│   ├── styles.css       # All styles (responsive)
│   ├── weatherApi.js    # API service with caching
│   ├── weatherDisplay.js # UI rendering logic
│   └── app.js           # Main application controller
└── .gitignore           # Git ignore patterns
```

## 🎨 UI Components

### Header
- Logo with branding
- Search bar with autocomplete
- Geolocation button

### Current Weather Section
- Location name and update time
- Current temperature with "feels like"
- Weather icon and description
- 6-item details grid (humidity, wind, pressure, UV, dew point, visibility)

### Air Quality Section
- AQI level with color coding
- PM2.5, PM10, O₃, NO₂ pollutants

### Hourly Forecast
- 8 items × 3 hours = 24-hour view
- Temperature, icon, description, precipitation chance

### Daily Forecast
- 5-day forecast cards
- Min/max temperatures
- Weather icon and description
- Precipitation probability

## 🔧 Configuration

Edit `src/config.js` to customize:

```javascript
WEATHER_API_KEY: 'your_key',    // Required: Your API key
CACHE_DURATION: 600000,         // Cache time in milliseconds
DEFAULT_CITY: 'Jakarta',        // Default city on load
LANGUAGE: 'en',                 // Language
UNITS: 'metric',                // 'metric' or 'imperial'
```

## 🌡️ Temperature Units

- **Metric (Celsius)**: Set `UNITS: 'metric'`
- **Imperial (Fahrenheit)**: Set `UNITS: 'imperial'`

## 🔒 Security Notes

- Store API key in environment variables for production
- Consider using a backend proxy to hide API key
- Rate limit: Free tier allows 1,000 calls/day

## 📊 API Data Structure

### Current Weather
- Temperature, feels like, humidity
- Wind speed, pressure, visibility
- UV index, dew point
- Weather conditions and icons

### Forecast
- 5-day forecast (3-hourly intervals)
- Daily min/max temps
- Precipitation probability

### Air Quality
- AQI level (1-5)
- PM2.5, PM10 levels
- O₃, NO₂ concentrations

## 🎯 Usage

### Search Weather
1. Type city name in search box
2. Click "Search" or press Enter
3. Weather data loads and displays

### Use Geolocation
1. Click "📍 Current" button
2. Allow location access in browser
3. Weather for current location loads

### View Forecasts
- Scroll down to see hourly and daily forecasts
- Click/tap any forecast item for more details

## 🐛 Troubleshooting

### API Key Error
```
⚠️ API key not configured
```
- Check your API key in `src/config.js`
- Ensure it's valid and active

### City Not Found
```
City not found. Please try another search.
```
- Try a major city first (London, Tokyo, New York)
- Check spelling

### Rate Limit Exceeded
```
API rate limit exceeded. Please try again later.
```
- Wait a moment and try again
- Caching helps reduce API calls

### Geolocation Not Working
- Enable location permissions in browser
- Use HTTPS (required for geolocation)
- Some browsers require user approval

## 🚀 Deployment

### GitHub Pages
```bash
git checkout develop
git push origin develop
# Enable Pages in settings → /develop branch
```

### Netlify
```bash
# Drag & drop this folder
# Or connect GitHub repo
# Auto-deploys on push
```

### Vercel
```bash
npm install -g vercel
vercel
# Follow prompts
```

## 📝 API Reference

### Current Weather
```
GET /data/2.5/weather?lat={lat}&lon={lon}&units={units}
```

### Forecast
```
GET /data/2.5/forecast?lat={lat}&lon={lon}&units={units}
```

### Air Quality
```
GET /data/3.0/air_pollution?lat={lat}&lon={lon}
```

### UV Index
```
GET /data/2.5/uvi?lat={lat}&lon={lon}
```

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Feel free to fork, modify, and use this dashboard!

## 📧 Support

For issues or questions:
1. Check OpenWeatherMap docs: https://openweathermap.org/api
2. Review error messages in browser console
3. Test with different cities/locations

---

Made with ❤️ using OpenWeatherMap API
