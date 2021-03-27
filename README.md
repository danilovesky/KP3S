# Marlin 2.0.7.2 for Kingroon KP3S

* Пауза во время печати
* EEPROM переведен на отдельную внутреннюю память
* Замена филамента во время печати
* Управление ретрактами во время печати
* Smoothieware алгоритм для драйверов
* После отключения электричества - возобнавление печати (могут быть сбои)
* Поддержка работы TMC 2209 без смены прошивки (нужно изменить шаги  X-79.8, Y-80.3, Z-400.8, E-95.4 )
  * Bmg/Titan E TMC 2209 - 404.5 шагов
  * Bmg/Titan E TMC 2225 - 810 шагов
* Добавлена функция подсветки рабочей области. Использовать LED - ленту или светодиоды на 5V
  ![alt text](photo_2020-10-27_00-29-01.jpg)

* Автоматическое включение/выключение вентилятора хотенда при достижении температуры в 100C (выключение происходит когда температура опускается ниже 100C) Чтобы активировать эту функцию, нужно подключить вентилятор к выводам HE1
  ![alt text](photo_2020-10-13_15-37-47.jpg)

* В прошивке включен Junction Deviations (0.036)
* Показывает процент печати: сколько времени печататает и сколько осталось времени печати (настраивается через плагин CuraPlugin_AddPctComplete.py который нужно поместить в C/Ultimaker Cura/plugins после в CURA через расширения пост-обработки добавить скрипт Display Progress On LCD)
* Показывает сколько затрачено пластика в "мм"
* Активирован Linear Advance (значение настраивается через слайсер) только с TMC2209/TMC2226
* Есть небольшая проблема с переэкструзией пластика.  Лечится заменой драйвера экструдера, либо настройкой потока в CURA

После установки прошивки инициализировать EEPROM, провести калибровку PID экструдера (запустить в печать PidCalibration.gcode), и сохранить настройки.
