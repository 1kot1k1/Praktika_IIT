# 🛥️ Azure Yachts — Full-Stack Yacht Management System

![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=.net&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91.svg?style=for-the-badge&logo=visual-studio&logoColor=white)

**Azure Yachts** — это современная веб-платформа для управления флотом элитных яхт. Проект представляет собой полноценное Full-Stack приложение, объединяющее элегантный фронтенд и мощную серверную часть на базе ASP.NET Core.

---

## 🛠 Технологический стек

| Слой | Технологии |
| :--- | :--- |
| **Backend** | C# / ASP.NET Core 8.0 |
| **Database** | Entity Framework Core / SQLite |
| **Frontend** | HTML5, CSS3 (Grid & Flexbox), Vanilla JavaScript |
| **Tools** | Visual Studio 2022, Dev Tunnels |

---

## 🗄️ Логика Базы Данных (Data Layer)

В проекте реализован подход **Code-First** через Entity Framework Core. Вам не нужно писать SQL-запросы вручную — вся структура данных описывается C#-классами.

### Архитектура данных:
1. **Models** — Обычные классы (POCO), которые EF Core превращает в таблицы.
2. **AppDbContext** — "Сердце" системы, которое связывает C# и SQLite.
3. **Relationships** — Реализованы связи «Один ко многим» (например, одна Яхта может иметь много Бронирований).

### Пример маппинга данных:
| C# Property | SQL Type | Роль |
| :--- | :--- | :--- |
| `int Id` | INTEGER | Primary Key (Auto-increment) |
| `string Name` | TEXT | Название яхты |
| `decimal Price` | REAL | Стоимость аренды |
| `Yacht Yacht` | Foreign Key | Навигационное свойство (связь) |

---

## 🚀 Ключевые возможности

*   ✅ **Динамический контент:** Все яхты в каталоге подгружаются из базы данных.
*   ✅ **Интерактивный UI:** Плавные слайдеры и всплывающие окна с характеристиками.
*   ✅ **Dev Tunnels:** Возможность запуска проекта через облачный туннель для демонстрации по публичной ссылке прямо из Visual Studio.
*   ✅ **CRUD операции:** Поддержка создания, чтения, обновления и удаления записей в БД.

---

## 💻 Как запустить проект

1. Откройте решение в **Visual Studio 2022**.
2. Проверьте наличие базы данных `azureyachts.db`. Если её нет, примените миграции:
   ```bash
   dotnet ef database update
