### Python API Challenge: Weather and Vacation Data Analysis
Project Overview
This project harnesses the power of data to answer a fundamental question: What is the weather like as we approach the equator? By leveraging the OpenWeatherMap API and other Python libraries, this project analyzes weather patterns across 500+ cities worldwide and explores vacation destinations based on ideal weather conditions. This repository is structured into two main parts:

Part 1: WeatherPy – An analysis of weather variables and their relationships with latitude.
Part 2: VacationPy – Using weather data to identify ideal vacation spots and map hotel locations.
Project Structure
css
Copy code
python-api-challenge/
├── WeatherPy/
│   ├── WeatherPy.ipynb
│   ├── api_keys.py
│   └── output_data/
│       ├── northern_lat_vs_temp.png
│       ├── southern_lat_vs_temp.png
│       ├── northern_lat_vs_humidity.png
│       └── ... [other output files]
├── VacationPy/
│   ├── VacationPy.ipynb
│   ├── api_keys.py
│   └── output_data/
│       ├── city_humidity_map.png
│       └── hotel_map.png
├── .gitignore
├── README.md
└── requirements.txt
Getting Started
Prerequisites
Python 3.x installed.
Required libraries:
pandas
matplotlib
numpy
requests
citipy
geopandas
geoviews
API Keys: Sign up and obtain API keys for the following services:
OpenWeatherMap API – for weather data.
Geoapify API – for geolocation and hotel information.
Installation
Clone the Repository:

bash
Copy code
git clone https://github.com/your-username/python-api-challenge.git
cd python-api-challenge
Install Dependencies:

bash
Copy code
pip install -r requirements.txt
Setup API Keys:

Place your OpenWeatherMap and Geoapify API keys in an api_keys.py file:
python
Copy code
# api_keys.py
weather_api_key = "YOUR_OPENWEATHERMAP_API_KEY"
geoapify_key = "YOUR_GEOAPIFY_API_KEY"
Ensure api_keys.py is included in .gitignore to protect your API keys.
Project Workflow
Part 1: WeatherPy
Objective
Visualize and analyze weather data across cities at varying distances from the equator. This part focuses on relationships between latitude and various weather variables.

Instructions
Generate Cities:

Use the citipy library to generate random cities based on latitude and longitude coordinates.
Fetch Weather Data:

Use the OpenWeatherMap API to collect weather data (temperature, humidity, cloudiness, wind speed) for each city.
Create Scatter Plots:

Generate scatter plots for the following relationships:
Latitude vs. Temperature
Latitude vs. Humidity
Latitude vs. Cloudiness
Latitude vs. Wind Speed
Linear Regression Analysis:

Perform linear regression to explore correlations in the Northern and Southern Hemispheres separately.
Plot the regression line, formula, and R-squared value for each relationship:
Northern Hemisphere: Temperature vs. Latitude
Southern Hemisphere: Temperature vs. Latitude
Northern Hemisphere: Humidity vs. Latitude
Southern Hemisphere: Humidity vs. Latitude
Northern Hemisphere: Cloudiness vs. Latitude
Southern Hemisphere: Cloudiness vs. Latitude
Northern Hemisphere: Wind Speed vs. Latitude
Southern Hemisphere: Wind Speed vs. Latitude
Interpretation:

After each pair of plots, discuss observed relationships and trends. Provide insights on how latitude influences each weather variable.
Part 2: VacationPy
Objective
Identify ideal vacation spots based on specific weather criteria and map nearby hotels.

Instructions
Create a Humidity Map:

Map each city using its latitude and longitude, with point sizes representing humidity levels.
Identify Ideal Weather Conditions:

Filter cities based on ideal weather criteria, for example:
Temperature between 21°C and 27°C
Wind speed < 4.5 m/s
Zero cloudiness
Hotel Search:

For each selected city, use the Geoapify API to find hotels within 10,000 meters.
Store city, country, coordinates, humidity, and hotel name in a DataFrame.
Create a Hotel Map:

Map each city with ideal weather conditions, including hotel name and country information in hover messages.
Results
Weather Analysis Findings
Latitude and Temperature: Confirms that temperature increases as cities get closer to the equator.
Latitude and Humidity/Cloudiness/Wind Speed: Weak or no correlations, suggesting other factors influence these variables more significantly than latitude.
Vacation Recommendations
Mapped cities meeting ideal weather conditions with nearby hotels, providing potential vacation destinations based on preferred weather parameters.
Repository Management
.gitignore Setup
Ensure that sensitive files such as api_keys.py are included in your .gitignore to prevent accidental uploads of API keys. Example .gitignore entry:

plaintext
Copy code
# Adding config.py file.
api_keys.py
Commit Structure
Maintain regular commits to track project progression. Each significant change should be committed with a clear and descriptive message.

Additional Resources
OpenWeatherMap API Documentation
Geoapify API Documentation
Citipy GitHub Repository
License
This project is licensed under the MIT License. See the LICENSE file for more details.
