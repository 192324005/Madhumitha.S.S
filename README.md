import requests

api_key = '<YOUR_API_KEY>'
city_name = '<CITY_NAME>'

api_endpoint = 'https://api.openweathermap.org/data/2.5/weather'
query_params = {'q': city_name, 'appid': api_key, 'units': 'metric'}

response = requests.get(api_endpoint, params=query_params)

if response.status_code == 200:
    data = response.json()
else:
    print(f'Error: {response.status_code} - {response.text}')
