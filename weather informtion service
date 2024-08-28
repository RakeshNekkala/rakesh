import requests

def get_weather(api_key, city):
    
    url = "http://api.weatherstack.com/current"
    
    
    params = {
        'access_key': api_key,
        'query': city
    }
    
    try:
        
        response = requests.get(url, params=params)
        response.raise_for_status()  
        data = response.json()

        
        if 'current' in data:
            weather = data['current']
            temperature = weather['temperature']
            weather_description = weather['weather_descriptions'][0]
            humidity = weather['humidity']
            wind_speed = weather['wind_speed']
            
            
            print(f"Weather in {city}:")
            print(f"Temperature: {temperature}°C")
            print(f"Condition: {weather_description}")
            print(f"Humidity: {humidity}%")
            print(f"Wind Speed: {wind_speed} km/h")
        else:
            print("Could not retrieve weather data. Please check the city name or API key.")
    
    except requests.RequestException as e:
        print(f"Error fetching weather data: {e}")

def main():
    api_key = '77c6e9c2b9df49313fa97ad0e609a395'  
    city = input("Enter the city name: ")
    get_weather(api_key, city)

if __name__ == '__main__':
    main()
