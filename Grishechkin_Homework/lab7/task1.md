**1. Какой по умолчанию используется порт для поключения?**

По умолчанию используется 22 порт

**2. Можно ли его изменить? если да то как?**

Да, порт можно изменить. Изменение производится в конфигурационном файле сервера /etc/ssh/sshd_config с помощью параметра Port. После изменения нужно прописывать systemctl restart sshd

**3. Какая служба отвечает за обработку запросов на подключения по ssh?**

Служба sshd (OpenSSH Daemon) отвечает за обработку запросов на подключения по SSH

**4. Какой файл конфигурации отвечает за его настройку?**

/etc/ssh/sshd_config

**5. Попробуйте подключиться по ssh к предоставленному вам серверу**

<img width="791" height="155" alt="image" src="https://github.com/user-attachments/assets/4db412c2-09a3-4aed-9cde-2db79e61a00e" />

**6. Отредактируйте файл настроек на сервере так, чтобы была возможность подключиться к серверу используя пользователя root**

Зашёл в файл конфигурации, добавил строчку PermitRootLogin yes и применил изменения

<img width="469" height="43" alt="image" src="https://github.com/user-attachments/assets/5715443f-f60b-4e0b-b331-566334d68bdc" />

<img width="493" height="83" alt="image" src="https://github.com/user-attachments/assets/823e53a8-2c6a-4373-8c83-e5ac8e0f8c76" />

**7. Измените колличество ошибок ввода пароля перед сборосом соединения, покажите эти измененения**

Изменил значение в файле конфигурации

<img width="158" height="27" alt="image" src="https://github.com/user-attachments/assets/bb855ea2-698b-498f-9085-18f1ba497d9f" />

Проверил и применил изменения

<img width="623" height="63" alt="image" src="https://github.com/user-attachments/assets/570cb5f6-deea-49ff-a669-ab189d7cb6c7" />

**8. Создайте пользователя ssh-user и попробуйте им подключиться к серверу**

<img width="736" height="454" alt="image" src="https://github.com/user-attachments/assets/77fc5d48-6a59-49bd-bba1-f8fd714b4a8b" />

<img width="419" height="72" alt="image" src="https://github.com/user-attachments/assets/bd771211-9d63-4b47-a7f3-8cdc8fec2650" />

**9. Ограничте ему возможность подключения к серверу. 10. Как вы это сделали?**

В файл конфигурации добавил ограничение для пользователя и перезапустил

<img width="498" height="47" alt="image" src="https://github.com/user-attachments/assets/b61ddc31-0874-4b17-8f38-3b122ad7c74e" />


<img width="228" height="47" alt="image" src="https://github.com/user-attachments/assets/f5f2f699-c303-4a87-94fd-0856b863583d" />

Проверил

<img width="776" height="179" alt="image" src="https://github.com/user-attachments/assets/43bb4b16-1df0-45d3-8fca-6d273aeb3a00" />

**11. Что хранится в файле known_hosts?**

<img width="1466" height="133" alt="image" src="https://github.com/user-attachments/assets/a878e18d-4f1a-40eb-a36e-0c65470c9a30" />

Файл ~/.ssh/known_hosts хранит список серверов, к которым пользователь подключался по SSH, и их публичные ключи.
Это позволяет SSH-клиенту проверять подлинность сервера и предотвращает подключение к поддельному серверу.
