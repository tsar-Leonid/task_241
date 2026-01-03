**1. Что такое ssh ключи и зачем они нужны?**

SSH-ключи (Secure Shell key) нужны для аутентификации и установления защищённого соединения между клиентом и сервером в протоколе SSH (Secure Shell).
По сути, это цифровой идентификатор, подтверждающий личность при удалённом подключении. SSH-ключи всегда работают парами: публичный ключ размещается на сервере, к которому требуется доступ, приватный хранится в секретности на устройстве.
Когда пользователь пытается подключиться к серверу, происходит криптографическая проверка: если приватный ключ соответствует публичному ключу на сервере, доступ предоставляется мгновенно.

**2. Как их создать?**

для создания SSH-ключей используется команда ssh-keygen -t ed25519

**3. Создайт пару публичный/приватный ключ ed_25519, где они хранятся?**

~/.ssh/id_ed25519 - приватный ключ

~/.ssh/id_ed25519.pub - публичный ключ

<img width="658" height="384" alt="image" src="https://github.com/user-attachments/assets/7ddcfc02-5d61-43d1-8fed-968368602786" />

<img width="573" height="172" alt="image" src="https://github.com/user-attachments/assets/386754c1-26ba-4385-84fe-900dfbd0e3c0" />

**4. Скопируйте публичный ключ на ваш сервер, в каком файле он будет храниться?**

<img width="989" height="192" alt="image" src="https://github.com/user-attachments/assets/4eca7a06-85bc-4e9d-b3aa-0f2494a99114" />

на сервере ключ будет храниться в ~/.ssh/authorized_keys

<img width="837" height="60" alt="image" src="https://github.com/user-attachments/assets/44d56a7d-00f1-4360-9d4d-fc71514bc3f1" />

**5. Попробуйте подключиться к серверу, у вас запросили пароль?**

Пароль не запрашивали

<img width="501" height="41" alt="image" src="https://github.com/user-attachments/assets/459db3e3-82cf-43be-86d2-aac459d9af9a" />

**6. Запретите подключение с паролем для всех пользователей, оставьте только с помощью ключа.**

Запретил подключение с паролем PasswordAuthentication no и не трогал строчку с подключением по ключу(было разрешено сразу)

<img width="948" height="90" alt="image" src="https://github.com/user-attachments/assets/935b2144-e7e1-41b1-bdb3-ee89725227e6" />

<img width="297" height="25" alt="image" src="https://github.com/user-attachments/assets/c5d2321b-d06e-41a3-92cf-afcde67a1fa7" />

<img width="277" height="23" alt="image" src="https://github.com/user-attachments/assets/31f10f66-50a4-453a-b3bb-83621043e16d" />

После этого ещё раз попробовал подключиться, всё нормально, пароль не запрашивает

<img width="520" height="63" alt="image" src="https://github.com/user-attachments/assets/1d4131f6-2545-464b-81ac-7efe67d2e77c" />


