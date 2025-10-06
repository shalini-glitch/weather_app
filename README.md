# Weather App 🌤️

A simple Python project that fetches live weather data for any city using the wttr.in API.

## How it works
- User enters a city name.
- The program fetches current weather and forecasts using the wttr.in API.
- Displays temperature, humidity, wind speed, sunrise/sunset times, and forecasts.

## How to run
1. Clone the repository.
2. Install Python.
3. Run:

4. ## Example Code

```python
import requests

city = input("Enter your city here: ")
url = f"https://wttr.in/{city}?format=j1"

try:
    response = requests.get(url, timeout=5)
    response.raise_for_status()
    data = response.json()

    if response.status_code == 200:
        current_condition = data["current_condition"][0]
        print(f"Temperature in {city}: {current_condition['temp_C']}°C")
except Exception as e:
    print("Error:", e)

