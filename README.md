# SQL-EX
# 1, 2, 3, 4, 5, 6, 7, 8, 9, 14, 16, 29, 34  https://www.sql-ex.ru/learn_exercises.php?LN=1
1)
     select model, speed, hd from PC
     where price <500
     2)
     Select distinct maker 
     from Product
     where type = 'Printer'
     3)
     Select 
     model,
     ram,
     screen
     from laptop
     where price > 1000
     4)
     select * from Printer
     where color = 'y'
     5)
     Select  model, speed, hd from PC
     where (CD='12x' or CD='24x')
     and price<600
     6)
     select distinct 
       t2.maker,
       t1.speed
         
     from Laptop t1
     inner join Product  t2
     on t1.model= t2.model
     and t1.hd>=10
     
     9)
     select distinct product.maker from product
     inner join pc
     on (pc.model=product.model) and (pc.speed>=450)
     14)
     Select distinct
       t1.class,
       t1.name,
       t2.country
     from Ships t1
     inner join Classes t2
     on (t1.class=t2.class)
     and (t2.numGuns>=10)
     
     
     7) select 
       a.model,
       price 
     from (
       select
         model,
         price 
       from PC 
       union
       select
         model,
         price 
       from Laptop
       union
       select
         model,
         price 
       from Printer
      ) 
     as a inner join Product p 
     on a.model = p.model
     WHERE p.maker = 'B'
     
     8)
     SELECT maker FROM product where type='pc'
     EXCEPT
     SELECT maker FROM product where type='laptop'
     
     34)
     Select 
     name 
     from classes,ships 
     where launched >=1922 
     and displacement>35000 
     and type='bb' 
     and ships.class = classes.class
     29)
     SELECT t1.point, t1.date, inc, out
     FROM income_o t1 LEFT JOIN outcome_o t2 ON t1.point = t2.point
     AND t1.date = t2.date
     UNION
     SELECT t2.point, t2.date, inc, out
     FROM income_o t1 RIGHT JOIN outcome_o t2 ON t1.point = t2.point
     AND t1.date = t2.date
     
     16)
     SELECT DISTINCT p1.model, p2.model, p1.speed, p1.ram
     FROM pc p1, pc p2
     WHERE p1.speed = p2.speed AND p1.ram = p2.ram AND p1.model > p2.model
