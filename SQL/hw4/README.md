## Ödev 4

Aşağıdaki sorgu senaryolarını [dvdrental](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip) örnek veri tabanı üzerinden gerçekleştiriniz.

1. **film** tablosunda bulunan **replacement_cost** sütununda bulunan birbirinden farklı değerleri sıralayınız.
2. **film** tablosunda bulunan **replacement_cost** sütununda birbirinden farklı kaç tane veri vardır?
3. **film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
4. **country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
5. **city** tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

## Çözüm

1. 
``` sql
    SELECT DISTINCT replacement_cost FROM film;

```

2. 
``` sql
    SELECT COUNT(DISTINCT replacement_cost) FROM film;

```

3. 
``` sql
    SELECT COUNT(*) FROM film WHERE (title LIKE 'T%') AND (rating = 'G');

```

4. 
``` sql
    SELECT COUNT(*) FROM country WHERE LENGTH(country) = 5;

```

5. 
``` sql
    SELECT COUNT(*) FROM city WHERE city ILIKE '%r';

```