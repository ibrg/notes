
## JOIN
#### INNER  JOIN

задача — найти записи о пользователях в одной таблице, для которых нет записей о топиках в другой таблице.

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

<figcaption>

The [ABC Train](https://example.com) is *very* big and red.

</figcaption>
 Результатом такого запроса станет выборка, в которую попали поля обеих таблиц. Здесь соединяются две таблицы: `users` и `topics` по условию `users.id = topics.user_id`. Это важное условие для правильной работы. 