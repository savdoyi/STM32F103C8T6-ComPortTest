# 🏗️ STM32 NEMA 17 Stepper Control
![STM32](https://img.shields.io/badge/STM32F103C8T6-Blue_Pill-007ACC)
![Motor](https://img.shields.io/badge/NEMA17-TB6600-4CAF50)

## 🔌 Pin Configuration
```c
// TB6600 ↔ STM32 Connections
#define ENA_PIN   GPIO_PIN_5  // PB5 (Enable)
#define DIR_PIN   GPIO_PIN_6  // PB6 (Direction)
#define PUL_PIN   GPIO_PIN_7  // PB7 (Pulse)
```

## 📟 Command Syntax
```bash
# Format: [d][vvv][ddd]
d   : 0=CCW, 1=CW, 2=Stop (2 hozircha ishlamaydi)
vvv : 001-999 (tezlik, hozir default 200 RPM)
ddd : 001-999 (gradusda burchak)

# Namuna:
0 050 180  # CCW yo'nalishda 50 tezlikda 180 gradus
1 100 090  # CW yo'nalishda 100 tezlikda 90 gradus
2 000 000  # To'xtatish (ishlamaydi)
```

## 🚀 Foydalanish
1. Hercules dasturini oching
2. Serial portni tanlang (115200 baud)
3. Quyidagi formatda buyruq yuboring:
```plaintext
[Direction][Speed][Angle]
M: 0 300 045
J: 1 250 180
```

## ⚠️ Eslatmalar
```bash
# Hozirgi cheklovlar:
- Tezlik parametri (vvv) hozir ishlamaydi (default=120 RPM)
- 1.8° = 1 step = 32 mikrostepga moslangan kod (NEMA17 uchun TB6600 ning sozlamasi asosida)
```

## 📡 Hercules Sozlamalari
![Hercules Setup](ComPortTest/hercules.png?text=Hercules+Serial+Config)  

📧 Savollar uchun: [savdoyi@ya.ru](mailto:savdoyi@ya.ru)  
🔗 Repo: [github.com/savdoyi/STM32F103C8T6-ComPortTest](https://github.com/savdoyi/STM32F103C8T6-ComPortTest)
