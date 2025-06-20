# Проект: Классификация пользовательских запросов

## Описание проекта

Проект посвящен задаче классификации пользовательских поисковых запросов с сайта 21vek.by по соответствующим категориям товаров. Цель — построить модель, которая сможет точно определять категорию товара на основе текста запроса.

## Данные

Для решения задачи предоставлены следующие файлы:

* `train.csv` – Обучающая выборка, содержащая пользовательские запросы (`Query`) и соответствующие им идентификаторы категорий товаров (`CategoryID`).
* `test.csv` – Тестовая выборка, содержащая только идентификаторы строк (`ID`) и запросы (`Query`). Используется для финального предсказания без указания правильных категорий.
* `sample_submission.csv` – Пример файла для отправки результатов предсказания, демонстрирующий требуемый формат (`ID`, `CategoryID`).
* `categories.csv` – Справочник, содержащий соответствие между идентификаторами категорий (`CategoryID`) и их текстовыми названиями (`CategoryName`).

## Столбцы данных

* `ID` – Уникальный идентификатор строки запроса.
* `Query` – Текст поискового запроса пользователя.
* `CategoryID` – Идентификатор категории товара (целевая переменная, присутствует только в `train.csv`).
* `CategoryName` – Текстовое название категории (присутствует только в `categories.csv`).

## Задача

Основная задача — разработать модель машинного обучения, которая по тексту запроса (`Query`) из тестовой выборки предскажет соответствующий `CategoryID`. Это задача многоклассовой классификации текста.

## Методология

1.  **Разведочный анализ данных (EDA):** Проведен подробный анализ обучающей и тестовой выборок для понимания структуры данных, распределения категорий, особенностей текстовых запросов, выявления пропусков и аномалий.
2.  **Подготовка данных:** (Была проведена предобработка текста: токенизация, лемматизация, удаление стоп-слов и т.д., а также векторизация текста).
3.  **Подбор модели:** Были рассмотрены и оценены различные модели машинного обучения для задачи классификации.
4.  **Финальная модель:** По результатам тестирования и оценки, наилучший показатель на тестовых данных показала модель **Логистической регрессии**.

## Метрика оценки

Качество предсказаний оценивалось с использованием метрики **Macro F1-score**.

## Результаты

Использование модели Логистической регрессии позволило достичь следующего результата на тестовых данных (согласно оценке на платформе Kaggle):

**Macro F1-score: 0.84188**
