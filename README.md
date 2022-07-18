int s0_pin =8;
int s1_pin =9;
int s2_pin =12;
int s3_pin =11;
int out_pin =10;
void setup()
{
Serial.begin(9600);
pinMode(s0_pin, OUTPUT);
pinMode(s1_pin, OUTPUT);
pinMode(s2_pin, OUTPUT);
pinMode(s3_pin, OUTPUT);
pinMode(out_pin, INPUT);
digitalWrite(s0_pin,HIGH);
digitalWrite(s1_pin,LOW);
}
void loop() {
digitalWrite(s2_pin,LOW);
digitalWrite(s3_pin,LOW);
int pale_yellow_color = pulseIn(out_pin, LOW);
pale_yellow_color = map(pale_yellow_color, 25,72,255,0);
delay(50);
digitalWrite(s2_pin,HIGH);
digitalWrite(s3_pin,HIGH);
int bright_yellow_color = pulseIn(out_pin, LOW);
bright_yellow_color = map(bright_yellow_color, 30,90,255,0);
delay(50);
digitalWrite(s2_pin,LOW);
digitalWrite(s3_pin,HIGH);
int deep_orange_color = pulseIn(out_pin, LOW);
deep_orange_color = map(deep_orange_color, 25,70,255,0);
delay(50);
Serial.print("PALE_YELLOW: ");
Serial.print(pale_yellow_color);
Serial.print(" ");
Serial.print("BRIGHT_YELLOW: ");
Serial.print(bright_yellow_color);
Serial.print(" ");
Serial.print("DEEP_ORANGE: ");
Serial.print(deep_orange_color);
Serial.println(" ");
delay(1000);
}
