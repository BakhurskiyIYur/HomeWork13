# Домашнее задание №13 (Тема "Сбор и использование статистики")

<img src="pic/0.JPG" align="center" />
<img src="pic/0_1.JPG" align="center" />
<img src="pic/0_2.JPG" align="center" />
<img src="pic/0_3.JPG" align="center" />

* Реализовать прямое соединение двух или более таблиц
  <img src="pic/1.JPG" align="center" />
* Реализовать левостороннее (или правостороннее) соединение двух или более таблиц
  <img src="pic/2.JPG" align="center" />
* Реализовать кросс соединение двух или более таблиц
  <img src="pic/3.JPG" align="center" />
* Реализовать полное соединение двух или более таблиц
  <img src="pic/4.JPG" align="center" />
* Реализовать запрос, в котором будут использованы разные типы соединений
  <img src="pic/5.JPG" align="center" />
* Сделать комментарии на каждый запрос
* К работе приложить структуру таблиц, для которых выполнялись соединения

  <pre><details><summary>Структура таблицы object</summary>
  CREATE TABLE IF NOT EXISTS public.object (
  id serial primary key NOT NULL,
  object_name character varying  NOT NULL      );
  </details></pre>

  <pre><details><summary>Структура таблицы parameter</summary>
  CREATE TABLE IF NOT EXISTS public.parameter (
  id serial primary key NOT NULL,
  obj_id integer,
  param_name character varying  NOT NULL      );
  </details></pre>

  <pre><details><summary>Структура таблицы history</summary>
  CREATE TABLE IF NOT EXISTS public.history (
  id serial primary key NOT NULL,
  param_id integer NOT NULL,
  val_time timestamp with time zone NOT NULL,
  val float );
  </details></pre>

  

