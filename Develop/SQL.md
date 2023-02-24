
## JOIN

Задача — найти записи о пользователях в одной таблице, для которых нет записей о топиках в другой таблице.

#### INNER  JOIN

```

-- В выборке участвуют не все поля только для того, чтобы уместить
-- ее на экран, а вообще здесь можно использовать `*`
SELECT first_name, title
  FROM users JOIN topics ON users.id = topics.user_id LIMIT 5;

 first_name |            title
------------+------------------------------
 Sean       | beatae voluptatem commodi
 Wyatt      | tempora accusamus nostrum
 Oleta      | eaque fugiat consequatur
 Brandon    | aut exercitationem expedita
 Domenica   | voluptatem soluta similique

```
 Результатом такого запроса станет выборка, в которую попали поля обеих таблиц. Здесь соединяются две таблицы: `users` и `topics` по условию `users.id = topics.user_id`. Это важное условие для правильной работы. 
 
`
`JOIN` — это сокращенная версия соединения `INNER JOIN`, то есть внутреннего соединения.
`

#### LEFT JOIN
`
`LEFT JOIN` берет все данные из одной таблицы и присоединяет к ним данные из другой, если они присутствуют. Если нет, то заполняет их `NULL`. Чисто технически этот запрос отличается только тем, что добавляется слово `LEFT`:
`

```
SELECT first_name, title FROM users
  LEFT JOIN topics ON users.id = topics.user_id LIMIT 5;

first_name |            title
------------+------------------------------
 Sean       | beatae voluptatem commodi
 Wyatt      | tempora accusamus nostrum
 Mia        |
 Royal      |
 Enos       | et eos dicta

```
`LEFT JOIN` полезен, когда нам нужно работать со всеми данными одной таблицы и связанными с ними записями, если они есть. Если их нет, то ничего страшного, мы все равно хотим получить данные из первой таблицы.
