**1. Установите пакет samba**

<img width="960" height="663" alt="image" src="https://github.com/user-attachments/assets/1f7f854e-eb14-4a4c-a663-bc77bb884f8d" />

<img width="960" height="640" alt="image" src="https://github.com/user-attachments/assets/5266e555-0f17-4f55-96ef-1149523edfec" />

**2. ЧТо такое побщая папка, зачем оно может быть нужно?**

Общая папка в Samba — это каталог в Linux, к которому можно получить доступ по сети с других компьютеров (Linux, Windows, macOS).
Она используется для обмена файлами, совместной работы, хранения общих документов или резервных копий.

**3. Создайте общую папку без пароля с правами только на чтение файлов**

<img width="460" height="80" alt="image" src="https://github.com/user-attachments/assets/d3673de2-a6dd-4e63-bafc-f39232333492" />

Добавил в конец файла smb.conf

<img width="377" height="123" alt="image" src="https://github.com/user-attachments/assets/c6a1d1ae-86de-47fe-9662-22e5b25323c2" />

**4. Создайте общую папку с паролем с правами на чтение и запись**

<img width="780" height="543" alt="image" src="https://github.com/user-attachments/assets/cfe76b8e-f870-407b-a543-f9ccf027f140" />

Добавил в конец файла smb.conf

<img width="376" height="127" alt="image" src="https://github.com/user-attachments/assets/75b5f32e-526e-4b29-8fcb-6a28fc738ac1" />

перезапустил systemctl restart smb

Доступ по логину и паролю, чтение и запись

**5. Создайте общую папку с доступом для какой-то группы с полными правами**

<img width="591" height="239" alt="image" src="https://github.com/user-attachments/assets/0a9d5812-d021-4d5c-93b1-8dfe86ed1779" />

Добавил в конец файла smb.conf

<img width="368" height="119" alt="image" src="https://github.com/user-attachments/assets/d3f9557d-ec6f-4e2e-b7c4-6598c5c41388" />

**6. Создайте общую папку в которой у одной группы будет полный доступ, а у другой только доступ на чтение. Третья группа не должна иметь к ней доступа**

<img width="602" height="420" alt="image" src="https://github.com/user-attachments/assets/9b67c6da-969d-4280-8b9a-213d2233d612" />

Добавил в конец файла smb.conf

<img width="401" height="148" alt="image" src="https://github.com/user-attachments/assets/007e537b-39af-4fa6-a48f-532fa297414e" />

fullaccess — полный доступ, readonly — только чтение, другие пользователи — доступа нет


