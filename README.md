###HW4

1. При загрузке системы и меню выбора ядра вошел в режим редактирования. (При любом из трех способов входа в систему без пароля необходимо было удалить строку ```console=ttys0,115200n8```

#1 cпособ
1. Добавил в конце строки, начинающейся с linux 16 ```init=/bin/sh``` и нажал ctrl+x
2. После загрузки системы перемонтировал корень в режиме rw - ```mount -o remount,rw /```

#2 способ
1. Добавил в конце строки, начинающейся с linux 16 ```rd.break``` и нажал ctrl+x
2. Далее попал в корневую файловую систему и поменял пароль администратора:
```
mount -o remount,rw /sysroot
chroot /sysroot
passwd root
touch /.autorelabel
```

#3 способ
1. В строке, начинающейся с linux 16 поменял ```ro``` на ```rw init=/sysroot/bin/sh``` и нажал ctrl+x

#Переименование VG
Логгирование всех команд приведено в файле boot.txt

#Добавление модуля initrd
Логгирование всех команд приведено в файле initrd.txt

