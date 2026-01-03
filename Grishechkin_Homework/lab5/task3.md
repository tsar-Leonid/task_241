**1. Посмотретите журналы ssh**

<img width="737" height="628" alt="image" src="https://github.com/user-attachments/assets/3c806815-ad43-4739-99c9-4d48eede0190" />

journalctl — утилита для просмотра логов systemd, -u sshd — фильтр по юниту sshd

**2. Выведите журналы в реальном времени**

<img width="900" height="217" alt="image" src="https://github.com/user-attachments/assets/83a0ece8-45e8-48ca-b8aa-4227e12c70e7" />

журнал обновляется в реальном времени, новые события появляются сразу, как только они происходят

**3. Выведите лог в реальном времени для службы sshd**

<img width="777" height="115" alt="image" src="https://github.com/user-attachments/assets/09653de6-6dff-4074-b07f-20a680772ff2" />

показывает только логи sshd, сразу выводит новые записи (например, когда кто-то подключается по SSH)

**4. Можно ли без комады journalctl прочитать логи systemd?**

Да, читать логи systemd без journalctl возможно, например через systemctl status, dmesg или текстовые логи при наличии rsyslog.
Однако эти способы дают ограниченную информацию и неудобны. Для полноценной работы с журналами systemd рекомендуется использовать journalctl.

<img width="960" height="648" alt="image" src="https://github.com/user-attachments/assets/78484ca7-6dbb-44c4-bfec-cef36d33fa03" />

**5. Сколько будет 2-2?**

<img width="313" height="46" alt="image" src="https://github.com/user-attachments/assets/f4e37737-683c-4114-af82-28d2c27c8125" />
