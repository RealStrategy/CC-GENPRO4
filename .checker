import requests
from colorama import init, Fore, Back, Style

init(autoreset=True)
bin_number = input('Ingrese el número del BIN: ')
url = f'https://lookup.binlist.net/{bin_number}'

response = requests.get(url)

if response.status_code == 200:
    bin_info = response.json()
    print("")
    print(Fore.RED +"INFORMACION DEL NUMERO BIN" + Fore.RESET) 
    print("")
    print(f'Número de tarjeta: {Fore.GREEN}{bin_number}{Fore.RESET}')
    print(f'Marca de tarjeta: {Fore.GREEN}{bin_info.get("brand", "No disponible")}{Fore.RESET}')
    print(f'Tipo de tarjeta: {Fore.GREEN}{bin_info.get("type", "No disponible")}{Fore.RESET}')
    print(f'Scheme/Network: {Fore.GREEN}{bin_info.get("scheme", "No disponible")}{Fore.RESET}')
    print(f'Largo de la tarjeta: {Fore.GREEN}{bin_info.get("number_length", "16")}{Fore.RESET}')
    print(f'Algoritmo de Luhn: {Fore.GREEN}{bin_info.get("luhn", "Yes")}{Fore.RESET}')
    print(f'País emisor: {Fore.GREEN}{bin_info["country"].get("name", "No disponible")}{Fore.RESET}')
    print(f'Código de país emisor: {Fore.GREEN}{bin_info["country"].get("alpha2", "No disponible")}{Fore.RESET}')
    print(f'Nombre del banco emisor: {Fore.GREEN}{bin_info["bank"].get("name", "No disponible")}{Fore.RESET}')
    print(f'Sitio web del banco emisor: {Fore.GREEN}{bin_info["bank"].get("url", "No disponible")}{Fore.RESET}')
    print(f'Teléfono del banco emisor: {Fore.GREEN}{bin_info["bank"].get("phone","No disponible")}{Fore.RESET}')
    print("")
else:
    print(f'El BIN {bin_number} no es válido o no se encontraron resultados.') 
