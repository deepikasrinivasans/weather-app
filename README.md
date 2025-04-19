# Weather-App
# Ex03 Weather App Using React
## Date: 19-04-2025
## Name: Deepika S
## Reg no: 2122222300028
## AIM
To build a weather application using React that displays weather details like temperature, wind speed, and sky condition for predefined cities with proper error handling and attractive UI.

---

## ALGORITHM

### STEP 1
Create a React app using `create-react-app`.

### STEP 2
Create a component named `WeatherApp.js`.

### STEP 3
Create a CSS file `WeatherApp.css` for styling.

### STEP 4
Define mock weather data for a few predefined cities (e.g., Chennai, Delhi, Mumbai).

### STEP 5
Add a text input to accept city name from the user.

### STEP 6
Add a search button or "Enter" key functionality to trigger the search.

### STEP 7
Display the corresponding weather data if the city exists in the mock data.

### STEP 8
Show an error message if the city is not found.

### STEP 9
Style the app using modern CSS with background gradients, box shadows, and hover effects.

### STEP 10
Test the application for different valid and invalid city inputs.

### STEP 11
Add screenshots of the UI and weather display.

### STEP 12
Push the code to GitHub and update the README with output images.

---

## PROGRAM

### App.js
```jsx
import React from "react";
import WeatherApp from "./WeatherApp";

function App() {
  return <WeatherApp />;
}

export default App;
```
### WeatherApp.js
```jsx
import React, { useState } from "react";
import "./WeatherApp.css";

const mockWeatherData = {
  "chennai": { temperature: "32°C", windSpeed: "15 km/h", condition: "Sunny" },
  "delhi": { temperature: "28°C", windSpeed: "10 km/h", condition: "Cloudy" },
  "mumbai": { temperature: "30°C", windSpeed: "12 km/h", condition: "Rainy" }
};

const WeatherApp = () => {
  const [city, setCity] = useState("");
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState("");

  const handleSearch = () => {
    const cityKey = city.toLowerCase();
    if (mockWeatherData[cityKey]) {
      setWeather(mockWeatherData[cityKey]);
      setError("");
    } else {
      setWeather(null);
      setError("City not found in our database.");
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === "Enter") handleSearch();
  };

  return (
    <div className="weather-container">
      <h2>Weather App</h2>
      <input
        type="text"
        placeholder="Enter city name"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyDown={handleKeyPress}
      />
      <button onClick={handleSearch}>Get Weather</button>

      {weather && (
        <div className="weather-info">
          <p><strong>Temperature:</strong> {weather.temperature}</p>
          <p><strong>Wind Speed:</strong> {weather.windSpeed}</p>
          <p><strong>Condition:</strong> {weather.condition}</p>
        </div>
      )}

      {error && <p className="error">{error}</p>}
    </div>
  );
};

export default WeatherApp;
```
### WeatherApp.css
```css
body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #89f7fe 0%, #66a6ff 100%);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.weather-container {
  background-color: rgba(255, 255, 255, 0.9);
  max-width: 400px;
  width: 100%;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
  text-align: center;
}

.weather-container h2 {
  color: #333;
  margin-bottom: 20px;
}

.weather-container input {
  padding: 10px;
  width: 65%;
  margin-right: 10px;
  border: 2px solid #ccc;
  border-radius: 8px;
  font-size: 16px;
}

.weather-container input:focus {
  border-color: #66a6ff;
  outline: none;
}

.weather-container button {
  padding: 10px 15px;
  background: #66a6ff;
  color: white;
  border: none;
  border-radius: 8px;
  font-weight: bold;
  cursor: pointer;
}

.weather-container button:hover {
  background: #4e8ef5;
}

.weather-info {
  margin-top: 25px;
  background-color: #f0f8ff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.05);
}

.weather-info p {
  margin: 10px 0;
  font-size: 16px;
}

.error {
  margin-top: 20px;
  color: #ff4d4d;
  font-weight: bold;
}
```
### Output
![image](https://github.com/user-attachments/assets/85d5227a-e93a-49e6-aaa3-fec5c905b98c)
![image](https://github.com/user-attachments/assets/f11fa638-3d6e-4abe-bed1-41e58c7809aa)
![image](https://github.com/user-attachments/assets/725e69e6-d347-4ccd-b72c-cc8e5cebe2bb)
![image](https://github.com/user-attachments/assets/700e5f20-46a0-4a6d-9a0d-2d4ece578689)

![image](https://github.com/user-attachments/assets/512b02c0-364e-46b1-a9b1-cc635ba3413e)

### Result
The React Weather App was successfully created and executed. It displays simulated weather data for predefined cities, handles errors gracefully, and provides an attractive and user-friendly UI.
