# Tarea-Estructura-de-datos
Codigo en readme file

import requests, re
def extractfromregularexpresion(regex, data):
    if data:
        return re.findall(regex, data )
    return None
data = requests.get("https://raw.githubusercontent.com/elastic/examples/master/Common%20Data%20Formats/apache_logs/apache_logs").text
regex = r"(\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3})\s-\s-\s\[(\d{2}\/\b[a-zA-Z]{3}\b\/\d{4})\:(\d{2}\:\d{2}\:\d{2})"

resultado = extractfromregularexpresion(regex, data)
for i in range(len(resultado)):
  print(f"La ip: {resultado[i][0]}, la fecha es: {resultado[i][1]} y la hora es: {resultado[i][2]}")
