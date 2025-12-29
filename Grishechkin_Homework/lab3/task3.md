**1.Выведите содержимое fstab. Что хранится в fstab?**

/etc/fstab — это файл конфигурации, в котором хранится информация о дисках и точках монтирования, которые система подключает при загрузке.

<img width="890" height="133" alt="image" src="https://github.com/user-attachments/assets/eb2f7a65-e170-4029-a127-711917aaecd4" />

**2.Добавьте в виртуальную машину ещё один диск**

В UTM изменить, диск и создал новый

<img width="331" height="154" alt="image" src="https://github.com/user-attachments/assets/2ca009f8-7bf7-466c-a672-2f87b9b240b0" />

**3.Узнайте как ситема видит ваш диск - выведите информацию о блочных устройствах**

Для вывода информации о дисках использовал lsblk

<img width="433" height="146" alt="image" src="https://github.com/user-attachments/assets/6421f0b0-7508-4a1d-a8b2-93f22c1d5fee" />

Добавился новый

**4.С помощью полученной информации создайте на диске таблицу разделов и фаловую систему ext4**

Сначала создаю таблицу разделов gpt(GUID Partition Table) - современный стандарт таблицы разделов для дисков. Создаю один раздел на весь диск и после создаю файловую систему ext4, чтобы диск можно было монтировать

<img width="790" height="542" alt="image" src="https://github.com/user-attachments/assets/a3e90566-b217-4eea-9fba-f4510fbe0d10" />

**5.Примонитруте диск в каталог /mnt**

<img width="659" height="135" alt="image" src="https://github.com/user-attachments/assets/b81a3b95-65db-4e7c-a768-58eb69f2a233" />

**6.Зайдите в каталог и создайте там файлы**

<img width="394" height="79" alt="image" src="https://github.com/user-attachments/assets/cc38bd6a-c1d9-4191-95cf-9f01546699a9" />

**7.Отмонтируйте диск и проверье остались ли файлы**

Отмонтирую с помощью umount, затем снова примонтирую и проверю файлы

<img width="483" height="93" alt="image" src="https://github.com/user-attachments/assets/15257602-6cb1-49ee-8e5d-0cbfd8f74fa6" />

Файлы остались, тк диск теперь храниит данные на разделе

**8.Сделайте так чтобы диск автоматически подключался при загрузке систем ( добавьте информацию о нём с fstab). 9.Проверьте корретность записанных в fstab данных перед перезагрузкой**

Сначала узнаю UUID раздела с помощью blkid и добавлю его в fstab

<img width="904" height="187" alt="image" src="https://github.com/user-attachments/assets/c18cebb6-1993-4b8b-acb7-44a61ce5ac79" />

с помошью **mount -a** проверил ошибки в /etc/fstab - если ничего не вывелось, значит ошибок нет

**10.Перезагрущите систему и убедитесь что диск был подключён к системе**

<img width="643" height="150" alt="image" src="https://github.com/user-attachments/assets/d9967369-f998-4617-990a-9cfc2b622b4c" />



