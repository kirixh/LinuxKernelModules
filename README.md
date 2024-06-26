## Разработка модулей для ядра linux в рамках учебного задания

### **Phonebook**
Модуль ядра, с которым можно взаимодействовать через символьное устройство. Модуль реализовывает простой телефонный справочник. Справочник для каждого пользователя хранит имя, фамилию, возраст, номер телефона, электронную почту.
Модуль поддерживает:
 - Возвращение всех данных по заданной фамилии пользователя;
 - Добавлять, удалять пользователей;
   
В рамках задачи разработаны и зарегистрированы в ядре системные функции, которые упрощают взаимодействие с символьным устройством.

Для работы с модулем можно:
 - Запустить ядро в QEMU, скомпилировать `test.c` и выполнить.
 - Выполнить скрипт `test.sh`.
 - Наблюдать лог работы при помощи `sudo dmesg`.

### **Keylogger**
Модуль, собирающий статистику о пользователе, а именно считает сколько символов было набрано на клавиатуре за последнюю минуту и выводит этот результат в логи.

Для работы с модулем можно:
- Запустить ядро в QEMU.
- Наблюдать лог работы при помощи `sudo dmesg`.

### Руководство по сборке
В папке scripts реализованы bash-скрипты для сборки initramfs и ядра с модулями.  Ядро собирается оптимально для запуска на QEMU. Размер ядра вместе с initrd составляет 13mb.
1) Соберите модуль при помощи команд `make .` и `build.sh` внутри директории с модулем.
2) Используйте команду `make .` в корневой директории для сборки ядра, и `make run .` для запуска в QEMU.
