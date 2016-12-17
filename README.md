#define  sensorPin  A0
#define buzzer_pin 6 //定义蜂鸣器驱动引脚
#define buzzer_fre 600 //定义蜂鸣器输出频率
int state;

void setup()
{
  pinMode(sensorPin, INPUT);
  pinMode(buzzer_pin,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  state = analogRead(sensorPin);
  Serial.print("state:");
  Serial.println(state);
  delay(10);
  if(state>300)
  { tone(buzzer_pin,buzzer_fre);    //驱动蜂鸣器   
  }
  else
  {
    noTone(buzzer_pin);
  }
  }
