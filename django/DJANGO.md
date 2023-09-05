# Руководство по установке, настройке и работе с Git
Добро пожаловать в руководство по python фреймворку Django! Этот документ поможет вам начать использовать Django, включая настройку и базовые команды. Независимо от вашего уровня опыта, здесь вы найдете полезную информацию.
## Содержание
1. **<u>Установка Django</u>**
1. **<u>Начало раты с Django</u>**
   - **<u>Создание репозитория</u>**
## Установка Django
   - Откройте командную строку (Bash, Shell ...) и установку командой: 
```sh
pip install django
```
   - Проверьте установку командой: 
```sh
django-admin --version
```
## Начало раты с Django
### Создание проекта
   - Создайте новую папку, в которой хранятся ваши проекты, либо в папку, где вы хотите создать проект Django.
   - Инициализируйте Django: 
```sh
django-admin startproject project_name
```
   - Перейдите в папку с проектом: 
```sh
cd project_name
```
### Создание проекта
   - Запустите начальный проект Django командой:
```sh
python manage.py runserver
```
   - Создайте приложение внутри текущего проекта командой:
```sh
python manage.py startapp app_name
```
   - Создайте подключение к базе дынных (в примере Postgres), изменив значение DATABASES в файле ./project_name/setting.py:
```py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'todo_app_django',
        'USER': 'postgres',
        'PASSWORD': 'admin',
        'HOST': 'localhost',
        'PORT': '5432'
    }
}
```
   - Создайте модели данных будующей или существующей базы дынных в файле ./app_name/models.py:
```py
class Users(models.Model):
    id = models.BigAutoField(primary_key=True)
    login = models.TextField()
    password = models.TextField()

    class Meta:
        db_table = 'users'
```
   - Выполните миграцию базы данных используя команды:
```sh
python manage.py makemigrations
```
```sh
python manage.py migrate
```
## Заключение
Поздравляем! Теперь у вас есть основные знания о Django. Django - фреймворк для создания и управления RESTful API. Продолжайте практиковаться и углублять свои знания, и вы сможете эффективно использовать Django в своих проектах. Если у вас возникнут вопросы, не стесняйтесь обращаться к [официальной документации Django](https://django.fun/ru/docs/django/4.1/) или сообществам разработчиков.