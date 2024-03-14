# Лабораторная работа 1
## Текст задания

Для выполнения лабораторной работы №1 необходимо:
1. На основе предложенной предметной области (текста) составить ее
описание. Из полученного описания выделить сущности, их
атрибуты и связи.
2. Составить инфологическую модель.
3. Составить даталогическую модель. При описании типов данных для
атрибутов должны использоваться типы из СУБД PostgreSQL.
4. Реализовать даталогическую модель в PostgreSQL. При описании и
реализации даталогической модели должны учитываться
ограничения целостности, которые характерны для полученной
предметной области.
5. Заполнить созданные таблицы тестовыми данными.
## Вариант 312471
### Описание предметной области, по которой должна быть построена доменная модель
```
На экране застыл образ Юпитера: клочья белых облаков, пятнистые
оранжево-розовые полосы и злобный глаз Большого Красного Пятна.
Лишь четверть диска скрывалась в тени; она-то и притягивала взгляды.
Там, в ночном небе планеты, китайский корабль летел навстречу своей
судьбе.
```
# Лабораторная работа 2
## Текст задания
Для отношений, полученных при построении предметной области из
лабораторной работы No1, выполните следующие действия: 
- Опишите функциональные зависимости для отношений полученной
схемы (минимальное множество); 
- Приведите отношения в 3NF (как минимум). Постройте схему на
основе 3NF (как минимум). Постройте схему на основе полученных
отношений; 
- Опишите изменения в функциональных зависимостях,
произошедшие после преобразования в 3NF (как минимум). Постройте
схему на основе 3NF;
- Преобразуйте отношения в BCNF. Докажите, что полученные
отношения представлены в BCNF;
- Какие денормализации будут полезны для вашей схемы? Приведите
подробное описание;
## Вариант 312471
### Описание предметной области, по которой должна быть построена доменная модель
```
На экране застыл образ Юпитера: клочья белых облаков, пятнистые
оранжево-розовые полосы и злобный глаз Большого Красного Пятна.
Лишь четверть диска скрывалась в тени; она-то и притягивала взгляды.
Там, в ночном небе планеты, китайский корабль летел навстречу своей
судьбе.
```
# Лабораторная работа 3
## Вариант 46712
### Текст задания

Составить запросы на языке SQL (пункты 1-7).
1. Сделать запрос для получения атрибутов из указанных таблиц, применив
фильтры по указанным условиям: \
Таблицы: `Н_ЛЮДИ`, `Н_ВЕДОМОСТИ`. \
Вывести атрибуты: `Н_ЛЮДИ.ИМЯ`, `Н_ВЕДОМОСТИ.ИД`.\
Фильтры (AND):\
a) `Н_ЛЮДИ.ИД` = `163484`.\
b) `Н_ВЕДОМОСТИ.ИД` = `1250981`. \
Вид соединения: `INNER JOIN`. 
2. Сделать запрос для получения атрибутов из указанных таблиц, применив
фильтры по указанным условиям: \
Таблицы: `Н_ЛЮДИ`, `Н_ВЕДОМОСТИ`, `Н_СЕССИЯ`. \
Вывести атрибуты: `Н_ЛЮДИ.ОТЧЕСТВО`, `Н_ВЕДОМОСТИ.ДАТА`,
`Н_СЕССИЯ.ЧЛВК_ИД`. \
Фильтры (AND): \
a) `Н_ЛЮДИ.ИМЯ` =` Александр`. \
b) `Н_ВЕДОМОСТИ.ДАТА` < `2010-06-18`. \
c) `Н_СЕССИЯ.ДАТА` = `2002-01-04`. \
Вид соединения: `LEFT JOIN`. 
3. Вывести число студентов КТИУ, которые без ИНН. \
Ответ должен содержать только одно число.
4. В таблице `Н_ГРУППЫ_ПЛАНОВ` найти номера планов, по которым обучается
(обучалось) ровно `2` групп на заочной форме обучения. \
Для реализации использовать подзапрос. 
5. Выведите таблицу со средними оценками студентов группы `4100` (Номер, ФИО,
Ср_оценка), у которых средняя оценка равна средней оценк(е|и) в группе `3100`. 
6. Получить список студентов, отчисленных после первого сентября 2012 года с
очной или заочной формы обучения (специальность: `230101`). В результат
включить: \
`номер группы`; \
`номер`, `фамилию`, `имя` и `отчество` студента; \
`номер пункта приказа`; \
Для реализации использовать подзапрос с `EXISTS`. 
7. Вывести список людей, не являющихся или не являвшихся студентами `СПбГУ
ИТМО` (данные, о которых отсутствуют в таблице `Н_УЧЕНИКИ`). В запросе
нельзя использовать `DISTINCT`.

# Лабораторная работа 4
## Вариант 3452
### Текст задания
Составить запросы на языке SQL (пункты 1-2). \
Для каждого запроса предложить индексы, добавление которых
уменьшит время выполнения запроса (указать таблицы/атрибуты, для
которых нужно добавить индексы, написать тип индекса; объяснить,
почему добавление индекса будет полезным для данного запроса). \
Для запросов 1-2 необходимо составить возможные планы
выполнения запросов. Планы составляются на основании предположения,
что в таблицах отсутствуют индексы. Из составленных планов необходимо
выбрать оптимальный и объяснить свой выбор. \
Изменятся ли планы при добавлении индекса и как? \
\
Для запросов 1-2 необходимо добавить в отчет вывод команды
`EXPLAIN ANALYZE` [запрос] \
Подробные ответы на все вышеперечисленные вопросы должны
присутствовать в отчете (планы выполнения запросов должны быть
нарисованы, ответы на вопросы - представлены в текстовом виде).
\
\
Сделать запрос для получения атрибутов из указанных таблиц,
применив фильтры по указанным условиям: \
Таблицы: `Н_ЛЮДИ`, `Н_СЕССИЯ`.
Вывести атрибуты: `Н_ЛЮДИ.ОТЧЕСТВО`, `Н_СЕССИЯ.УЧГОД`. \
Фильтры (AND): \
a) `Н_ЛЮДИ.ИД` = `142095`. \
b) `Н_СЕССИЯ.ЧЛВК_ИД` > `100012`. \
Вид соединения: `LEFT JOIN`. \
\
Сделать запрос для получения атрибутов из указанных таблиц, применив
фильтры по указанным условиям: \
Таблицы: `Н_ЛЮДИ`, `Н_ВЕДОМОСТИ`, `Н_СЕССИЯ`. \
Вывести атрибуты: `Н_ЛЮДИ.ФАМИЛИЯ`, `Н_ВЕДОМОСТИ.ИД`, `Н_СЕССИЯ.ЧЛВК_ИД`. \
Фильтры (AND): \
a) `Н_ЛЮДИ.ИД` > `163484`. \
b) `Н_ВЕДОМОСТИ.ЧЛВК_ИД` < `105590`. \
c) `Н_СЕССИЯ.УЧГОД` = `2008/2009`. \
Вид соединения: `LEFT JOIN`. 
