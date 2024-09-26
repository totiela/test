# 🎬 Чат-Бот для Поиска Фильмов

[![Запустить приложение](https://img.shields.io/badge/Streamlit-Запустить%20приложение-red?style=for-the-badge&logo=streamlit)](https://movie-search-chatbot-by-sanchezzz.streamlit.app/)

## 📜 Описание проекта

**Movie Search Chatbot** — это интерактивный чат-бот, предназначенный для поиска фильмов, анализа информации по актёрам и режиссёрам, а также рекомендаций похожих фильмов на основе вашего описания. Проект ориентирован на любителей кино, которые хотят найти фильм по ключевым словам, узнать больше о любимых актерах или режиссёрах, или получить интересную статистику, например, средние рейтинги фильмов с участием нескольких актёров.

### Целевая аудитория:
- **Киноэнтузиасты**, которым нужны персонализированные рекомендации на основе предпочтений.
- Пользователи, помнящие **сюжетные фрагменты**, имена актёров или режиссёра, но забывшие название фильма.
- Люди, которым нужна **сложная агрегация информации**, недоступная в публичных источниках, например, рейтинг фильмов, где снимались Леонардо Ди Каприо и Том Харди.

## 🚀 Ключевые возможности

1. **Поиск по описанию фильма:** Чат-бот может находить фильмы по ключевым словам или описанию, которые вы помните.
2. **Рекомендации похожих фильмов:** На основе введённого описания бот предложит фильмы, которые могут вам понравиться.
3. **Анализ сложных запросов:** Например, средний рейтинг фильмов, где играли несколько актёров вместе.
4. **Интерактивный чат с историей:** Вы можете взаимодействовать с ботом через диалог, сохраняя историю общения.
5. **Использование мощных языковых моделей:** Под капотом работает модель **gemma2-27b** от Google через API NVIDIA.

## 🛠 Особенности реализации

1. **Языковая модель:** Чат-бот использует модель **gemma2-27b**, которая обеспечивает глубокое понимание текста и контекста.
2. **История чата:** Поддерживается история запросов, что позволяет боту запоминать предыдущие вопросы.
3. **Два агента:** 
   - **SQL-агент** отвечает за сложные SQL-запросы к базе данных.
   - **Retriever-агент** находит фильмы на основе введённого описания, используя векторные и ключевые поисковые методы.
4. **Кастомный супер-агент:** Управляет агентами, ведёт диалог на русском языке и использует специальную память для учёта предыдущих запросов.

## 📚 Необходимые библиотеки и ресурсы

Для работы чат-бота требуются следующие библиотеки (указаны в `requirements.txt`):
- **LangChain** — основная библиотека для работы с агентами и ретриверами.
- **FAISS** — для векторного поиска похожих фильмов по ключевым словам.
- **SQLite** — база данных для хранения информации о фильмах.

## 🔧 Технические аспекты

1. **Парсинг данных:** Используется API и гет-запросы к iMDb для сбора данных более чем о 5000 фильмах.
2. **Базы данных:** Проект использует две базы данных:
   - **FAISS** для поиска по векторным представлениям фильмов на основе ключевых слов.
   - **SQLite** для структурированных запросов, таких как получение фильмов по жанру, актёрам и режиссёрам.
3. **Архитектура агента:** В проекте используется связка из двух агентов — SQL и Retriever, которые работают через кастомные промпты для улучшения производительности и вывода на русском языке.
4. **Память:** Реализована через **ConversationBufferMemory** для запоминания предыдущих взаимодействий с пользователем.

## 📦 Деплой

Чат-бот деплоирован на платформе **Streamlit**, что позволило быстро и легко создать доступную веб-страницу для взаимодействия с приложением.

Запуск MVP версии осуществляется [по этой ссылке](https://movie-search-chatbot-by-sanchezzz.streamlit.app/).

## 🔮 Планы на будущее

1. Улучшение обработки ошибок.
2. Расширение базы данных фильмов.
3. Добавление новых возможностей, таких как:
   - Поддержка Telegram-бота.
   - Увеличение числа агентов и улучшение их взаимодействия.
   - Оптимизация модели для ускорения работы.
