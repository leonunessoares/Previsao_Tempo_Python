# Previsao_Tempo_Python

# pip install beautifulsoup4

# Previsão do tempo para a cidade do Rio de Janeiro

from bs4 import BeautifulSoup

import requests

html = requests.get("https://www.climatempo.com.br/previsao-do-tempo/cidade/321/riodejaneiro-rj").content

soup = BeautifulSoup(html, 'html.parser')

resume = soup.find(class_='-gray-line')

tempoMin = soup.find(id='min-temp-1')

tempMax = soup.find(id='max-temp-1')

print('Previsão tempo no Rio de Janeiro')

print('Temperatura mínima: ' + tempoMin.string)

print ('Temperatura máxima: ' + tempMax.string)
