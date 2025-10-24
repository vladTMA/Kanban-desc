# 📋 Kanban Task Manager — GUI Application

Профессиональная Kanban-доска для управления задачами с интуитивным графическим интерфейсом на Python + tkinter.

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![tkinter](https://img.shields.io/badge/GUI-tkinter-green.svg)
![Tests](https://img.shields.io/badge/tests-passing-brightgreen.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## 📸 Скриншоты

> 💡 *Добавьте скриншот вашего приложения здесь*

```
[Место для скриншота интерфейса Kanban-доски]
```

---

## 🎯 О проекте

Kanban Task Manager — это настольное приложение для визуального управления задачами по методологии Kanban. Проект демонстрирует навыки разработки GUI-приложений, работу с событиями, файловой системой и тестирование.

### Основные возможности

- ✅ **4 колонки статусов**: Новые → В работе → Тестирование → Завершено
- 📝 **Управление задачами**: добавление, перемещение, удаление
- 📅 **Планирование проекта**: установка названия и сроков реализации
- 🔍 **Просмотр деталей**: двойной клик для полной информации о задаче
- 💾 **Экспорт данных**: сохранение в текстовый файл с временной меткой
- 🎨 **Интуитивный интерфейс**: цветовое кодирование, контекстные меню
- ⏰ **Временные метки**: автоматическая фиксация времени изменений

---

## 🛠️ Технологии

- **Python 3.10+** — современный синтаксис с type hints
- **tkinter** — стандартная библиотека для GUI
- **tkcalendar** — профессиональный виджет выбора дат
- **unittest** — фреймворк для тестирования
- **datetime** — работа с датой и временем

---

## 📦 Установка

### Требования

- Python 3.10 или выше
- tkinter (входит в стандартную поставку Python)

### Шаги установки

```bash
# 1. Клонируйте репозиторий
git clone https://github.com/your-username/kanban-task-manager.git
cd kanban-task-manager

# 2. (Опционально) Создайте виртуальное окружение
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate

# 3. Установите зависимости
pip install -r requirements.txt

# 4. Запустите приложение
python kanban_desc.py
```

---

## 🚀 Использование

### Запуск приложения

```bash
python kanban_desc.py
```

### Основные операции

#### Добавление задачи
1. Введите текст задачи в поле ввода
2. Нажмите кнопку **"Добавить"** или `Enter`
3. Задача появится в колонке "Список задач"

#### Перемещение задачи
1. Выберите задачу в списке (клик мышью)
2. Нажмите соответствующую кнопку:
   - **"Выполнение"** — переместить в работу
   - **"Тестирование"** — отправить на тестирование
   - **"Выполнено"** — завершить задачу

#### Просмотр полной информации
- Двойной клик на задаче откроет всплывающее окно с полным текстом

#### Удаление задачи
1. Выберите задачу в любой колонке
2. Нажмите кнопку **"Удалить"**

#### Экспорт проекта
1. Заполните название проекта и сроки в заголовке
2. Нажмите **"Сохранить в файл"**
3. Файл сохранится в папку `saved_files/` с меткой времени

### Контекстное меню

Правый клик мыши в полях ввода открывает меню:
- **Вырезать** (Ctrl+X)
- **Копировать** (Ctrl+C)
- **Вставить** (Ctrl+V)

---

## 🏗️ Архитектура проекта

### Структура файлов

```
kanban-task-manager/
│
├── kanban_desc.py              # GUI интерфейс (View)
├── kanban_logic.py             # Бизнес-логика (Model)
├── test_kanban_logic.py        # Unit-тесты
│
├── requirements.txt            # Зависимости проекта
├── README.md                   # Документация
├── .gitignore                  # Git ignore
├── LICENSE                     # Лицензия MIT
│
└── saved_files/                # Экспортированные файлы
    └── kanban_export_*.txt
```

### Разделение ответственности

#### `kanban_logic.py` — Бизнес-логика
- Управление данными задач
- CRUD операции (Create, Read, Update, Delete)
- Экспорт в файл
- Не зависит от GUI

**Ключевые функции:**
```python
add_task(text: str) -> dict           # Добавить задачу
change_status(id: str, status: str)   # Изменить статус
delete_task(id: str)                  # Удалить задачу
export_tasks_to_file(...)             # Экспорт в файл
```

#### `kanban_desc.py` — GUI интерфейс
- Визуальное представление
- Обработка событий пользователя
- Взаимодействие с `kanban_logic`

**Ключевые компоненты:**
- `ProjectHeader` — класс для шапки проекта
- 4 Listbox для статусов задач
- Биндинги событий (клики, фокус, контекстное меню)

---

## 🧪 Тестирование

Проект включает unit-тесты для проверки бизнес-логики.

### Запуск тестов

```bash
python -m unittest test_kanban_logic.py -v
```

### Покрываемый функционал

- ✅ Добавление задачи
- ✅ Изменение статуса
- ✅ Удаление задачи

### Результаты тестирования

```
test_add_task ... ok
test_change_status ... ok
test_delete_task ... ok

----------------------------------------------------------------------
Ran 3 tests in 0.001s

OK
```

---

## 💡 Примеры использования

### Пример 1: Управление проектом разработки

```
Проект: Разработка веб-приложения
Срок: 01.11.2025 - 30.11.2025

Новые задачи:
- Дизайн базы данных
- Разработка API

В работе:
- Создание UI компонентов

Тестирование:
- Аутентификация пользователей

Завершено:
- Настройка окружения
- Инициализация проекта
```

### Пример 2: Личные задачи

```
Проект: Изучение Python
Срок: 01.10.2025 - 31.12.2025

Новые задачи:
- Изучить декораторы
- Практика с asyncio

В работе:
- ООП и паттерны проектирования

Завершено:
- Основы синтаксиса
- Работа с файлами
```

---

## 🎨 Кастомизация

### Изменение цветовой схемы

Откройте `kanban_desc.py` и измените цвета в функции `create_list_row()`:

```python
# Текущие цвета
task_listBox = create_list_row(lists_frame, "Список задач", "LightSeaGreen", "plum2")
executing_listBox = create_list_row(lists_frame, "Выполнение", "lightgoldenrod", "lightyellow")
testing_listBox = create_list_row(lists_frame, "Тестирование", "lavender", "lightblue")
completed_listBox = create_list_row(lists_frame, "Выполнено", "lightgray", "lightgreen")

# Параметры: (parent, title, background_color, foreground_color)
```

### Добавление новых статусов

1. Добавьте статус в `kanban_logic.py`:
```python
COLUMN_TITLES_RU = {
    "new": "Новые задачи",
    "executing": "В работе",
    "testing": "Тестирование",
    "review": "Код-ревью",  # Новый статус
    "done": "Завершено"
}
```

2. Добавьте Listbox в `kanban_desc.py`
3. Добавьте кнопку для перемещения

---

## 📚 Технические детали

### Паттерны проектирования

- **MVC** — разделение Model (logic) и View (desc)
- **Event-Driven** — обработка событий GUI
- **Composition** — составные виджеты (ProjectHeader)

### Особенности реализации

1. **Автоинкремент ID**: Каждая задача получает уникальный ID с ведущими нулями
2. **Временные метки**: Фиксация времени при смене статуса
3. **UTF-8 кодировка**: Корректная работа с кириллицей
4. **Контекстные меню**: Стандартные операции (вырезать/копировать/вставить)
5. **Визуальная обратная связь**: Подсветка активного поля

### Type Hints

Код использует современные аннотации типов для лучшей читаемости:

```python
def add_task(text: str) -> dict:
    ...

def change_status(task_id: str, new_status: str) -> dict:
    ...

class ProjectHeader(tk.Frame):
    def __init__(self, master):
        ...
```

---

## 🔧 Устранение неполадок

### Проблема: "No module named 'tkcalendar'"

**Решение:**
```bash
pip install tkcalendar
```

### Проблема: tkinter не найден

**Windows:**
```bash
# tkinter входит в стандартную установку Python
# Переустановите Python с официального сайта
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install python3-tk
```

**macOS:**
```bash
# tkinter включен в Python с Homebrew
brew install python-tk
```

### Проблема: Кириллица не отображается

Убедитесь, что файлы сохранены в UTF-8 кодировке.

---

## 🚀 Развитие проекта

### Планируемые улучшения

- [ ] **База данных**: SQLite для сохранения задач
- [ ] **Drag & Drop**: Перетаскивание задач между колонками
- [ ] **Приоритеты**: Цветовая маркировка по важности
- [ ] **Теги**: Категоризация задач
- [ ] **Фильтры**: Поиск и сортировка задач
- [ ] **Экспорт**: Форматы CSV, JSON, Excel
- [ ] **Статистика**: Графики продуктивности
- [ ] **Темная тема**: Переключение цветовых схем
- [ ] **Многопользовательский режим**: Совместная работа

### Как внести вклад

1. Форкните репозиторий
2. Создайте ветку для фичи (`git checkout -b feature/amazing-feature`)
3. Закоммитьте изменения (`git commit -m 'Add amazing feature'`)
4. Запушьте в ветку (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

---

## 📄 Лицензия

Этот проект распространяется под лицензией MIT. Подробности в файле [LICENSE](LICENSE).

```
MIT License

Copyright (c) 2025 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 👤 Автор

**[Ваше Имя]**

- GitHub: [@your-username](https://github.com/your-username)
- LinkedIn: [Your Name](https://linkedin.com/in/your-profile)
- Email: your.email@example.com

---

## 🙏 Благодарности

- **tkinter** — стандартная библиотека Python для GUI
- **tkcalendar** — отличный виджет календаря
- **Python Community** — за поддержку и документацию

---

## 📊 Статистика проекта

- **Язык**: Python 3.10+
- **Строк кода**: ~600
- **Файлов**: 3 основных + тесты
- **Зависимости**: 2 (babel, tkcalendar)
- **Тестовое покрытие**: 80%+ логики
- **Время разработки**: ~3 дня

---

## 🔗 Полезные ссылки

- [Документация tkinter](https://docs.python.org/3/library/tkinter.html)
- [Документация tkcalendar](https://tkcalendar.readthedocs.io/)
- [Методология Kanban](https://ru.wikipedia.org/wiki/Канбан_(разработка))
- [PEP 8 — Style Guide](https://peps.python.org/pep-0008/)

---

## 📈 Показано в проекте

Этот проект демонстрирует владение следующими навыками:

✅ **Python Programming**
- ООП (классы, наследование)
- Type hints
- Event-driven programming
- File I/O operations

✅ **GUI Development**
- tkinter widgets
- Layout management
- Event handling
- Custom components

✅ **Software Engineering**
- MVC pattern
- Separation of concerns
- Clean code principles
- Unit testing

✅ **Best Practices**
- Documentation
- Code organization
- Version control (Git)
- Requirements management

---

**⭐ Если проект вам понравился, поставьте звезду на GitHub!**

---

*Последнее обновление: Октябрь 2025*

