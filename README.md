Simple library for the TSL45315 Lux Sensor breakout board for Arduino
Initializes the sensor and puts it into "Normal Operation" mode.

Demo sketch:

--- snip ---
#include <Wire.h>
#include <Makerblog_TSL45315.h>

Makerblog_TSL45315 luxsensor = Makerblog_TSL45315(TSL45315_TIME_M4);

uint32_t lux;

void setup() {
  Serial.begin(9600);
  Serial.println("Start");
  Serial.println(luxsensor.begin());
}

void loop() {
  lux = luxsensor.readLux();
  Serial.println(lux, DEC);
  delay(1000);
}
--- snap ---