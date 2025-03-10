# Reverse Captcha: Detección IA vs Humanos

## Introducción

Este proyecto es un prototipo de **Reverse Captcha**, un mecanismo innovador que permite detectar si el acceso a una página web fue realizado por un agente de IA o por un humano. El desafío consiste en calcular el producto de dos números primos generados aleatoriamente. Se mide el tiempo de respuesta para distinguir entre accesos automatizados (IA) y accesos manuales (humanos).

> **Nota:** Una respuesta ingresada en menos de un segundo se asume como acción de una IA, mientras que un tiempo mayor se asume como respuesta humana. En ambos casos, se concede el acceso, pero se lleva un registro para que el dueño de la página pueda analizar la proporción de accesos de cada tipo.

## Características

- **Generación de números primos:**  
  Se generan dos números primos de 256 bits utilizando la API de criptografía del navegador y un test de primalidad (Miller-Rabin).

- **Validación del desafío:**  
  Se solicita al usuario (o agente) que ingrese el producto de los dos números primos. Se valida la respuesta comparándola con el producto calculado.

- **Detección de agente:**  
  Se mide el tiempo de respuesta mediante `performance.now()`. Una respuesta rápida (≤ 1 segundo) se asume como realizada por una IA.

- **Reporte de accesos:**  
  Se muestran en pantalla contadores diferenciados para accesos de IA y humanos, lo que permite al propietario del sitio conocer el tipo de tráfico.

- **Interfaz responsiva:**  
  Diseño adaptado para facilitar la extracción de datos por agentes automatizados.

## Tecnologías Utilizadas

- **Frontend:**  
  - HTML5
  - CSS3 (diseño responsivo)
  - JavaScript (ES6+)

- **Lógica de Seguridad:**  
  - Generación de números aleatorios y BigInt.
  - Algoritmo de Miller-Rabin para verificación de números primos.
  - Medición de tiempo de respuesta con `performance.now()`.
