**1. Где хранятся пользвательские и системные настройки подключения?**

Пользовательские настройки: ~/.ssh/config

Системные настройки: /etc/openssh/ssh_config

**2. Что за файл options?**

Файл options — это пользовательский SSH-конфиг, в котором можно прописать алиас сервера, имя пользователя и порт, чтобы при подключении не вводить их вручную.
Современные версии OpenSSH не используют options, это устаревший формат. Сейчас вместо него используется ~/.ssh/config — пользовательский SSH-конфиг.

**3. Отредактируйте файл options так, чтобы можно было подключаться не вводя имя пользвателя и порт. 4. Назовите подключение удобным для вас спсобом. 5. Проверьте работоспособность**

<img width="513" height="132" alt="image" src="https://github.com/user-attachments/assets/160434b0-9a6d-4665-a804-776c0b8d5404" />

<img width="487" height="80" alt="image" src="https://github.com/user-attachments/assets/3668116f-821e-448e-ae9d-3c2a1cad9af8" />

Вылезала эта штука, подумал, что может быть из-за options, сделал через ~/.ssh/config, но там тоже так

<img width="778" height="184" alt="image" src="https://github.com/user-attachments/assets/8dab6176-e550-48a7-bf6a-991a1bcfa6a7" />

попробовал через другие порты, там аналогично

<img width="828" height="255" alt="image" src="https://github.com/user-attachments/assets/a8acf90b-5dcf-41dc-93e9-19bad39f536e" />

обычным путём тоже перестало работать 

<img width="496" height="81" alt="image" src="https://github.com/user-attachments/assets/9e7d03db-a502-4c99-ba39-8af1012b63d0" />

как понял оно подключается, но сразу рвётся соединение и что-то с серваками

Заработало!

<img width="785" height="205" alt="image" src="https://github.com/user-attachments/assets/4a0441b6-60ea-4ab2-8bdc-6226f8e60806" />
