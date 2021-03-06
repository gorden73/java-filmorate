# Filmorate project
Educational project on creating a service
<br>for selecting films based on their rating

<br>Фич-лист:
<br> - Функциональность «Отзывы» (4 сторипоинта)
<br> - Функциональность «Поиск» (5 сторипоинтов)
<br> - Функциональность «Общие фильмы» (2 сторипоинта)
<br> - Функциональность «Рекомендации» (5 сторипоинтов)
<br> - Функциональность «Лента событий» (4 сторипоинта)
<br> - Функциональность «Популярные фильмы» (2 сторипоинта)
<br> - Функциональность «Фильмы по режиссёрам» (4 сторипоинта)

<br>![ER diagram](/er-filmorate/ER-filmorate.png)
<br>Примеры запросов:
1. Выгрузка всех пользователей:
   <br>SELECT *
   <br>FROM user;

2. Выгрузка одного пользователя (n - id пользователя):
   <br>SELECT *
   <br>FROM user
   <br>WHERE user_id = n;

3. Выгрузка друзей пользователя (n - id пользователя):
   <br>SELECT friend_id
   <br>FROM friend
   <br>WHERE user_id = n;

4. Выгрузка общих друзей
с другим пользователем: <br>(n - id 1 пользователя)
   <br>(m - id 2 пользователя)		
   <br>SELECT friend_id
   <br>FROM friend
   <br>WHERE user_id = n
   <br>AND user_id = m
   <br>GROUP BY friend_id;

5. Выгрузка всех фильмов:
   <br>SELECT *
   <br>FROM film;

6. Выгрузка одного фильма (n - id фильма):
   <br>SELECT *
   <br>FROM film
   <br>WHERE film_id = n;

7. Выгрузка N-популярных фильмов:
   <br>SELECT film_id
   <br>FROM like
   <br>GROUP BY film_id
   <br>ORDER BY COUNT(user_id) DESC
   <br>LIMIT N;