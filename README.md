# Описание бизнес-задачи

На платформе для подготовки к собеседованиям IT Resume несколько месяцев проводились разные рекламные кампании по привлечению пользователей. На тест воронки выделялся 1 месяц. Т.е. 1 месяц = 1 рекламная воронка. Далее необходимо было принять решение - какие воронки масштабировать, а какие порезать. 

Система монетизации платформы - подписочная модель. 

# Как я решала задачу

Мной было предложено провести когортный анализ rolling retention. Предпоссылки следующие: 

1. Факт однозначной разбивки рекламных тестов по месяцам делает очень удобным анализ динамики поведения клиентов в разрезе рекламных когорт 
2. Т.к. модель монетизации платформы - подписка, то логичнее всего оценивать именно долгосрочную динамику удержания, а не деньги, заработанные в моменте
3. В проведенных ранее исследованиях мной было установлено, что `lifetime` обычного (неплатящего) пользователя в данном продукте очень сильно коррелирован с `LTV` когорты в целом. 

> По поводу последнего - стоит отметить, что это не всегда так. Когорта пользователей может очень долго и вовлеченно пользоваться бесплатным функционалом, однако совсем не покупать подписку. 

Выбор `rolling retention` среди других видов удержания обусловлен тем, что в силу специфики платформы заход в конкретный `n`-день нам не так важно. Больше играет роль, вернулся ли пользователь в целом на платформу спустя день, неделю или даже полгода. 

# С какими данными работала 

Для анализа я использовала базу `simulative` и, в частности, оценивал заходы на платформу по таблице `userentry`.

Данные для подключения:

```
* Хост: 95.163.241.236
* Порт: 5432
* База данных: simulative
* Юзер: student
* Пароль: qweasd963
```

# Код

Свой код я описал [**здесь**](script.sql)

# Бизнес-выводы

Свои выводы я описал [**здесь**](insights.md)
