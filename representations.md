# Представления

## Tree

Представление новогодной елки состоит из следующих полей: долгота lg, ширина lt, рейтинг rating, id - ссылка /trees/:id, vote - ссылка на представленияе Vote /trees/:id/vote.
```
{
  "lg": float,
  "lt": float,
  "rating": float,
  "id": str,
  "vote": str,
}
```
## Tree collection

Представление списка новогодних ёлок. Состоит из полей trees - список ёлок, содержит представления Tree; self - ссылка на данное представление, которое может быть получено из запросов GET, описанных в requests.md.

```
{
  "trees": [tree],
  "self": str,
}
```

## Vote

Представление одного голоса состоит из полей id - ссылка /trees/:id/vote, stars - число звезд, выставленных данной елке пользователем.
```
{
  "id": str,
  "stars": int,
}
```
