# CNCShieldGRBL
GRBL software adapted for using with Arduino Nano CNC Shield
Пины отвечающие за шаг и направление отличаются у Arduino Nano и Arduino Uno, поэтому залитая в Arduino Nano прошивка GRBL работать не будет.
Для того чтобы она заработала надо внести изменения в файл cpu_map_atmega328p.h (для версии grbl 0.9 и ранее) или cpu_map.h (для версии 1.1f). Находим в них следующие строки:

#define X_STEP_BIT 2
#define Y_STEP_BIT 3
#define Z_STEP_BIT 4
#define X_DIRECTION_BIT 5
#define Y_DIRECTION_BIT 6
#define Z_DIRECTION_BIT 7

и приводим их в такой вид:

#define X_STEP_BIT 5
#define Y_STEP_BIT 6
#define Z_STEP_BIT 7
#define X_DIRECTION_BIT 2
#define Y_DIRECTION_BIT 3
#define Z_DIRECTION_BIT 4

Сохраняем файл и заливаем прошивку через Arduino IDE 
