# Домашнее задание №13 (Тема "Сбор и использование статистики")

<br>__*На виртуальной машине развернул кластер Postgres версии 15. Создал базу данных testdb.*__
<img src="pic/0.JPG" align="center" />

<br>__*В базе данных testdb создал таблицу object, в которой будут храниться названия объектов-родителей:*__
<img src="pic/0_1.JPG" align="center" />

<br>__*Далее создал таблицу parameter. В ней будет храниться перечень параметров, которые имеют свзяь с родительским объектом из таблицы object по полю obj_id:*__
<img src="pic/0_2.JPG" align="center" />

<br>__*И также создал таблицу history для хранения исторических значений параметров (param_id):*__
<img src="pic/0_3.JPG" align="center" />

* Реализовать прямое соединение двух или более таблиц
  
  <br>__*Соединение находит пары строк, которые соединяются и удовлетворяют предикату соединения. В показанном ниже запросе используется первый предикат соединения "h.param_id = p.id", позволяющий соединить значения (h.val_time, h.val) с параметром (p. param_name), а второй предикат "p.obj_id = o.id", позволяющий найти объекты (o.object_name), к которым относятся параметры (p. param_name):*__  
  <img src="pic/1.JPG" align="center" />
  
* Реализовать левостороннее (или правостороннее) соединение двух или более таблиц

  <br>__*Внешнее соединение, которое выводит все строки из левой таблицы parameter и только те записи, которые совпадают из правой таблицы object по соответствующему предикату соединения "p.obj_id = o.id". Иными словами, для каждого параметра из таблицы parameter определил родителя из таблицы object.*__
  <img src="pic/2.JPG" align="center" />
  
* Реализовать кросс соединение двух или более таблиц
  
  <br>__*Перекрестное соединение возвращает декартово произведение строк из наборов строк в соединении. Другими словами, он соединяет каждую строку из первого набора строк с каждой строкой из второго набора строк. Например, соединим таблицу parameter и таблицу history:*__  
  <img src="pic/3.JPG" align="center" />
  
* Реализовать полное соединение двух или более таблиц
  
  <br>__*Если для какой-либо из таблиц не нашлось строки в другой таблице, то строка все равно попадает в результат, а значения столбцов другой таблицы равны null.*__  
  <img src="pic/4.JPG" align="center" />
  
* Реализовать запрос, в котором будут использованы разные типы соединений
  
  <br>__*В следующем запросе определяю текущее (последнее) значение для каждого параметра. Также в общий набор данных добавляю родителей (o.object_name), к которым принадлежат параметры (p.param_name):*__
  <img src="pic/5.JPG" align="center" />
  
* Сделать комментарии на каждый запрос
* К работе приложить структуру таблиц, для которых выполнялись соединения

<pre><details><summary>Структура таблицы object</summary>
    CREATE TABLE IF NOT EXISTS public.object (
    id serial primary key NOT NULL,
    object_name character varying  NOT NULL      );</details></pre>  
<pre><details><summary>Структура таблицы parameter</summary>
    CREATE TABLE IF NOT EXISTS public.parameter (
    id serial primary key NOT NULL,
    obj_id integer,
    param_name character varying  NOT NULL      );</details></pre>  
<pre><details><summary>Структура таблицы history</summary>
    CREATE TABLE IF NOT EXISTS public.history (
    id serial primary key NOT NULL,
    param_id integer NOT NULL,
    val_time timestamp with time zone NOT NULL,
    val float );</details></pre>

  

