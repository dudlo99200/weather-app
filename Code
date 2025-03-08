import requests
def get_weather(city, api_key):
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}&units=metric"
    try:
        response = requests.get(url)
        if response.status_code == 200:
            data = response.json()

            weather = {
                "city": data["name"],
                "temperature": data["main"]["temp"],
                "description": data["weather"][0]["description"],
                "humidity": data["main"]["humidity"],
                "wind_speed": data["wind"]["speed"]
            }
            return weather
        else:
            return f"Error: {response.status_code} - {response.text}"
    except Exception as e:
        return f"Error: {e}"


def main():
    api_key = "YOUR_API_KEY_HERE" 
    print("Welcome to the weather app!")
    while True:
        city = input("\nEnter the city name (or 'exit' to quit): ")

        if city.lower() == "exit":
            print("Goodbye!")
            break

        weather = get_weather(city, api_key)

        if isinstance(weather, dict):
            print(f"\nWeather in {weather['city']}:")
            print(f"Temperature: {weather['temperature']}°C")
            print(f"Description: {weather['description']}")
            print(f"Humidity: {weather['humidity']}%")
            print(f"Wind Speed: {weather['wind_speed']} m/s")
        else:
            print(weather)
if __name__ == "__main__":
    main()          


        

