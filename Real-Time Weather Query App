import streamlit as st
import requests

# OpenWeatherMap API Key (register to get one)
API_KEY = "your_api_key"
BASE_URL = "http://api.openweathermap.org/data/2.5/weather"

# Title
st.title("Real-Time Weather Query App")

# User input for city
city = st.text_input("Enter city name", "Vienna")

if city:
    params = {"q": city, "appid": API_KEY, "units": "metric"}
    response = requests.get(BASE_URL, params=params)
    
    if response.status_code == 200:
        data = response.json()
        st.write(f"**City**: {data['name']}")
        st.write(f"**Temperature**: {data['main']['temp']}°C")
        st.write(f"**Weather**: {data['weather'][0]['description']}")
        st.write(f"**Humidity**: {data['main']['humidity']}%")
    else:
        st.warning("Could not fetch weather data. Please check the city name!")
