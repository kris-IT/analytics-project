```python
# Этап 1. Получение данных
```

Изучим данные, предоставленные сервисом для проекта.

## Импорт библиотек


```python
import pandas as pd# <импорт библиотеки pandas>
```

Прочитаем файл *music_project.csv* и сохраним его в переменной *df*. 


```python
df = pd.read_csv("/datasets/music_project.csv")# <чтение файла с данными с сохранением в df>
```

Получение первых 10 строк таблицы.


```python
df.head(10)# <получение первых 10 строк таблицы df>
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>userID</th>
      <th>Track</th>
      <th>artist</th>
      <th>genre</th>
      <th>City</th>
      <th>time</th>
      <th>Day</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>FFB692EC</td>
      <td>Kamigata To Boots</td>
      <td>The Mass Missile</td>
      <td>rock</td>
      <td>Saint-Petersburg</td>
      <td>20:28:33</td>
      <td>Wednesday</td>
    </tr>
    <tr>
      <td>1</td>
      <td>55204538</td>
      <td>Delayed Because of Accident</td>
      <td>Andreas Rönnberg</td>
      <td>rock</td>
      <td>Moscow</td>
      <td>14:07:09</td>
      <td>Friday</td>
    </tr>
    <tr>
      <td>2</td>
      <td>20EC38</td>
      <td>Funiculì funiculà</td>
      <td>Mario Lanza</td>
      <td>pop</td>
      <td>Saint-Petersburg</td>
      <td>20:58:07</td>
      <td>Wednesday</td>
    </tr>
    <tr>
      <td>3</td>
      <td>A3DD03C9</td>
      <td>Dragons in the Sunset</td>
      <td>Fire + Ice</td>
      <td>folk</td>
      <td>Saint-Petersburg</td>
      <td>08:37:09</td>
      <td>Monday</td>
    </tr>
    <tr>
      <td>4</td>
      <td>E2DC1FAE</td>
      <td>Soul People</td>
      <td>Space Echo</td>
      <td>dance</td>
      <td>Moscow</td>
      <td>08:34:34</td>
      <td>Monday</td>
    </tr>
    <tr>
      <td>5</td>
      <td>842029A1</td>
      <td>Преданная</td>
      <td>IMPERVTOR</td>
      <td>rusrap</td>
      <td>Saint-Petersburg</td>
      <td>13:09:41</td>
      <td>Friday</td>
    </tr>
    <tr>
      <td>6</td>
      <td>4CB90AA5</td>
      <td>True</td>
      <td>Roman Messer</td>
      <td>dance</td>
      <td>Moscow</td>
      <td>13:00:07</td>
      <td>Wednesday</td>
    </tr>
    <tr>
      <td>7</td>
      <td>F03E1C1F</td>
      <td>Feeling This Way</td>
      <td>Polina Griffith</td>
      <td>dance</td>
      <td>Moscow</td>
      <td>20:47:49</td>
      <td>Wednesday</td>
    </tr>
    <tr>
      <td>8</td>
      <td>8FA1D3BE</td>
      <td>И вновь продолжается бой</td>
      <td>NaN</td>
      <td>ruspop</td>
      <td>Moscow</td>
      <td>09:17:40</td>
      <td>Friday</td>
    </tr>
    <tr>
      <td>9</td>
      <td>E772D5C0</td>
      <td>Pessimist</td>
      <td>NaN</td>
      <td>dance</td>
      <td>Saint-Petersburg</td>
      <td>21:20:49</td>
      <td>Wednesday</td>
    </tr>
  </tbody>
</table>
</div>



Общая информация о данных таблицы *df*.





```python
df.info# <получение общей информации о данных в таблице df>
```




    <bound method DataFrame.info of          userID                              Track            artist  \
    0      FFB692EC                  Kamigata To Boots  The Mass Missile   
    1      55204538        Delayed Because of Accident  Andreas Rönnberg   
    2        20EC38                  Funiculì funiculà       Mario Lanza   
    3      A3DD03C9              Dragons in the Sunset        Fire + Ice   
    4      E2DC1FAE                        Soul People        Space Echo   
    ...         ...                                ...               ...   
    65074  729CBB09                            My Name            McLean   
    65075  D08D4A55  Maybe One Day (feat. Black Spade)       Blu & Exile   
    65076  C5E3A0D5                          Jalopiina               NaN   
    65077  321D0506                      Freight Train     Chas McDevitt   
    65078  3A64EF84          Tell Me Sweet Little Lies      Monica Lopez   
    
                genre            City        time        Day  
    0            rock  Saint-Petersburg  20:28:33  Wednesday  
    1            rock            Moscow  14:07:09     Friday  
    2             pop  Saint-Petersburg  20:58:07  Wednesday  
    3            folk  Saint-Petersburg  08:37:09     Monday  
    4           dance            Moscow  08:34:34     Monday  
    ...           ...               ...       ...        ...  
    65074         rnb            Moscow  13:32:28  Wednesday  
    65075         hip  Saint-Petersburg  10:00:00     Monday  
    65076  industrial            Moscow  20:09:26     Friday  
    65077        rock            Moscow  21:43:59     Friday  
    65078     country            Moscow  21:59:46     Friday  
    
    [65079 rows x 7 columns]>



Рассмотрим полученную информацию подробнее.

Всего в таблице 7 столбцов, тип данных у каждого столбца - < напишите название типа данных >.

Подробно разберём, какие в *df* столбцы и какую информацию они содержат:

* userID — идентификатор пользователя;
* Track — название трека;  
* artist — имя исполнителя;
* genre — название жанра;
* City — город, в котором происходило прослушивание;
* time — время, в которое пользователь слушал трек;
* Day — день недели.

Количество значений в столбцах различается. Это говорит о том, что в данных есть <введите определение> значения.



**Выводы**

Каждая строка таблицы содержит информацию о композициях определённого жанра в определённом исполнении, которые пользователи слушали в одном из городов в определённое время и день недели. Две проблемы, которые нужно решать: пропуски и некачественные названия столбцов. Для проверки рабочих гипотез особенно ценны столбцы *time*, *day* и *City*. Данные из столбца *genre* позволят узнать самые популярные жанры.

# Этап 2. Предобработка данных

Исключим пропуски, переименуем столбцы, а также проверим данные на наличие дубликатов.

Получаем перечень названий столбцов. Какая наблюдается проблема — кроме тех, что уже были названы ранее?


```python
df.columns# <перечень названий столбцов таблицы df>
```




    Index(['  userID', 'Track', 'artist', 'genre', '  City  ', 'time', 'Day'], dtype='object')



В названиях столбцов есть пробелы, которые могут затруднять доступ к данным.

Переименуем столбцы для удобства дальнейшей работы. Проверим результат.




```python
df.set_axis(['user_id', 'track_name', 'artist_name', 'genre_name', 'city', 'time', 'weekday'], axis='columns', inplace=True) # <переименование столбцов>
```


```python
df.columns# <проверка результатов - перечень названий столбцов>
```




    Index(['user_id', 'track_name', 'artist_name', 'genre_name', 'city', 'time',
           'weekday'],
          dtype='object')



Проверим данные на наличие пропусков вызовом набора методов для суммирования пропущенных значений.


```python
df.isnull().sum()# <суммарное количество пропусков, выявленных методом isnull() в таблице df>
```




    user_id           0
    track_name     1231
    artist_name    7203
    genre_name     1198
    city              0
    time              0
    weekday           0
    dtype: int64



Пустые значения свидетельствуют, что для некоторых треков доступна не вся информация. Причины могут быть разные: скажем,  не назван конкретный исполнитель народной песни. Хуже, если проблемы с записью данных. Каждый отдельный случай необходимо разобрать и выявить причину.

Заменяем пропущенные значения в столбцах с названием трека и исполнителя на строку 'unknown'. После этой операции нужно убедиться, что таблица больше не содержит пропусков.


```python
df['track_name'] = df['track_name'].fillna('unknown')# <замена пропущенных значений в столбце 'track_name' на строку 'unknown' специальным методом замены>

```


```python
df['artist_name'] = df['artist_name'].fillna('unknown')# <замена пропущенных значений в столбце 'artist_name' на строку 'unknown' специальным методом замены>
```


```python
df.isnull().sum()# <проверка: вычисление суммарного количества пропусков, выявленных в таблице df>
```




    user_id           0
    track_name        0
    artist_name       0
    genre_name     1198
    city              0
    time              0
    weekday           0
    dtype: int64



Удаляем в столбце с жанрами пустые значения; убеждаемся, что их больше не осталось.


```python
df = df.dropna(subset = ['genre_name'])# <удаление пропущенных значений в столбце 'genre_name'>
```


```python
df.isnull().sum()# <проверка>
```




    user_id        0
    track_name     0
    artist_name    0
    genre_name     0
    city           0
    time           0
    weekday        0
    dtype: int64



Необходимо установить наличие дубликатов.  Если найдутся, удаляем, и проверяем, все ли удалились.


```python
df.duplicated().sum()# <получение суммарного количества дубликатов в таблице df>
```




    3755




```python
df = df.drop_duplicates().reset_index(drop=True)# <удаление всех дубликатов из таблицы df специальным методом>
```


```python
df.duplicated().sum()# <проверка на отсутствие>
```




    0



Дубликаты могли появиться вследствие сбоя в записи данных. Стоит обратить внимание и разобраться с причинами появления такого «информационного мусора».

Сохраняем список уникальных значений столбца с жанрами в переменной *genres_list*. 

Объявим функцию *find_genre()* для поиска неявных дубликатов в столбце с жанрами. Например, когда название одного и того же жанра написано разными словами.






```python
genres_list = df['genre_name'].unique()# <сохранение в переменной genres_list списка уникальных значений, выявленных специальным методом в столбце 'genre_name'>
```


```python
def find_genre(genre): 
    count = 0
    for i in genres_list:
        if i == genre: 
            count += 1
    return count#кончании работы цикла функция возвращает значение счётчика

```

Вызов функции *find_genre()* для поиска различных вариантов названия жанра хип-хоп в таблице.

Правильное название — *hiphop*. Поищем другие варианты:

* hip
* hop
* hip-hop



```python
find_genre('hip')# <вызовом функции find_genre() проверяется наличие варианта 'hip'>
```




    1




```python
find_genre('hop')# <проверяется наличие варианта 'hop'>
```




    0




```python
find_genre('hip-hop')# <проверяется наличие варианта 'hip-hop'>
```




    0



Объявим функцию *find_hip_hop()*, которая заменяет  неправильное название этого жанра в столбце *'genre_name'* на *'hiphop'* и проверяет успешность выполнения замены.

Так исправляем все варианты написания, которые выявила проверка.


```python
def find_hip_hop(df, wrong):# <создание функции find_hip_hop()>
    df['genre_name'] = df['genre_name'].replace(wrong, 'hiphop')# функция принимает как параметры таблицу df и неверное название
    wrong_count = df[df['genre_name'] == wrong]['genre_name'].count()# к столбцу 'genre_name' применяется специальный метод, 
    return wrong_count# который заменяет второй параметр на строку 'hiphop'
find_hip_hop(df, 'hip')# результат работы равен подсчитанному методом count() числу значений столбца, 
# которые равны второму параметру
# функция возвращает результат
```




    0




```python
find_hip_hop(df,'hip')# <замена одного неверного варианта на hiphop вызовом функции find_hip_hop()>
```




    0



Получаем общую информацию о данных. Убеждаемся, что чистка выполнена успешно.


```python
df.info()# <получение общей информации о данных таблицы df>
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 60126 entries, 0 to 60125
    Data columns (total 7 columns):
    user_id        60126 non-null object
    track_name     60126 non-null object
    artist_name    60126 non-null object
    genre_name     60126 non-null object
    city           60126 non-null object
    time           60126 non-null object
    weekday        60126 non-null object
    dtypes: object(7)
    memory usage: 3.2+ MB
    

**Вывод**

На этапе предобработки в данных обнаружились не только пропуски и проблемы с названиями столбцов, но и всяческие виды дубликатов. Их удаление позволит провести анализ точнее. Поскольку сведения о жанрах важно сохранить для анализа, не просто удаляем все пропущенные значения, но заполним пропущенные имена исполнителей и названия треков. Имена столбцов теперь корректны и удобны для дальнейшей работы.

# Действительно ли музыку в разных городах слушают по-разному?

Была выдвинута гипотеза, что в Москве и Санкт-Петербурге пользователи слушают музыку по-разному. Проверяем это предположение по данным о трёх днях недели — понедельнике, среде и пятнице.

Для каждого города устанавливаем количество прослушанных  в эти дни композиций с известным жанром, и сравниваем результаты.

Группируем данные по городу и вызовом метода *count()* подсчитываем композиции, для которых известен жанр.


```python
df.groupby('city').count()# <группировка данных таблицы df по столбцу 'city' и подсчёт количества значений столбца 'genre_name'>
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>user_id</th>
      <th>track_name</th>
      <th>artist_name</th>
      <th>genre_name</th>
      <th>time</th>
      <th>weekday</th>
    </tr>
    <tr>
      <th>city</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Moscow</td>
      <td>41892</td>
      <td>41892</td>
      <td>41892</td>
      <td>41892</td>
      <td>41892</td>
      <td>41892</td>
    </tr>
    <tr>
      <td>Saint-Petersburg</td>
      <td>18234</td>
      <td>18234</td>
      <td>18234</td>
      <td>18234</td>
      <td>18234</td>
      <td>18234</td>
    </tr>
  </tbody>
</table>
</div>



В Москве прослушиваний больше, чем в Питере, но это не значит, что Москва более активна. У Яндекс.Музыки в целом больше пользователей в Москве, поэтому величины сопоставимы.

Сгруппируем данные по дню недели и подсчитаем прослушанные в понедельник, среду и пятницу композиции, для которых известен жанр.


```python
df.groupby('weekday').count()# <группировка данных по столбцу 'weekday' и подсчёт количества значений столбца 'genre_name'>

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>user_id</th>
      <th>track_name</th>
      <th>artist_name</th>
      <th>genre_name</th>
      <th>city</th>
      <th>time</th>
    </tr>
    <tr>
      <th>weekday</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Friday</td>
      <td>21482</td>
      <td>21482</td>
      <td>21482</td>
      <td>21482</td>
      <td>21482</td>
      <td>21482</td>
    </tr>
    <tr>
      <td>Monday</td>
      <td>20866</td>
      <td>20866</td>
      <td>20866</td>
      <td>20866</td>
      <td>20866</td>
      <td>20866</td>
    </tr>
    <tr>
      <td>Wednesday</td>
      <td>17778</td>
      <td>17778</td>
      <td>17778</td>
      <td>17778</td>
      <td>17778</td>
      <td>17778</td>
    </tr>
  </tbody>
</table>
</div>



Понедельник и пятница — время для музыки; по средам пользователи немного больше вовлечены в работу.

Создаём функцию *number_tracks()*, которая принимает как параметры таблицу, день недели и название города, а возвращает количество прослушанных композиций, для которых известен жанр. Проверяем количество прослушанных композиций для каждого города и понедельника, затем среды и пятницы.


```python
def number_tracks(df, day, city):
    track_list = df[(df['weekday'] == day) & (df['city'] == city)]
    track_list_count = track_list['genre_name'].count()
    return track_list_count
# и одновременно значение в столбце 'city' равно параметру city
# в переменной track_list_count сохраняется число значений столбца 'genre_name',
# рассчитанное методом count() для таблицы track_list
# функция возвращает значение track_list_count
```


```python
number_tracks(df, 'Monday', 'Moscow')
# <список композиций для Москвы в понедельник>
```




    15347




```python
number_tracks(df, 'Monday', 'Saint-Petersburg')# <список композиций для Санкт-Петербурга в понедельник>
```




    5519




```python
number_tracks(df, 'Wednesday', 'Moscow')# <список композиций для Москвы в среду>
```




    10865




```python
number_tracks(df, 'Wednesday', 'Saint-Petersburg')# <список композиций для Санкт-Петербурга в среду>
```




    6913




```python
number_tracks(df, 'Friday', 'Moscow')# <список композиций для Москвы в пятницу>
```




    15680




```python
number_tracks(df, 'Friday', 'Saint-Petersburg')# <список композиций для Санкт-Петербурга в пятницу>
```




    5802



Сведём полученную информацию в одну таблицу, где ['city', 'monday', 'wednesday', 'friday'] названия столбцов.



```python
data = [['Moscow', 15347, 10865, 15680], ['Saint-Petersburg', 5519, 6913, 5802]]
columns = ['city', 'monday', 'wednesday', 'friday']
table = pd.DataFrame(data=data, columns=columns)
 # <таблица с полученными данными>
```

**Вывод**

Результаты показывают, что относительно среды музыку в Петербурге и Москве слушают «зеркально»: в Москве пики приходятся на понедельник и пятницу, а в среду время прослушивания снижается. Тогда как в Санкт-Петербурге среда — день самого большого интереса к музыке, а в понедельник и пятницу он меньше, причём почти одинаково меньше.

# Утро понедельника и вечер пятницы — разная музыка или одна и та же?

Ищем ответ на вопрос, какие жанры преобладают в разных городах в понедельник утром и в пятницу вечером. Есть предположение, что в понедельник утром пользователи слушают больше бодрящей музыки (например, жанра поп), а вечером пятницы — больше танцевальных (например, электронику).

Получим таблицы данных по Москве *moscow_general* и по Санкт-Петербургу *spb_general*.


```python
moscow_general = df[df['city'] == 'Moscow']# получение таблицы moscow_general из тех строк таблицы df, 
# для которых значение в столбце 'city' равно 'Moscow'
```


```python
spb_general = df[df['city'] == 'Saint-Petersburg']
```

Создаём функцию *genre_weekday()*, которая возвращает список жанров по запрошенному дню недели и времени суток с такого-то часа по такой-то.


```python
def genre_weekday(df, day, time1, time2):
    genre_list = df[(df['weekday'] == day) & (df['time'] > time1) & (df['time'] < time2)]
    genre_lst_sorted = genre_list.groupby('genre_name')['genre_name'].count()
    genre_list_sorted = genre_lst_sorted.sort_values(ascending = False).head(10)
    return genre_list_sorted
```

Cравниваем полученные результаты по таблице для Москвы и Санкт-Петербурга в понедельник утром (с 7 до 11) и в пятницу вечером (с 17 до 23).


```python
genre_weekday(moscow_general, 'Monday', '07:00:00', '11:00:00')# <вызов функции для утра понедельника в Москве (вместо df таблица moscow_general)>
```




    genre_name
    pop            781
    dance          549
    electronic     480
    rock           474
    hiphop         286
    ruspop         186
    world          181
    rusrap         175
    alternative    164
    classical      157
    Name: genre_name, dtype: int64




```python
genre_weekday(spb_general, 'Monday', '07:00:00', '11:00:00')# <вызов функции для утра понедельника в Петербурге (вместо df таблица spb_general)>
```




    genre_name
    pop            218
    dance          182
    rock           162
    electronic     147
    hiphop          80
    ruspop          64
    alternative     58
    rusrap          55
    jazz            44
    classical       40
    Name: genre_name, dtype: int64




```python
genre_weekday(moscow_general, 'Friday', '17:00:00', '23:00:00')# <вызов функции для вечера пятницы в Москве>
```




    genre_name
    pop            713
    rock           517
    dance          495
    electronic     482
    hiphop         273
    world          208
    ruspop         170
    alternative    163
    classical      163
    rusrap         142
    Name: genre_name, dtype: int64




```python
genre_weekday(spb_general, 'Friday', '17:00:00', '23:00:00')# <вызов функции для вечера пятницы в Питере>
```




    genre_name
    pop            256
    rock           216
    electronic     216
    dance          210
    hiphop          97
    alternative     63
    jazz            61
    classical       60
    rusrap          59
    world           54
    Name: genre_name, dtype: int64



Популярные жанры в понедельник утром в Питере и Москве оказались похожи: везде, как и предполагалось, популярен поп. Несмотря на это, концовка топ-10 для двух городов различается: в Питере в топ-10 входит джаз и русский рэп, а в Москве жанр *world*.

В конце недели ситуация не меняется. Поп-музыка всё так же на первом месте. Опять разница заметна только в концовке топ-10, где в Питере пятничным вечером тоже присутствует жанр *world*.

**Вывод**

Жанр поп безусловный лидер, а топ-5 в целом не различается в обеих столицах. При этом видно, что концовка списка более «живая»: для каждого города выделяются более характерные жанры, которые действительно меняют свои позиции в зависимости от дня недели и времени.

# Москва и Питер — две разные столицы, два разных направления в музыке. Правда?

Гипотеза: Питер богат своей рэп-культурой, поэтому это направление там слушают чаще, а Москва — город контрастов, но основная масса пользователей слушает попсу.



Сгруппируем таблицу *moscow_general* по жанру, сосчитаем численность композиций каждого жанра методом *count()*, отсортируем в порядке убывания и сохраним результат в таблице *moscow_genres*.

Просмотрим первые 10 строк этой новой таблицы.


```python
moscow_genres = moscow_general.groupby('genre_name')['genre_name'].count()
moscow_genres = moscow_genres.sort_values(ascending = False)
df.groupby('genre_name')
df.groupby('genre_name')['genre_name']
df.groupby('genre_name').count()
df.sort_values(by = 'genre_name', ascending = False)
# подсчёт числа значений 'genre_name' в этой группировке методом count(), 
# сортировка Series в порядке убывания и сохранение в moscow_genres
```


```python
moscow_genres.head(10)# <просмотр первых 10 строк moscow_genres>
```




    genre_name
    pop            5892
    dance          4435
    rock           3965
    electronic     3786
    hiphop         2096
    classical      1616
    world          1432
    alternative    1379
    ruspop         1372
    rusrap         1161
    Name: genre_name, dtype: int64



Сгруппируем таблицу *spb_general* по жанру, сосчитаем численность композиций каждого жанра методом *count()*, отсортируем в порядке убывания и сохраним результат в таблице *spb_genres*.

Просматриваем первые 10 строк этой таблицы. Теперь можно сравнивать два города.


```python
spb_genres = spb_general.groupby('genre_name')['genre_name'].count()# <группировка таблицы spb_general, расчёт, сохранение в spb_genres>
```


```python
spb_genres = spb_genres.sort_values(ascending = False)
spb_genres.head(10)# <просмотр первых 10 строк spb_genres>
```

**Вывод**

В Москве, кроме абсолютно популярного жанра поп, есть направление русской популярной музыки. Значит, что интерес к этому жанру шире. А рэп, вопреки предположению, занимает в обоих городах близкие позиции.

# Этап 4. Результаты исследования


Рабочие гипотезы:

* музыку в двух городах — Москве и Санкт-Петербурге — слушают в разном режиме;

* списки десяти самых популярных жанров утром в понедельник и вечером в пятницу имеют характерные отличия;

* население двух городов предпочитает разные музыкальные жанры.

**Общие результаты**

Москва и Петербург сходятся во вкусах: везде преобладает популярная музыка. При этом зависимости предпочтений от дня недели в каждом отдельном городе нет — люди постоянно слушают то, что им нравится. Но между городами в разрезе дней неделей наблюдается зеркальность относительно среды: Москва больше слушает в понедельник и пятницу, а Петербург наоборот - больше в среду, но меньше в понедельник и пятницу.

В результате первая гипотеза < укажите подтверждена/не подтверждена>, вторая гипотеза < укажите подтверждена/не подтверждена > и третья < укажите подтверждена/не подтверждена >.
