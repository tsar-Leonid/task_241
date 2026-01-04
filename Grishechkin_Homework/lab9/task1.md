**1. Установите iptables**

<img width="667" height="258" alt="image" src="https://github.com/user-attachments/assets/748736b4-1359-4386-8988-2db5228ea7fc" />

<img width="1470" height="434" alt="image" src="https://github.com/user-attachments/assets/d1eb9eed-aaa5-4dac-9fdc-832bca92dd12" />

**2. Проверьте осталась ли возможность подключения по ssh к вашему серверу**

<img width="532" height="64" alt="image" src="https://github.com/user-attachments/assets/91702115-5ff7-4c11-b585-e9fa6a43c711" />

**3. Почему может пропасть такая возможность?**

После настройки iptables доступ по SSH может перестать работать, потому что firewall блокирует входящие соединения. 
Если не добавить правило для TCP-порта 212, новые подключения к серверу через SSH не смогут пройти.

**4. Откройте нужный порт на сервере чтобы восстановить подключение**

<img width="889" height="207" alt="image" src="https://github.com/user-attachments/assets/a3d63199-d2a2-4ed1-9bea-76b5258a0d82" />

-A INPUT добавляю (-A = append) правило в цепочку INPUT (входящие соединения), -p tcp правило применяется только к TCP-протоколу, --dport 212 применяю правило к портy назначения 212 + проверил

**5. Это будет udp или tcp прот?**

TCP, так как SSH работает поверх TCP-протокола

**6. Сохраняются ли записанные вами правила после перезагрузки?**

Нет, правила iptables не сохраняются автоматически и будут удалены после перезагрузки системы.

**7. Как их сохранить?**

Сохранил текущие правила в файл и создал systemd-сервис для автозагрузки правил

<img width="1253" height="327" alt="image" src="https://github.com/user-attachments/assets/3acad8eb-d4fb-46e2-ab3e-f0c12073ca5e" />

Before=network.target — правила применяются до старта сети, Type=oneshot — сервис выполняется один раз, 
iptables-restore — загружает правила из файла, RemainAfterExit=yes — systemd считает сервис активным после выполнения,
WantedBy=multi-user.target - Сервис будет запускаться при старте системы.

<img width="563" height="254" alt="image" src="https://github.com/user-attachments/assets/98918a7f-d131-4798-bd34-4e79bdd19060" />

Затем активировал сервис и проверил
