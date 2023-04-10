import RPi.GPIO as GPIO
import time
import Adafruit_DHT

# Configurar el pin del relé
RELE_PIN = 18
GPIO.setmode(GPIO.BCM)
GPIO.setup(RELE_PIN, GPIO.OUT)

# Configurar el sensor de humedad
SENSOR_PIN = 23
SENSOR_TYPE = Adafruit_DHT.DHT11

# Función para medir la humedad
def medir_humedad():
    humedad, temperatura = Adafruit_DHT.read_retry(SENSOR_TYPE, SENSOR_PIN)
    return humedad

# Función para encender la bomba de agua
def regar():
    GPIO.output(RELE_PIN, GPIO.HIGH)
    time.sleep(5) # Tiempo que la bomba de agua debe estar encendida
    GPIO.output(RELE_PIN, GPIO.LOW)

# Bucle principal
while True:
    humedad = medir_humedad()
    print("Humedad:", humedad)
    
    # Si la humedad es baja, encender la bomba de agua hasta que la humedad alcance el 50%
    if humedad < 50:
        print("Baja humedad, regando...")
        regar()
        while medir_humedad() < 50:
            time.sleep(1)
    
    # Esperar 3 horas antes de volver a medir la humedad
    time.sleep(3 * 60 * 60)
