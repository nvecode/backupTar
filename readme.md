# Программа создания бэкапов/ресторов в ОС семейнства Linux

Скрипт на bash, который позволяет выполнять бэкопирование файлов/директорий с указанием нужной глубины полных/инкреметных копий.
В программе доступно 3 режима:
1) Инкрементное бэкопирование
2) Полное бэкопирование
3) Восстановление

backupscript_interact - добавление интерактивных функций, включая просмотр содержимого бэкапа перед восстановлением.
backupscript_no_interact - первая версия бэкопирования при помощи tar.


Примеры запуска скрипта backupscript_interact:
1) Полный бэкап в 00:00 каждое воскресенье: 
```
0 0 * * 0 /usr/local/bin/backupTar backup full /backups/ nextcloud /opt/nextcloud/nextcloud-data/data/ 2 14 >> /var/log/backupTar/backup.log 2>&
```
2) Инкреметный бэкап в 00:00 с понедельника по субботу:
```
0 0 * * 1-6 /usr/local/bin/backupTar backup incr /backups/ nextcloud /opt/nextcloud/nextcloud-data/data/ 2 14 >> /var/log/backupTar/backup.log 2>&1
```