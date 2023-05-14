# План автоматизации тестирования сценария перехода к форме записи на обучение профессии "Тестировщик ПО" и ее заполнения

## Перечень автоматизируемых сценариев
1. Проверка переходов к форме для записи:

    - открыть [страницу Нетологии](https://netology.ru/) -> в заголовке слева, кликнуть кнопку "Каталог курсов" -> выбрать раздел "Программирования" -> в открывшемся [разделе](https://netology.ru/development) выбрать "Тестировщик ПО" -> на открывщейся [странице](https://netology.ru/programs/qa?recommended_by=instant_search) кликнуть кнопку "Записаться", которая переносит в конец страницы к форме для записи;

    - открыть [страницу Нетологии](https://netology.ru/) -> в заголовке слева, кликнуть кнопку "Каталог курсов" -> в поле для ввода нести "Тестировщик" -> из выпадающего списка выбрать "Тестеровщик ПО" -> на открывщейся [странице](https://netology.ru/programs/qa?recommended_by=instant_search) пролистать вниз страницы к форме для записи;

    - открыть [страницу Нетологии](https://netology.ru/) -> пролистать до раздела "Направления обучения" -> выбрать раздел "Программирования" -> в открывшемся [разделе](https://netology.ru/development) выбрать "Тестировщик ПО" -> на открывщейся [странице](https://netology.ru/programs/qa?recommended_by=instant_search) кликнуть кнопку "Записаться", которая переносит в конец страницы к форме для записи;

    - открыть [страницу Нетологии](https://netology.ru/) -> пролистать до раздела "Направления обучения" -> нажать на кнопку "Полный каталог" -> на открывшейся [странице](https://netology.ru/navigation) выбрать "Тестировщик ПО" -> на открывщейся [странице](https://netology.ru/programs/qa?recommended_by=instant_search) пролистать вниз страницы к форме для записи;

2. Проверка полей формы для записи

Для составления тестов используем документацию с требованиями валидности полей. Если требований нет, использовать стандартные:

    **Поле Имя** - разрешены только буквы (латиница и кириллица), дефисы и пробелы, минимум два символа;

    **Поле Телефон** - только цифры (11 цифр), допустим символ + (на первом месте);

3. Проверка отправки формы для записи через кнопку "Записаться"

    - Отправка формы с валидными значениями.

        Результат: Данные успешно отправлены и могут быть просмотрены в базе данных. Появится всплывающее окно об успешном завершении записи.


    - Отправка формы с невалидными значениями

        Результат: Данные не отправляются, нет записи в БД. Появится сообщение об ошибке(ах).

    - Отправка формы с пустыми значениями.

        Результат: Данные не отправляются, нет записи в БД. Появится сообщение об необходимости заполнить поле(я).

    



## Перечень используемых инструментов с обоснованием выбора
- JDK (актуальной версии, к примеру 11), в проекте планируется использование Java, поэтому устанавливаем этот набор программ и библиотек;
- IntelliJ IDEA, среда для написания кода автотестов;
- Gradle, система автоматической сборки;
- GIT и Github, используем для работы с логальным и удаленным хранилищем;
- Docker, для развертывания SUT, 
- DBeaver, используем для просмотра базы данных;
- MySQL и PostgreSQL, для доступа к базе данных из кода автотестов.

Для написания кода автотестов, повышения его читаемости и подготовки отчетов:
- JUnit Jupiter;
- SQL, язык для управления базами данных;
- Lombok, предлагает различные аннотации, цель которых – заменить ненужный повторяющийся код;
- Faker, для генерации данных;
- Selenide, удобен при написании автотестов веб-интерфейсов;
- Allure, для создания отчетов о выполнении автотестов;
- Allure-Selenide, для интеграции одного инструмента с другим.

## Перечень необходимых разрешений, данных и доступов
- Письменное задание или разрешение на тестирование [веб-сайта Нетологии](https://netology.ru);
- Документация с требованиями к полям формы для записи;
- Подготовлен и предоставлен SUT с данными для развертывания,
- База данных (подготовленная или пустая). 

## Перечень и описание возможных рисков при автоматизаци
- Автоматизация не исключает ручную проверку, т.к. не отслеживает визуальную часть: цвета, верстку и др.
- Нет тестовых меток, поэтому даже не значительное изменение веб-элементов может привести к падению автотестов.

## Перечень необходимых специалистов для автоматизации
- Разработчик, который подготовит и предоставит SUT и БД.
- Тестировщик ПО.

## Интервальная оценка с учётом рисков в часах
- Ориентировочно потребуется 32 рабочих часа. Без учета времени на подготовку SUT и Базы данных.
