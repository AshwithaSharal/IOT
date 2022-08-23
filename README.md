## IoT
*WORD DOCUMENT"<br><br>
https://wokwi.com/projects/333798144987890259 -3 LED<br>

https://wokwi.com/projects/333802283016913490 -RGB single<br>

https://wokwi.com/projects/333806517323039316 -RGB<br>

https://wokwi.com/projects/333807078478971475 -liquid crystal<br>

https://wokwi.com/projects/334344785890378322 -temperature humidity sensor<br>

https://wokwi.com/projects/334348711681327699 -US Sensor<br>

https://wokwi.com/projects/334347782067323474 -IR Sensor<br>

https://wokwi.com/projects/335073076185137748 -Ultrasonic sensor<br>

PIR Sensor:<br>
PIR sensors allow you to sense motion, almost always used to detect whether a human has moved in or out of the sensors range. They are small, inexpensive, low-power, easy to use and don't wear out. For that reason they are commonly found in appliances and gadgets used in homes or businesses. They are often referred to as PIR, "Passive Infrared", "Pyroelectric", or "IR motion" sensors.<br>
Working:<br>
The passive infrared sensor does not radiate energy to space. It receives the  infrared radiation from the human body to make an alarm. Any object with temperature is constantly radiating infrared rays to the outside world. The surface temperature of the human body is between 36° C - 27 ° C and most of its radiant energy concentrated in the wavelength range of 8 um-12 um.<br>
In the detection area, the lens of the detector receives the infrared radiation energy of the human body through the clothing and focused on the pyroelectric sensor. When the human body moves in this surveillance mode, it enters a certain field of view in sequence and then walks out of the field of view. The pyroelectric sensor sees the moving human body for a while and then does not see it, so the infrared radiation of human body constantly changes the temperature of the pyroelectric material. So that it outputs a corresponding signal, which is the alarm signal.<br>
Pin Diagram:<br>
![image](https://user-images.githubusercontent.com/98145023/173380027-511662c7-bd5f-41b9-bf2d-f1c808ecc3ab.png)<br>
Code:<br>
https://wokwi.com/projects/334347041012449875<br>

https://wokwi.com/projects/334432104736621140 -LED FADE<br>

https://wokwi.com/projects/334432905214296659 -LED BUTTON<br>

https://wokwi.com/projects/334433292061246034 -Motion Sensor<br>

https://wokwi.com/projects/334433622983443027 -Motion Sensor LED<br>

https://wokwi.com/projects/334433939640812114 -Motion Sensor Buzzer<br>

https://wokwi.com/projects/334434338424750674 -Ultrasonic Sensor using buzzer<br>

https://wokwi.com/projects/334434924189712979 -Ultrasonic LED<br>

https://wokwi.com/projects/334975929264636499 -Servo motor<br>

https://wokwi.com/projects/334976902300172883 -Servo motor controlled by potentiometer<bt>

https://wokwi.com/projects/334977571156394580 -Button Servo-meter<br>
  
https://wokwi.com/projects/334980059722941011 -Ultrasonic sensor controls  servo motor<br>
  
https://wokwi.com/projects/335070912800883284 -Buzzer beap<br>
  
https://wokwi.com/projects/335066465499611731 -Buzzer beap using push button<br>
  
https://wokwi.com/projects/335612233788686931 -Ultrasonic sensor to blink LED<br>

https://wokwi.com/projects/335700666020266579 -LED using Potentiometer<br><br>

LAB PROGRAMS<br>
1)program1: LED WITH BUZZER<br>
https://wokwi.com/projects/337602112497123922<br><br>
  
2)program2: LED with PUSH BUTTON:<br>
https://wokwi.com/projects/334431214876230226<br><br>

3)Program3:DHT 22 sensor: <br>
https://wokwi.com/projects/337603663792964179<br><br>

4)Program 4: relay with arduino ie Servo motor with BUTTON: <br>
  https://wokwi.com/projects/337603967810798163<br><br>

5)Program 5: LCD DHT 22 <br>
https://wokwi.com/projects/337605922532622930<br><br>


**ESP8266**<br><br>
ULTRASONIC:<br>

const int trigPin = D5;<br>
const int echoPin = D6;<br>
// defines variables<br>
long duration;<br>
int distance;<br>
float inch;<br>
void setup() {<br>
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output<br>
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input<br>
  Serial.begin(9600); // Starts the serial communication<br>
}<br>
void loop() {<br>
  // Clears the trigPin<br>
  digitalWrite(trigPin, LOW);<br>
  delayMicroseconds(2);<br>
  // Sets the trigPin on HIGH state for 10 micro seconds<br>
  digitalWrite(trigPin, HIGH);<br>
  delayMicroseconds(10);<br>
  digitalWrite(trigPin, LOW);<br>
  // Reads the echoPin, returns the sound wave travel time in microseconds<br>
  duration = pulseIn(echoPin, HIGH);<br>
  // Calculating the distance<br>
  distance = duration * 0.034 / 2;<br>
  // Prints the distance on the Serial Monitor<br>
  inch = distance / 2.54;<br>
  Serial.print("Distance: ");<br>
  Serial.print(distance);<br>
  Serial.println(" cm ");<br>
  Serial.print("Inch    : ");<br>
  Serial.print(inch);<br>
  Serial.println(" inches ");<br>
  delay(500);<br>
}<br><br>

TEMPERATURE HUMIDITY SENSOR:<br>
  
#include <Adafruit_Sensor.h><br>
    #include <DHT.h>;<br>
    #define DHTPIN D7   // what pin we're connected to<br>
    #define DHTTYPE DHT11   // DHT 22  (AM2302)<br>
    DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino<br>
    //Variables<br>
    int chk;<br>
    float hum;  //Stores humidity value<br>
    float temp; //Stores temperature value<br>
    void setup()<br>
    {<br>
      Serial.begin(9600);<br>
      dht.begin();<br>
    }<br>
    void loop()<br>
   {<br>
       delay(2000);<br>
       //Read data and store it to variables hum and temp<br>
       hum = dht.readHumidity();<br>
       temp= dht.readTemperature();<br>
       //Print temp and humidity values to serial monitor<br>
       Serial.print("Humidity: ");<br>
       Serial.print(hum);<br>
       Serial.print(" %, Temp: ");<br>
       Serial.print(temp);<br>
       Serial.println(" Celsius");<br>
       delay(1000); //Delay 2 sec.<br>
   }<br><br>
   
LED:<br>
  
void setup() {<br>
  // put your setup code here, to run once:<br>
pinMode(D6,OUTPUT);<br>
}<br>
void loop() {<br>
  // put your main code here, to run repeatedly:<br>
digitalWrite(D6, HIGH);<br>
delay(1000);<br>
digitalWrite(D6, LOW);<br>
delay(1000);<br>
}<br><br><br>

RGB:<br>
  
int red_light_pin= D5;<br>
int green_light_pin = D6;<br>
int blue_light_pin = D7;<br>
void setup() <br>
{<br>
  pinMode(red_light_pin, OUTPUT);<br>
  pinMode(green_light_pin, OUTPUT);<br>
  pinMode(blue_light_pin, OUTPUT);<br>
}<br>
void loop() <br>
{<br>
  RGB_color(255, 0, 0); // Red<br>
  delay(1000);<br>
  RGB_color(0, 255, 0); // Green<br>
  delay(1000);<br>
  RGB_color(0, 0, 255); // Blue<br>
  delay(1000);<br>
  RGB_color(255, 255, 125); // Raspberry<br>
  delay(1000);<br>
  RGB_color(0, 255, 255); // Cyan<br>
  delay(1000);<br>
  RGB_color(255, 0, 255); // Magenta<br>
  delay(1000);<br>
  RGB_color(255, 255, 0); // Yellow<br>
  delay(1000);<br>
  RGB_color(255, 255, 255); // White<br>
  delay(1000);<br>
}<br>
void RGB_color(int red_light_value, int green_light_value, int blue_light_value)<br>
 {<br>
  analogWrite(red_light_pin, red_light_value);<br>
  analogWrite(green_light_pin, green_light_value);<br>
  analogWrite(blue_light_pin, blue_light_value);<br>
}<br><br>

IR:<br>
  
int ir=D5;<br>
int led=D6;<br>
void setup() {<br>
  // put your setup code here, to run once:<br>
  pinMode(ir,INPUT);<br>
    pinMode(led,OUTPUT);<br>
    Serial.begin(9600);<br>
    }<br>
void loop() {<br>
  // put your main code here, to run repeatedly:<br>
  int irvalue=digitalRead(ir);<br>
  if(irvalue==LOW)<br>
  {<br>
    Serial.println("LOW");<br>
    digitalWrite(led,HIGH);<br>
  }<br>
  else<br>
  {<br>
    Serial.println("HIGH");<br>
    digitalWrite(led,LOW);<br>
  }<br>
delay(100);<br>
}<br><br>
ZA void loop()<br>
{<br>
// put your main code here, to run repeatedly:<br>
int irvalue=digitalRead(ir);<br>
if(irvalue==LOW)<br>
{<br>
Serial.println("LOW");<br>
digitalWrite(led,HIGH);<br>
}<br>
else<br>
{<br>
Serial.println("HIGH");<br>
digitalWrite(led,LOW);<br>
}<br>
delay(100);<br>
}<br>


<br>
LDR<br>
const int ldrPin=A0;<br>
void setup() {<br>
Serial.begin(9600);<br>
pinMode(ldrPin,INPUT);<br>
}<br>
void loop()<br>
{<br>
int rawData = analogRead(ldrPin);<br>
Serial.println(rawData);<br>
delay(1000);<br>
}<br>






<br>
LDR_LED<br>
<br>
int ldr=A0;//Set A0(Analog Input) for LDR.<br>
int value=0;<br>
int led=D1;<br>
void setup()
{<br>
Serial.begin(9600);<br>
pinMode(led,OUTPUT);<br>
}<br>

void loop()<br>
{
value=analogRead(ldr);//Reads the Value of LDR(light).<br>
Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.<br>
Serial.println(value);<br>
if(value<50)<br>
{<br>
digitalWrite(led,HIGH);//Makes the LED glow in Dark.<br>
}<br>
else<br>
{<br>
digitalWrite(led,LOW);//Turns the LED OFF in Light.<br>
}<br>
delay(1000);<br>
}<br><br>



LED_CHASER<br>

int pinsCount=6; // declaring the integer variable pinsCount 
int pins[] = {D0,D1,D7,D5,D3,D2}; // declaring the array pins[]<br>

void setup() 
  {<br>
for (int i=0; i<pinsCount; i=i+1)
  { // counting the variable i from 0 to 9 
   pinMode(pins[i], OUTPUT); // initialising the pin at index i of the array of pins as OUTPUT<br> 
  } 
  }<br>

void loop() 
  { 
  for (int i=0; i<pinsCount; i=i+1)
  { // chasing right 
   digitalWrite(pins[i], HIGH); // switching the LED at index i on 
   delay(100); // stopping the program for 100 milliseconds 
   digitalWrite(pins[i], LOW); // switching the LED at index i off 
   } 
  for (int i=pinsCount-1; i>0; i=i-1)
  { // chasing left (except the outer leds) 
  digitalWrite(pins[i], HIGH); // switching the LED at index i on 
  delay(100); // stopping the program for 100 milliseconds 
  digitalWrite(pins[i], LOW); // switching the LED at index i off<br>
} 
}<br>
   




