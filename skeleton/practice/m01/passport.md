# Паспорт проекта

## 1. Общие сведения

| | |
|---|---|
| Название | TODO |
| Назначение (1–2 предложения) | TODO |
| Исходный репозиторий | TODO ссылка |
| Мой форк | TODO ссылка |
| Лицензия | TODO (файл LICENSE или «нет») |
| Тип | TODO веб / мобильное / десктоп + API |

## 2. Стек

| Слой | Технология | Версия |
|---|---|---|
| Клиент | TODO | |
| Сервер | TODO | |
| База данных | TODO | |
| Сборка / пакеты | TODO | |

Объём кода (вставьте вывод `python tools/metrics.py <путь>` или `cloc .`):

```
TODO
```

## 3. Структура каталогов

| Папка / файл | Назначение |
| --- | --- |
| `config/` | Конфигурационные файлы проекта, содержит `config.php`. |
| `database/` | SQL-файлы базы данных: `schema.sql`, `seed.sql`. |
| `public/` | Публичная часть приложения: `index.php`, `api.php`, папки `assets/`, `uploads/`. |
| `src/` | Основная бизнес-логика: классы авторизации, работы с БД, книгами, пользователями, бронированием и отчётами. |
| `templates/` | PHP-шаблоны страниц: каталог, профиль, регистрация, авторизация, административная панель и интерфейс библиотекаря. |
| `.env.example` | Пример настроек окружения. |
| `.gitignore` | Список исключений для Git. |
| `LICENSE` | Лицензия проекта. |
| `README.md` | Описание проекта и инструкция по запуску. |

## 4. Зависимости

Основные зависимости (не более 15 самых важных):

| Пакет | Версия | Зачем нужен |
|---|---|---|
| TODO | | |

## 5. История репозитория

Вставьте вывод `python tools/repo_stats.py <путь>` и прокомментируйте.

- Коммитов: TODO, период: TODO
- Авторов: TODO
- Ветки и теги: TODO
- Самые часто изменяемые файлы и почему: TODO
- Что показал `git blame` по файлу `TODO`: TODO

## 6. Запуск

Шаги, которые реально сработали у вас (с командами):

```
Установите XAMPP. Скачайте версию для Windows с apachefriends.org и установите в папку по умолчанию C:\xampp
Откройте XAMPP Control Panel и нажмите Start у Apache и MySQL. Обе строки должны стать зелёными. Если Windows спросит про брандмауэр, разрешайте доступ только для частных сетей
Должен существовать файл C:\xampp\htdocs\kait-library\public\index.php. Windows при распаковке часто добавляет лишнюю папку kait-library\kait-library, в этом случае перенесите содержимое на уровень выше
Откройте PowerShell и выполните команды по очереди. При успехе они ничего не выводят:
cd C:\xampp\htdocs\kait-library
C:\xampp\mysql\bin\mysql -u root -e "CREATE DATABASE kait_library CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci"
C:\xampp\mysql\bin\mysql -u root --default-character-set=utf8mb4 kait_library -e "source database/schema.sql"
C:\xampp\mysql\bin\mysql -u root --default-character-set=utf8mb4 kait_library -e "source database/seed.sql"
Откройте сайт: http://localhost/kait-library/public/
В следующие разы достаточно нажать Start у Apache и MySQL и открыть тот же адрес
```

Проблемы при запуске и как решили:
```
Apache не стартует	-> Порт 80 занят другой программой, например IIS. Закройте её.
MySQL не стартует	-> Порт 3306 занят другим MySQL. На этом ПК так и будет из-за службы MySQL80, её надо остановить.
Ошибка про VCRUNTIME140.dll	-> Выполните winget install Microsoft.VCRedist.2015+.x64
could not find driver	-> В C:\xampp\php\php.ini уберите ; перед extension=pdo_mysql и перезапустите Apache.
Access denied for user 'root'	-> На MySQL стоит пароль. Скопируйте .env.example в .env и впишите пароль в DB_PASS.
Unknown database или нет таблиц	-> Шаг 4 не выполнен до конца.
Страница 404	-> В htdocs лишняя вложенная папка
```

## 7. Вывод о проекте

Насколько проект зрелый, что бросилось в глаза, где вероятны проблемы: TODO
