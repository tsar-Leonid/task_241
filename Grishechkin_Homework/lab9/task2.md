**1. Удалите iptables и установите firewalld**

Удалил iptables
<img width="1469" height="257" alt="image" src="https://github.com/user-attachments/assets/261e67cc-ff7f-479c-8864-1b6b657946af" />

Установил firewalld
<img width="1468" height="742" alt="image" src="https://github.com/user-attachments/assets/4610f3e9-7796-4009-a715-2eaee83d11c0" />

Запустил и добавил в автозагрузку, проверил
<img width="1026" height="349" alt="image" src="https://github.com/user-attachments/assets/a4770fd8-f788-4ccc-96de-e71c80764e30" />

**2. Попробуйте так-же проверить возможность подключения по ssh**

<img width="467" height="43" alt="image" src="https://github.com/user-attachments/assets/41d9527d-1a56-4879-90bf-de0459d107aa" />

**3. Если её нет то откройте порт**

У меня получилось подключиться, но если бы нет, то нужно было бы использовать команду **sudo firewall-cmd --add-port=212/tcp**

**4. Выведите список открытых портов с помощью firewall-cmd**

<img width="555" height="40" alt="image" src="https://github.com/user-attachments/assets/02e63a77-d5fa-424b-b270-287e1adc2770" />

**5. Можно ли там добавить порты по названию сервиса?**

Да, в firewalld можно разрешать доступ не только по номеру порта, но и по имени сервиса.

Например, для добавления сервиса ssh - **sudo firewall-cmd --add-service=ssh**
Для проверки, что сервис добавлен - **sudo firewall-cmd --list-services**

**6. На вашей Локальной виртуальной машине попробуйте подключиться к серверу samba из предыдущих заданий**

Что-то не получается 

<img width="550" height="60" alt="image" src="https://github.com/user-attachments/assets/2521d457-55b6-43f3-b631-667defa19405" />

<img width="432" height="41" alt="image" src="https://github.com/user-attachments/assets/f0fbb439-2007-4b53-962d-14296fad6a71" />

**7. Если не получилось то откройте нужные порты**

<img width="669" height="381" alt="image" src="https://github.com/user-attachments/assets/4da82e58-f6b9-49a8-a62c-3a8bcfbed9b6" />

**8. Сделайте так чтобы изменения были постоянными**

--permanent - означает что добавляем постоянное правило, после этого нужно перезагрузить правила, применить sudo firewall-cmd --reload
