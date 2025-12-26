import requests

def get_weather(kota):
    # Menggunakan API gratis dari Open-Meteo
    url = f"https://api.open-meteo.com/v1/forecast?latitude=-6.21&longitude=106.85&current_weather=true"
    
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        temp = data['current_weather']['temperature']
        print(f"Suhu saat ini di Jakarta: {temp}°C")
    else:
        print("Gagal mengambil data.")

if __name__ == "__main__":
    get_weather("Jakarta")
    
