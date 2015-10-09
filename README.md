# Adafruit-Motor-HAT-CppCX-Library
Porting Adafruit-Motor-HAT-Python-Library to Windows 10 IoT Core from here: https://github.com/adafruit/Adafruit-Motor-HAT-Python-Library/tree/master/Adafruit_MotorHAT

##Example Usage

```C++
auto motorDriver = ref new AdafruitMotorHAT(MaxPwmFrequency);
motorDriver->Init();
for (int i = 30; i <= 100; i += 10)
{
  float power = (float)i / 100.0f;
  
  LogInfo("Using power %d", int(power * 100.0f));
  
  motorDriver->Forward(MotorID::Motor1, power);
  motorDriver->Forward(MotorID::Motor2, power);
  
  Sleep(3000);
  
  motorDriver->Coast(MotorID::Motor2);
  motorDriver->Coast(MotorID::Motor1);
  
  Sleep(1000);
}
```
