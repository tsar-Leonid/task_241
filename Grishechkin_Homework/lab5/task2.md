**1. Создайте скрипт который создаёт папку заполняет её файлами ( имена 1-4 ) и записывает в них информацию о текущей дате, версии ядра, имени компьютера и списе всех файлов в домашнем каталоге пользователя от которого выполняется скрипт( не забудьте сдлеать проверку на существование файлов и папок)**

создал файл скрипта в домашней директории <img width="327" height="29" alt="image" src="https://github.com/user-attachments/assets/1022cab9-bc6d-4cab-a0f7-7d134ba2d78a" />

далее написал скрипт. Объяснение скрипта: перехожу в домашний каталог пользователя, от имени которого выполняется скрипт; создаю переменную DIR, в которой хранится имя каталога info_dir,
делаю проверку, если каталог не существует, то он создаётся; далее переменным присваиваю нужную нам информацию: дата и время, версия ядра, имя компьютера, список всех файлов и папок в домашнем каталоге пользователя.
циклом for пробегаю по файлам 1 2 3 4, проверяю существование файлов, если нет, то создаю его, вывожу полученную выше информацию и перезаписываю в файлы 

<img width="896" height="662" alt="image" src="https://github.com/user-attachments/assets/8fba773f-b75c-483b-98e8-63d449e94bc1" />

Дал права на выполнение и проверил работу

<img width="470" height="437" alt="image" src="https://github.com/user-attachments/assets/7cc58d90-604f-4080-9548-f89a6fd695b7" />

**2. Создайте юнит который будет вызывать этот скрипт при запуске. Проверьте** 

<img width="509" height="20" alt="image" src="https://github.com/user-attachments/assets/17931f16-c900-4680-a676-ac88626eed4f" /> - создал файл сервиса
  
Содержимое юнита:

<img width="379" height="216" alt="image" src="https://github.com/user-attachments/assets/f461900a-1288-41c4-bd52-c6107ec99fb9" />

Type=oneshot - говорим systemd, что это однократная задача: она запускается и завершается (не остаётся в фоне). ExecStart=/home/spyro/script.sh - путь к скрипту. 
WantedBy=multi-user.target говорит systemd: «Создай ссылку на этот юнит в каталоге зависимостей multi-user.target.wants/». multi-user.target — это стандартный режим загрузки Linux (без GUI).

После перезагрузил конфигурацию systemd - sudo systemctl daemon-reload, sudo systemctl enable script.service - включил сервис для автозапуска. Запусьтл вручную и проверил статус.

<img width="809" height="263" alt="image" src="https://github.com/user-attachments/assets/52ce5767-6b64-45e3-b59a-2d40cc12e274" />

Затем перезагрузил систему sudo reboot и проверил статус (скрипт выполнился при запуске)

<img width="752" height="210" alt="image" src="https://github.com/user-attachments/assets/00dd9ce0-4aaf-4be0-9e1b-9a11c455cea8" />

**3. Создайте таймер который будет вызывать выполнение одноимённого systemd юнита каждые 5 минут.**

<img width="592" height="272" alt="image" src="https://github.com/user-attachments/assets/c7113897-4b20-43fc-b3e6-fb7f950225c5" />

<img width="956" height="397" alt="image" src="https://github.com/user-attachments/assets/9649d8c3-0b99-47d2-bf95-a4f8648f56ba" />

**4. От какого пользователя вызыаются юниты поумолчанию?**

По умолчанию от рута, если не указано иное в секции [Service] в User=

**5. Создайте пользователя от имени которого будет выполняться ваш скрипт.**

<img width="493" height="68" alt="image" src="https://github.com/user-attachments/assets/8eb76ce2-b0d5-4eed-8e60-36bfed4d0a0c" />

**6. Дополните юнит информацией о пользователе от которого должен выплняться скрипт.**

копирую скрипт, делаю владельцем scriptuser и делаю скрипт исполняемым

<img width="717" height="117" alt="image" src="https://github.com/user-attachments/assets/9319cb0f-ca98-46c3-84c2-1417d54eaf97" />

Меняю юнит

<img width="731" height="299" alt="image" src="https://github.com/user-attachments/assets/4fb98421-c5d4-4d1d-857c-9ac51729c205" />

Применил и проверил работу

<img width="568" height="14" alt="image" src="https://github.com/user-attachments/assets/8b0228bd-3a20-4c76-896a-d0084f8b91cc" />
<img width="752" height="292" alt="image" src="https://github.com/user-attachments/assets/028f06b9-cca3-4746-a5d5-c14be9bafe21" />

**7. Дополните ваш скрипт так, что бы он независимо от местоположения всега выполнялся в домашней папке того кто его вызывает.**

В скрипте использовал cd "$HOME" - $HOME автоматически указывает на домашний каталог того пользователя, от имени которого выполняется юнит








