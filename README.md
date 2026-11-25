# Лабораторная работа №3 · Подзапросы, пользовательские типы и CASE

Журнал книжных рекомендаций · Валеев А.А.

## Что понадобится

- Python 3.12 или новее с Tkinter. Проверить установку можно командой `python -m tkinter` или `python3 -m tkinter`. В Linux Tkinter может устанавливаться отдельно, например пакетом `python3-tk`.
- Запущенный PostgreSQL 13+ и учётная запись PostgreSQL с правом создавать схемы в выбранной базе.
- Все файлы репозитория. Скачайте его через **Code → Download ZIP** или клонируйте, затем откройте папку с `main.py` в терминале.

## Запуск

**macOS и Linux**

```sh
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python main.py
```

**Windows PowerShell**

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe main.py
```

Если на Windows установлена более новая версия Python, укажите её в первой команде.

## Подключение к PostgreSQL

1. В окне приложения нажмите **Подключение**. Для локального PostgreSQL обычно используются сервер `localhost` и порт `5432`.
2. Укажите имя базы данных, роль PostgreSQL и её пароль, если он требуется. Нажмите **Подключиться**.
3. На вкладке **Данные** нажмите **Создать схему**, затем **Загрузить демоданные**.

Работа использует схему `valeev_books_3`.

## Быстрая проверка

1. Откройте **Выражения → Вложенный SELECT**. Выберите `engines` снаружи и `benchmarks` внутри.
2. Выберите `EXISTS`, укажите `engine_id` для обоих ключей корреляции и задайте внутренний фильтр `hit_rate >= 0.8`.
3. Нажмите **Проверить**. В результате будут `ReaderCircle` и `BookBlend`.
4. Для проверки `COALESCE` откройте **Обработка NULL**, выберите `benchmarks.remark` и подставьте текст «Без заметки».
