# plant_waters
Mide la cantidad de humedad en una planta, especificamente en la tierra.
En este ejemplo, se utiliza el módulo "RPi.GPIO" para controlar un LED conectado al pin 18 de la Raspberry Pi. También se utiliza el módulo "Adafruit_DHT" para leer la humedad de un sensor conectado al pin 23. La función "medir_humedad()" lee la humedad del sensor y la devuelve en porcentaje.

El bucle principal mide la humedad y la muestra por consola. Si la humedad es inferior al 30%, el LED se enciende utilizando la función "GPIO.output()". De lo contrario, el LED se apaga. El programa espera 3 horas antes de volver a medir la humedad.

En este código, la función "regar()" enciende el relé durante 5 segundos para activar la bomba de agua. Si la humedad es inferior al 50%, el bucle principal llama a la función "regar()" y espera hasta que la humedad alcance el 50% antes de continuar. El programa espera 3 horas antes de volver a medir la humedad.
