# CODTECH-Task1
#CODTECH_IT_SOLUTIONS 
import requests
import matplotlib.pyplot as plt

url = "https://api.example.com/data"
headers = {"Authorization": "Bearer YOUR_API_KEY"}
response = requests.get(url, headers=headers)

if response.status_code == 200:
    data = response.json()
    dates = [entry['date'] for entry in data]
    values = [entry['value'] for entry in data]

    plt.figure(figsize=(10, 5))
    plt.plot(dates, values, marker='o', linestyle='-', color='g')
    plt.xlabel("Date")
    plt.ylabel("Value")
    plt.title("API Data Visualization")
    plt.xticks(rotation=45)
    plt.show()
else:
    print("Error:", response.status_code)
