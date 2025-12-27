# Отчет по лабраторной работе на тему "Автоматизация сборки и деплоя Python Docker-приложений через Jenkins с интеграцией GitHub"
Введение
Цель данной лабораторной работы — освоить практические навыки работы с Ansible, инструментом для автоматизации конфигурации и управления инфраструктурой. В рамках работы предстояло настроить управляющую машину с Ansible, развернуть управляемый хост в Docker-контейнере, настроить SSH-подключение без пароля, создать инвентарный файл и выполнить

Ход работы
# 1.1 Обновление пакетов системы

<img width="320" height="98" alt="image" src="https://github.com/user-attachments/assets/c0e68428-7c14-44aa-bac8-70da139c1e3e" />
<img width="399" height="115" alt="image" src="https://github.com/user-attachments/assets/9c1a225b-7081-477e-8814-d564e3e450a3" />

# 1.2 Установка Python и pip

<img width="646" height="62" alt="image" src="https://github.com/user-attachments/assets/8ceb7903-9328-433b-af34-1ced278c48af" />

# 1.3 Установка Ansible через apt

<img width="461" height="91" alt="image" src="https://github.com/user-attachments/assets/4ab25ba5-582b-440c-b028-d300bbc1944d" />

# 1.4 Проверка установки Ansible

<img width="929" height="169" alt="image" src="https://github.com/user-attachments/assets/b4ebfffa-1d5c-4a82-8fcb-2a476591db34" />

# 2.1 Генерация SSH ключевой пары

<img width="647" height="318" alt="image" src="https://github.com/user-attachments/assets/8a9057a6-bed7-4da9-8b0f-ed8b3a220091" />

# 2.2 Установка прав доступа

<img width="478" height="59" alt="image" src="https://github.com/user-attachments/assets/f7be1ce3-2731-458c-9197-22f2ba0fe5f5" />

# Проверка создания ключей

<img width="614" height="51" alt="image" src="https://github.com/user-attachments/assets/4ba161be-a271-4bd9-a50c-c242fa955225" />

ШАГ 3: Запуск управляемого контейнера в Docker
Создаем рабочую директорию

<img width="350" height="62" alt="image" src="https://github.com/user-attachments/assets/769c5a7b-3354-4d25-ad4a-ef1c1f3194bc" />

Dockerfile:

<img width="776" height="550" alt="image" src="https://github.com/user-attachments/assets/fff1a313-ab21-4234-b699-dd1e4cdce091" />

docker-compose.yml:

<img width="594" height="408" alt="image" src="https://github.com/user-attachments/assets/61d20219-6d38-4648-8ebd-3ac7aa3b8b9a" />

Сборка и запуск контейнера:

# Сборка образа
# Запуск контейнера в фоновом режиме

<img width="507" height="91" alt="image" src="https://github.com/user-attachments/assets/4152e56c-a3d4-45a4-aab1-d71c20fa4ede" />

Проверка запущенного контейнера

<img width="965" height="119" alt="image" src="https://github.com/user-attachments/assets/0a245e3c-0b94-4fad-9e20-be1ba61ece42" />

Копирование публичного SSH ключа в контейнер
# Создаем директорию .ssh в контейнере

<img width="793" height="45" alt="image" src="https://github.com/user-attachments/assets/396bc5c8-cd66-4752-aa24-ccf8edb90759" />

# Копируем публичный ключ

<img width="702" height="53" alt="image" src="https://github.com/user-attachments/assets/6b27dcf6-10a4-46ad-ba9d-e8c7788f5195" />

# Устанавливаем правильные права доступа

<img width="921" height="52" alt="image" src="https://github.com/user-attachments/assets/554771e1-3847-4681-a0ce-691199ecfc20" />

ШАГ 4: Проверка SSH подключения к контейнеру
# 4.1 Проверка SSH подключения

<img width="722" height="91" alt="image" src="https://github.com/user-attachments/assets/db4406b6-3c1d-48f6-938e-cbe3eda3b597" />
<img width="720" height="297" alt="image" src="https://github.com/user-attachments/assets/e288d02a-f97d-4b3b-80a2-2d6de530d8dd" />
<img width="254" height="37" alt="image" src="https://github.com/user-attachments/assets/bc456932-4495-40b3-a8e9-54358c811f95" />

Выходим из контейнера

<img width="258" height="51" alt="image" src="https://github.com/user-attachments/assets/de31d935-0c12-4f0d-8657-0b95aea6e34d" />

ШАГ 5: Создание инвентарного файла Ansible
inventory.ini:

<img width="958" height="233" alt="image" src="https://github.com/user-attachments/assets/4057b5df-89f4-4e1f-a69b-6b2c319ec8e9" />

Проверка инвентаря:

<img width="649" height="438" alt="image" src="https://github.com/user-attachments/assets/27a1edf0-fc25-4fd3-bc3b-55f37b89affe" />

Проверка подключения Ansible к управляемому хосту
Тест ping:

<img width="675" height="87" alt="image" src="https://github.com/user-attachments/assets/e99f99e3-0250-43db-bd74-4be4a020cfe6" />

Сбор информации о системе:

<img width="641" height="182" alt="image" src="https://github.com/user-attachments/assets/7a6eaa4d-7780-480a-8436-81cda1454a6f" />

Выполнение простой команды:

<img width="944" height="67" alt="image" src="https://github.com/user-attachments/assets/66c3f884-3137-4acc-9861-76d53e63a21e" />

Создание и запуск Ansible Playbook
playbook.yml

<img width="527" height="129" alt="image" src="https://github.com/user-attachments/assets/cd8903ec-45d8-436d-ad01-f76c4edfda1b" />

Запуск playbook:

<img width="1280" height="274" alt="image" src="https://github.com/user-attachments/assets/e90d7890-1a1b-4f05-8185-6c96532577f4" />
<img width="729" height="78" alt="image" src="https://github.com/user-attachments/assets/3a6ef19b-bd36-4da5-b510-1fc9d0b708a5" />

Выполнение заданий для самостоятельной работы
Задание 1: Базовое подключение (уже выполнено)
Ansible установлен
SSH ключи сгенерированы
Инвентарный файл создан
Ping работает
Задание 2: Базовые ad-hoc команды
# 1. Информация о ядрах CPU

<img width="927" height="120" alt="image" src="https://github.com/user-attachments/assets/bf86ba18-2977-4ffa-9642-15286575cca1" />

# 2. Свободное место на диске

<img width="741" height="167" alt="image" src="https://github.com/user-attachments/assets/9e1ee3af-7c4d-4f5c-ac2c-028f59c663a7" />

# 3. Список всех пользователей

<img width="800" height="421" alt="image" src="https://github.com/user-attachments/assets/c85fc8f4-f8d8-40c9-a7fe-64d1110e2052" />

# 4. Изменение временной зоны хоста на UTC (с использованием sudo)

<img width="937" height="56" alt="image" src="https://github.com/user-attachments/assets/2c9ed148-6485-4fc6-9cae-434487247032" />

Задание 3: Работа с файлами
task3_files.yml:

<img width="561" height="634" alt="image" src="https://github.com/user-attachments/assets/d901761b-f845-4585-829a-2fa79bd2a852" />

Запуск playbook:

<img width="1280" height="495" alt="image" src="https://github.com/user-attachments/assets/9f5bdf41-43dd-4c2e-be56-aaba28b1f1ef" />
<img width="615" height="44" alt="image" src="https://github.com/user-attachments/assets/bdc8cba4-5a96-4647-bb11-46470f3c52ac" />

Проверка результатов:

<img width="859" height="85" alt="image" src="https://github.com/user-attachments/assets/28c4a006-5221-4754-ba7f-6aec7ab1a27e" />
<img width="942" height="82" alt="image" src="https://github.com/user-attachments/assets/12cdcc67-4445-4d3e-94c5-1c9f081ef30c" />
