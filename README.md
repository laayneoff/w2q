## Лабораторная работа №1 [15.02.2025]
![0_table](https://github.com/user-attachments/assets/587dc3ae-b03c-4c5d-a64a-a5c93a396292)

### Таблица
![](/LabW1/0_table.png)
### Задание №1
Выберите из таблицы orders все заказы
![1](https://github.com/user-attachments/assets/b17c43f9-52f8-4471-904e-041591838089)

![](/LabW1/1.png)

```
SELECT * FROM orders;
```
### Задание №2
Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
![2](https://github.com/user-attachments/assets/1933ce85-020e-4b17-959b-4fefb00f98af)

![](/LabW1/2.png)

```
SELECT * FROM orders WHERE status IN ('cancelled','in_progress','delivery')
```
### Задание №3
Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
![3](https://github.com/user-attachments/assets/95cea53b-b2ad-420c-a739-f7747a65002b)

![](/LabW1/3.png)

```
SELECT * FROM orders WHERE status = 'new' OR status = 'cancelled'
```
### Задание №4
Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа
![4](https://github.com/user-attachments/assets/db101ab0-177b-47cb-b5d0-cbf3977e8ca3)

![](/LabW1/4.png)

```
SELECT id,sum FROM orders WHERE products_count > 3
```
## Лабораторная работа №2 [22.02.2025]
### Задание №161

#### Таблица
![0_table](https://github.com/user-attachments/assets/dd2f4916-17d5-4ddf-aff2-d6735c86abb0)

![](/LabW2/161/0_table.png)

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![1](https://github.com/user-attachments/assets/d845dd44-8443-4e61-9a47-3ac9d3ee8361)

![](/LabW2/161/1.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 3;
```
2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![2](https://github.com/user-attachments/assets/73f48bc6-a005-4500-86ba-350bff84d784)

![](/LabW2/161/2.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 2;
```
### Задание №166
#### Таблица
![0_table](https://github.com/user-attachments/assets/44bcce2f-3c87-4a97-8334-ff2523cc5a68)

![](/LabW2/166/0_table.png)

3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).
![1](https://github.com/user-attachments/assets/b27cabc3-4d24-4cbd-8572-ca39c22691ee)

![](/LabW2/166/1.png)

```
insert into orders (id, products, sum) value (6, 4, 8000);
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/3437e61d-04ff-4ca5-a2ac-90737f765c53)

![](/LabW2/166/1_result.png)

### Задание №167
#### Таблица
![0_table](https://github.com/user-attachments/assets/ac3e2dfd-99f1-4757-85b8-0d4d104581fb)

![](/LabW2/167/0_table.png)

4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
   ![1](https://github.com/user-attachments/assets/d6835058-3e3a-4fe3-9e6c-c1c3a10e51fb)

![](/LabW2/167/1.png)

```
insert into products (id, name, count, price) value (7, 'VR-очки', 2, 70000);
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/0b029cad-414c-4ada-917f-d600ac888e66)

![](/LabW2/167/1_result.png)

### Задание №172
#### Таблица
![0_table](https://github.com/user-attachments/assets/d02acd94-2c5c-4ee5-948e-d20e8d293612)

![](/LabW2/172/0_table.png)

5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.
![1](https://github.com/user-attachments/assets/28757bba-89db-4728-bb89-a752beacd007)

![](/LabW2/172/1.png)

```
update products set name='PS5' where id=7;
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/caf048fb-bfd2-457a-abf1-43ccfbc1474e)

![](/LabW2/172/1_result.png)
