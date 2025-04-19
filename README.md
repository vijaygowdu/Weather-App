## Weather-App
## Name : K Vijay
## Reg No : 212223040236
## Dtae : 19/04/2025
## Program :
### App.js:
```
import React, { useState } from 'react';
import './App.css';

const weatherData = {
  hyderabad: { temperature: "32°C", wind: "15 km/h", sky: "Sunny" },
  delhi: { temperature: "28°C", wind: "10 km/h", sky: "Cloudy" },
  mumbai: { temperature: "30°C", wind: "8 km/h", sky: "Humid" },
  chennai: { temperature: "34°C", wind: "12 km/h", sky: "Hot" },
};

function WeatherApp() {
  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState('');

  const handleSearch = () => {
    const cityKey = city.toLowerCase();
    if (weatherData[cityKey]) {
      setWeather(weatherData[cityKey]);
      setError('');
    } else {
      setWeather(null);
      setError('City not found in our database.');
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === 'Enter') handleSearch();
  };

  return (
    <div className="app">
      <h1>Weather App</h1>
      <input
        type="text"
        placeholder="Enter city name..."
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyPress={handleKeyPress}
      />
      <button onClick={handleSearch}>Search</button>

      {weather && (
        <div className="weather-info">
          <p><strong>Temperature:</strong> {weather.temperature}</p>
          <p><strong>Wind Speed:</strong> {weather.wind}</p>
          <p><strong>Sky:</strong> {weather.sky}</p>
        </div>
      )}
      {error && <p className="error">{error}</p>}
    </div>
  );
}

export default WeatherApp;
```
### App.css:
```
body {
  background: linear-gradient(to right, #74ebd5, #ACB6E5);
  height: 100vh;
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.app {
  text-align: center;
  padding-top: 80px;
  color: #333;
}

h1 {
  color: #fff;
  font-size: 40px;
  margin-bottom: 40px;
}

input {
  padding: 12px;
  width: 260px;
  border: 2px solid #ffffff;
  border-radius: 8px;
  font-size: 16px;
  outline: none;
}

button {
  padding: 12px 25px;
  margin-left: 10px;
  background-color: #4A90E2;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.3s ease;
}

button:hover {
  background-color: #357ABD;
}

.weather-info {
  margin-top: 30px;
  background-color: rgba(255, 255, 255, 0.8);
  display: inline-block;
  padding: 25px 40px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  font-size: 18px;
  color: #333;
}

.error {
  margin-top: 30px;
  color: #ff4d4d;
  font-weight: bold;
}
```
## Output :
![WhatsApp Image 2025-04-19 at 13 36 21_563c3b4e](https://github.com/user-attachments/assets/49ecf360-6f66-4650-88a5-e400d6332469)
![WhatsApp Image 2025-04-19 at 13 37 30_0a40187d](https://github.com/user-attachments/assets/512cd0f2-f1b1-4adf-a40b-b8a60a243021)
![WhatsApp Image 2025-04-19 at 13 37 57_1dc3d913](https://github.com/user-attachments/assets/dc649f14-8b3a-445d-abe2-3f9e7b0446a7)


