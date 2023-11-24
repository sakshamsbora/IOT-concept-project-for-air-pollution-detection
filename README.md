# IOT-concept-project-for-air-pollution-detection
Here we have the code for the project


# CODE HAS TO BE RUNNED ON ARDUINO #
# Should have sensors like mq2 for the project #
\\make sure you are also having the buzzer and a led too//

CODE :_ 
         int smokepin = A1; 
int buzzer = 1; 
int led= 9; 
 float sensorValue; 
 void setup ()
{
pinMode (buzzer, OUTPUT);
pinMode (smokepin, INPUT);
pinMode (led, OUTPUT);
Serial.begin(9600); 
Serial.println("Gas sensor is giving you a warning now");
delay(1800); 
noTone(buzzer);
}
 void loop()
{
sensorValue = analogRead(smokepin);
 Serial.print("Sensor Value: ");
Serial.print(sensorValue);
 if(sensorValue >200)
{
Serial.print(" | Smoke has been detected");
(buzzer,1000,200);
digitalWrite(led, HIGH);
}
else {
noTone(buzzer);
digitalWrite(led, LOW);
}
Serial.println("");
delay(1200);
}

