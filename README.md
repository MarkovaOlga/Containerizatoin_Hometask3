### Задание №3

#### Запуск контейнера с использованием образа "cowsay"
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc3001.jpg)

#### Некоторые команды

Просмотр списка образов

![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc302.jpg)

Просмотр списка запущенных контейнеров.
И просмотр списка всех контейнеров (включая остановленные).
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc303.jpg)

Удаление контейнера.

![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc304.jpg)

Удаление всех остановленных контейнеров.
И принудительное удаление всех контейнеров (включая запущенные)
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc305.jpg)

#### Хранение данных в контейнерах Docker

Для начала запустим контейнер из образа Ubuntu и войдем в него:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc306.jpg)

Посмотрим содержимое корневой директории:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc307.jpg)

Создадим новую директорию в корне:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc308.jpg)

Создаем файл внутри контейнера Ubuntu
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc309.jpg)

Остановим контейнер и затем запустим его снова
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc310.jpg)

Наши данные сохранятся, так как мы не пересоздавали контейнер.

Удалим контейнер и создадим его заново, используя те же команды:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc311.jpg)
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc312.jpg)
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc313.jpg)

В этот раз наши данные будут утеряны, так как контейнер был удален.

**Использование внешнего хранилища**

Создадим директорию и подмонтируем ее к контейнеру:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc314.jpg)
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc315.jpg)


Мы создали директорию и подмонтировали ее в контейнер, что позволило нам сохранить данные.

Добавим данные в подмонтированную директорию:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc316.jpg)

Проверим доступность данных с локальной системы:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc317.jpg)
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc318.jpg)

Удалим контейнер и создадим его снова, подмонтировав директорию:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc319.jpg)

Мы видим, что данные по-прежнему доступны.

#### Хранение данных в контейнерах Docker: Практическое руководство

Создаем папку, которую мы будем готовы смонтировать в контейнер.
В этой папке создаем файл test.txt и наполняем его данными:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc320.jpg)

Создаем контейнер из образа ubuntu:22.10 и задаем ему имя и hostname:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc321.jpg)

Монтируем созданный текстовый файл из домашней директории внутрь смонтированной папки в контейнере:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc322.jpg)

Смотрим содержимое текстового файла в контейнере:
![picture](https://github.com/MarkovaOlga/Containerizatoin_Hometask3/blob/main/pictures/sc323.jpg)

Объяснение:
Мы создали контейнер и монтировали папку docker-mount-example внутрь контейнера. 
Затем мы монтировали файл test.txt из домашней директории внутрь этой папки в контейнере. 
При просмотре содержимого файла в контейнере, вы увидите данные из файла в домашней директории.
