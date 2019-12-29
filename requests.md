# Запросы

## Рейтинг новогодних ёлок

Рейтинг новогодних ёлок содержит информацию о топе новогодних ёлок по оценкам голосования пользователей.
Для получения рейтинга используется метод GET. top - число ёлок в рейтинге.

```
GET /raiting?top=:top
```

Content type: ``` application/vnd.xmas.treelist+json ```

Возвращает представление Tree collection из representations.md.

## Список новогодних елок вблизи пользователя

```
GET /around?lg=:lg&lt=:lt&width=:width&height=:height
```

Возваращает список новогдних ёлок вблизи пользователя. Параметрами выступают долгота lg, ширина lt - местонахождение пользователя.
Width, height отклонения по долготе и ширине от местонахождения пользователя.

Content type: ``` application/vnd.xmas.treelist+json ```

Возвращает представление Tree collection из representations.md.

##  Получение информации о конкретной новогодней ёлке

```
GET /trees/:id
```
Content type: ``` application/vnd.xmas.tree + json ```

Возвращает представление Tree по идентификатору.

## Проголосовать за новогоднюю елку

```
POST /trees/:id/vote 
```
Content type: ``` application/vnd.xmas.vote + json ```

Выставление рейтинга в звездах пользователем. Посылается представление Vote из representations.md.

## Получение информации о выставленном голосе за конкретную ёлку пользователем

```
GET /trees/:id/vote 
```
Content type: ``` application/vnd.xmas.vote + json ```

Возвращает представление Vote из representations.md.

В предыдущих двух запросах в http заголовке Authorization нужно передать параметр Basic user_id, где user_id - целое положительное число, идентификатор пользователя. В противном случае вернется код ошибки 401.
