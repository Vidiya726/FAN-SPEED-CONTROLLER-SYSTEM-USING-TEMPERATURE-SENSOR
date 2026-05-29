# FAN-SPEED-CONTROLLER-SYSTEM-USING-TEMPERATURE-SENSOR
## EXP 1(A) FAN SPEED CONTROLLER SYSTEM USING TEMPERATURE SENSOR

### Aim:
	To measure the Temperature using DHT11/DHT22/TMP36  sensor with Arduino UNO Board/ESP-32 using Tinker CAD.

# Hardware / Software Tools required:
	PC/ Laptop with Internet connection
    Tinker CAD tool (Online)
	Arduino UNO Board/ESP-32
	Temperature Sensor (DHT11/DHT22/TMP36)

# Circuit Diagram:
<img width="983" height="677" alt="Screenshot 2026-05-29 114414" src="https://github.com/user-attachments/assets/62cbc7ae-4a3e-480f-bfa7-d4550e923436" />

# Procedure 

# Program
```
const int analogIn = A0;

int humiditysensorOutput = 0;

// Defining Variables
int RawValue = 0;
double Voltage = 0;
double tempC = 0;
double tempF = 0;

void setup()
{
    Serial.begin(9600);
    pinMode(A1, INPUT);
}

void loop()
{
    RawValue = analogRead(analogIn);

    Voltage = (RawValue / 1023.0) * 5000;   // Convert to millivolts
    tempC = (Voltage - 500) * 0.1;          // 500 mV offset
    tempF = (tempC * 1.8) + 32;             // Convert to Fahrenheit

    Serial.print("Raw Value = ");
    Serial.print(RawValue);

    Serial.print("\t milli volts = ");
    Serial.print(Voltage, 0);

    Serial.print("\t Temperature in C = ");
    Serial.print(tempC, 1);

    Serial.print("\t Temperature in F = ");
    Serial.println(tempF, 1);

    humiditysensorOutput = analogRead(A1);

    Serial.print("Humidity: ");
    Serial.print(map(humiditysensorOutput, 0, 1023, 10, 70));
    Serial.println("%");

    delay(5000);   // Iterate every 5 seconds
}
```
# Output
<img width="1040" height="524" alt="Screenshot 2026-05-29 114601" src="https://github.com/user-attachments/assets/95d7ee55-ae8c-479b-b13b-c2c5a8b303c0" />
<img width="846" height="420" alt="Screenshot 2026-05-29 114620" src="https://github.com/user-attachments/assets/33681449-e7eb-4b52-be47-9b2695a534ef" />


# Result
The Temperature using DHT11/DHT22/TMP36 sensor with Arduino UNO Board/ESP-32 using Tinker CAD is simulated.

