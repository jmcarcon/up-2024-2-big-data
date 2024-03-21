SQL CHALLENGES
===========

_By Juan Manuel Carrillo_.

------------

1. Show the most expensive article from every brand, and the average prices of each brand

For this exercise we just had to join the articles table with the 
manufacturers table, by linking manufacturers_id from the first table
with the primary key of the second mentioned table.

After joining the tables, we grouped the records by brand, and just by 
using the `MAX` and the `AVG` functions applied on price, we get the most
expensive article by brand and the average price for each brand.

```sql
SELECT a.title AS ARTICLE, m.title AS BRAND, MAX(a.price) AS PRICE, AVG(a.price) AVERAGE_PRICE
FROM articles AS a
LEFT JOIN manufacturers as m on a.manufacturer_id = m.id
GROUP BY m.title;
```

By applying this SQL, we got the next results:

![img.png](img.png)

2. How many articles from each category are there?

For this problem, we had to use 3 tables: articles, articles_categories 
and categories. All these 3 tables were linked through the article_id
and the category_id.

After making the relationship between the tables we just had to group
the registers by category and use the `COUNT` function to get the 
number of articles
```sql
SELECT c.title AS CATEGORIA, COUNT(*) AS CANTIDAD_ARTICULOS
FROM articles as a
LEFT JOIN articles_categories as ac on a.id=ac.article_id
LEFT JOIN categories as c on ac.category_id=c.id
GROUP BY c.title;
```
By applying this SQL, we got the next results:

![img_1.png](img_1.png)

3. Idem brand?

In order to solve this problem, we just had to use the articles and 
manufacturers tables. We linked these 2 tables  through the manufacturers_id, 
just like we did in problem 1.

After making the relationship between the tables we just had to group
the registers by brand and use the `COUNT` function to get the 
number of articles
```sql
SELECT m.title AS MARCA, COUNT(*) AS CANTIDAD_ARTICULOS
FROM articles as a
LEFT JOIN manufacturers as m on a.manufacturer_id = m.id
GROUP BY m.title;
```
By applying this SQL, we got the next results:

![img_2.png](img_2.png)

4. Top 5 relevant articles per brand

For this final challenge we had to connect the same table, the articles one, 
with itself, to get the registers through the `COUNT` function.

After having this, we just accessed to the first 5 and made the relationship
with the manufacturers table. All this while having into account the relevance 
of the articles, and ordering the table by brand and relevance.

```sql
SELECT m.title AS MARCA, a.title AS ARTICULO, a.relevance AS RELEVANCIA
FROM articles AS a
JOIN manufacturers AS m ON a.manufacturer_id = m.id
WHERE (
    SELECT COUNT(*)
    FROM articles AS a2
    WHERE a2.manufacturer_id = a.manufacturer_id AND a2.relevance >= a.relevance
) <= 5
ORDER BY MARCA, RELEVANCIA DESC;
```
By applying this SQL, we got the next results:
![img_3.png](img_3.png)
