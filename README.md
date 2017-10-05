2017-2018
=============

# Домашка 1

Вы могли заметить что в последнее время в Минске очень плотно взялись вырубкой и обрезкой деревьев. И многие люди расстраиваются из-за того, в том числе Валик. А расстраиваются по-большей части из-за того, что критерии действий с деревьями совсем не ясны. Нам, как программистам, хотелось бы понимать четкий алгоритм действий.

В рамках нашей первой домашней работы вы должны автоматизировать данную задачу и написать программу, которая бы автоматически принимала решение о необходимом действии: оставить дерево в покое, обрезать ветки или срубить.

Некоторые из вас знают что в мире программирования обычные деревья не растут. Конечно можно пытаться определить различные критерии по фотографии самого дерева, но для первой домашней работы было бы немного черезчур. Поэтому для упрощения в качестве деревьев возьмем самые обычные [бинарные деревья](https://ru.wikipedia.org/wiki/%D0%94%D0%B2%D0%BE%D0%B8%D1%87%D0%BD%D0%BE%D0%B5_%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE). Если вы никогда не сталкивались с такой структурой данных - гугл вам в помощь.

Как известно - вырастить свой лес это довольное долгое занятие и может занять лет 30-50. Валик с Юрой позаботились об этом для вас и высадили очень давно свой лес на стеройдах. К сожалению он еще не успел вырасти, но к вечеру пятницы обещал взойти и быть доступным по [ссылке](https://rubyroidlabs.com/trees.zip). В данном лесу каждое дерево представляет собой отдельный файл, который вы найдете в архиве. Внутри каждого файла лежит сериализованное дерево в формате JSON.

Простое дерево в файле выглядит примерно следующим образом:

```small.tree
[1,[[2,[3,4]],[3,[5,2]]]]
```

Если мы попытаемся отобразить данное дерево более классическим образом:

```
     1
  /     \  
  2      3
/  \    /  \
3   4   5   2
```

Каждый узел данного дерева может являться:

- Массивом, где первый элемент это значение узла, а второй элемент это дочерние узлы ( левый и правый ).
- Число, что означает что у данного узла нету наследников.

### Задание (Level 1)

В самом простейшем варианте задания вам нужно научиться читать некоторые деревья по именам из архива и выводить их на экран в формате, который был представлен чуть выше. Имена деревьев должны передаваться в программу с использованием ENV-переменных.

Пример работы:

```
$ NAME=small ruby trees.rb

     1
  /     \  
  2      3
/  \    /  \
3   4   5   2

$ NAME=funny ruby trees.rb

Данное дерево не растет в данном лесу.

$ ruby trees.rb

Безымянных деревьев у нас не растет.

```

### Задание (Level 2)

Если вы не передали имя дерево в программу, тогда вы должны показывать все деревья по очереди из нашего леса, отсортировав их по именам. После каждого дерева вы должны запрашивать у пользователя хочет ли он продолжить просмотр или прервать.

Пример работы:

```
awesome_tree.tree

     1
  /     \  
  3      2
/  \    
3   3

Желаете продолжить? [y/n] y


binary_tree.tree

     2
  /     \  
  2      2


Желаете продолжить? [y/n] y

cold_tree.tree

     0
  /     \   
  0      0


Желаете продолжить? [y/n] n

Спасибо что были в нашем лесу

```

### Задание (Level 3)

Теперь после вывода каждого из деревьев вы должны автоматически определять действие, которое нужно выполнить с данным деревом. Чего мы и добивались. 

Критерии действий с деревьями:

1) Если общая сумма всех узлов деревье больше 100, тогда дерево уже старое и необходимо его срубить.

2) Если максимальная глубина дерева больше 5, тогда дерево слишком высокое и необходимо его обрезать

3) Если дерево не очень высокое и не очень старое - то оставить его как есть.

Действие необходимо показывать после каждого действия.

Пример работы:

```
awesome_tree.tree

     1
  /     \  
  3      2
/  \    
3   3

Оставить.

Желаете продолжить? [y/n] y


binary_tree.tree

     2
  /     \  
  2      2

Оставить

Желаете продолжить? [y/n] y

old_tree.tree

     12
  /     \   
70       58

Срубить

Желаете продолжить? [y/n] n

Спасибо что были в нашем лесу
```


2016-2017
=============

# Домашка 1

Необходимо написать калькулятор, который умеется считать в обратной польской нотации. Пример работы калькулятора:

```
# Запускаем нашу программу
./calculator
2
3
+
#=> 5

7
12
14
+
*
#=> 182
```

В базовой версии задания вам нужно реализовать 4 операции: `+`, `-`, `/`, `*` ( сложение, вычитание, деление, умножение ).

В продвинутой версии мы вводим еще одну операцию `!`. Суть операции заключается в том, что она должна обнулять заданное количество единичных бит числа начиная с самого младшего. Данная операция принимает в себя 2 аргумента. Первый аргумент - это число, над котором проводится операция. Второй - количество единичных бит, которое нужно обнулить. Для примера возьмем число 93 ( 01011101 ) в качестве аргумента и 3 в качестве второго аргумент. Это значит начиная с младшего бита нам надо обнулить 3 единицы. То есть 01011101 станет 01010000 или 80.

```
93
3
!
#=> 80
```

# Домашка 2

Необходимо разработать telegram-бота, который бы помогал вам сдавать лабараторные работы в университете вовремя, чтобы вы успешно закончили этот курс.

### Задание ( Level 1 )

Основная задача бота напоминать вам какие предметы и сколько лабораторных работ у вас должно быть сдано к сегодня, чтобы не давать вам расслабляться. Для этого вам предстоит научить его следующим командам: 

* `/start` - выводит приветствие и описание всех доступных команд
* `/semester` - запоминает даты начала и конца семестра
* `/subject` - добавляет предмет и количество лабораторных работ по нему
* `/status` - выводит твой список лаб, которые тебе предстоит сдать
* `/reset` - сбрасывает для пользователя все данные.

В базовом функционале бот на основании введенных вами данных о начале и конце семестра, сегодняшней дате и количеству лаб должен примерно предполагать сколько лабараторных работ вам надо было бы уже сдать.

##### Примеры работы команд:

```
> /start

< Привет. Я тебе смогу помочь сдать все лабы, чтобы мамка не ругалась. Смотри список что я умею:
* /semester - запоминает даты начала и конца семестра
* /subject - добавляет предмет и количество лабораторных работ по нему
*  .....
```

```
> /semester

< Когда начинаем учиться?
> 2016-09-01

< Когда надо сдать все лабы?
> 2016-11-25

> Понял, на все про все у нас 2 месяца и 24 дня.

```

```
> /subject
< Какой предмет учим?
> ОАиП
> Сколько лаб надо сдать?
< 7
> ОК

> /subject
< Какой предмет учим?
> КПиЯП
> Сколько лаб надо сдать?
< 5
> ОК
```

```
> /status

< К этому времени у тебя должно было быть сдано:
> ОАиП - 3 из 7
> КПиЯП - 2 из 5
> 
> Давай поднажмем!
```


### Задание ( Level 2 )

Продвинутый уровень отличается от базового тем, что бот умеет запоминать какие предметы вы сдали. Для этого добавляется команда '/submit', которая так же может быть активирована сообщением 'я сдал'. После активации команды вам приходят все ваши предметы отдельными _кнопками_. В примере кнопку будем показывать через квадратные скобки. После того как вы выбрали кнопкой имя предмета, он вам присылает новые кнопки со всеми номерами оставшихся лаб.

##### Примеры работы команд:

```
> /submit

> Что сдавал?
> [ ОАиП ]
> [ КПиЯП ]
> 
> КПиЯП
> 
> Какая лаба?
> [ 1 ]
> [ 2 ]
> [ 3 ]
> [ 4 ]
> [ 5 ]
> 
> 1
> 
> Красавчег!
```

```
> я сдал

> Что сдавал?
> [ ОАиП ]
> [ КПиЯП ]
> 
> КПиЯП
> 
> Какая лаба?
> [ 2 ]
> [ 3 ]
> [ 4 ]
> [ 5 ]
> 
> 3
> 
> Красавчег!
```

Также меняется немного вид команды `/status`:

```
> /status

< К этому времени у тебя должно было быть сдано:
> ОАиП - 1 2 3 4 5 6 7
> КПиЯП - 2 4 5
> 
> Тебе осталось сдать 10 лаб из 12. Не грусти, лето уже скоро.
```

### Задание ( Level 3 )

В самом продвинутом вариант, ваш бот присылает вам в телеграм по таймеру ( раз в 1 день, раз в 2 дня, раз в неделю по пятницам ) напоминалку со списком всего что у вас не сдано. Если кто-то доберется до этого уровня сложности - пишите в личку для обсуждения.

### Требования для сдачи

* Мы не используем тут никакие фреймворки, только чистый руби и библиотеки ( конкретно нельзя использовать sinatra, padrino, rails и производные ).
* У вас должен быть Gemfile в корне со всеми вашими зависимостями
* Весь код должен быть разбит на классы
* Каждая команда бот - отдельный класс, который наследуется от общего класса
* Бот должен работать для любого пользователя, с кем он заговорит
* Для хранения данных использовать или отдельный файл для каждого пользователя или redis как альтернативу

### Немного технических советов:

Создать телеграмм бота и получить хоть одно сообщение от него. Вообще создание ботов - то еще удовольствие, об этом можно почитать в официальной документации ( https://core.telegram.org/api ). Для имплементации бота настоятельно рекомендую использовать telegram-bot-ruby ( https://github.com/atipugin/telegram-bot-ruby ). Также Юра писал какую-то статью про ботов у нас в блоге, можно почитать и подписаться ( http://blog.rubyroidlabs.com/2016/06/telegram-bot/ ).

Также вам скорее всего понадобится прокидывать порты, для того чтобы ловить вебхуки. Используйте для этого утилиту под названием `ngrok`.

# Домашка 3

Цель данной домашки - познакомиться с синатрой, а также попробовать HTML, CSS и javascript. В рамках этой цели мы будем работать над приложением, в котором пользователи могут совместно писать фразы. Фраза - это набор слов и знаков препинаний, которые вводят пользователи.
Основная идея состоит в том что пользователь не может подряд добавлять более 1 слова. 

Все приложение состоит из 4 страниц

* Страница со списком всех фраз, которая является главной странице приложения
* Страница создания новой фразы
* Страница одной фразы, в которой можно добавлять слова к фразе
* Страница входа/регистрации, где пользователь вводит имя, чтобы приложение его запомнило

С точки зрения взаимодействия это выглядит примерно так:

* Вася зашел на главную страницу, которая пустая, потому что еще никто не начинал новых фраз.
* Вася нажал на кнопку начать новую фразу и попал на страницу создания фразы
* Вася вписав слово "Ночь" в поле для фразы, сохранил и перешел на главную страниц, где стала отображаться его новая фраза.
* Виталик зашел на главную, увидел что есть фраза "Ночь" от Васи, кликнул на нее и добавил слово "режет", после чего был перенаправлен на главную страницу.
* На главной Виталик захотел добавить еще слово, зашел на страницу добавления слова, но система не дала возможности добавлять слово и попросила подождать очереди.
* Вася увидел что теперь он может добавить еще слово к своей фразе и дописал "глаза", получил "Ночь режет глаза".
* Зашла Оля, увидела что ночь режет глаза и добавила "безнопилой", теперь получилось "Ночь режет глаза бензопилой".
* повторять_пока опустить_перо стенка_слева (~~лайк, если понял о чем я~~), т.е. и так далее


### Уровень 1

На первом уровень вам нужно просто сделать страницу со списком фраз и кнопкой добавления новой фразы. Каждая фраза должна быть подсвечена определенным образом, чтобы было понятно можете вы ее продлить или нет. По клику на фразу вы переходите на страницу с добавлением. Если система не смогла определить что вы за пользователь - она перенаправляет вас на страницу, где вы можете написать ваше имя, после чего приложение вас запомнит. Добавив слово к фразе, вас должно перенаправить на страницу со всеми фразами и показать сообщение, что фраза обновлена успешно. Важно что вместе со словом, также можно ставить 1 любой знак препинания кроме точки.

### Уровень 2

На данном уровне предлагается на странице с редактированием показывать всю историю изменения фразы о самого начала, то есть кто ее создал и кто какие слова добавил. Добавленное слово должно выделяться курсивом. Примерно так:

"Ночь режет глаза безопилой"

- Оля ( 2016-11-11 12:37 ): "Ночь режет глаза __бензопилой__"
- Вася ( 2016-11-11 12:35 ): "Ночь режет __глаза__"
- Виталик ( 2016-11-11 12:33 ): "Ночь __режет__"
- Вася ( 2016-11-11 12:32 ): "Ночь"

Также появляется возможно редактировать все фразы не на отдельной странице, а на странице со списком всех фраз. Обновление должно происходить асинхронно, для этого нужно использовать jQuery и Ajax.

### Уровень 3

На странице редактирования всех фраз нужно использовать websockets для того,  чтобы получить измененные фразы с сервера и сразу их показывать на странице со всеми фразами. 

### Технические требования

* Sinatra с любыми количеством клевых и модных гемов.
* Для идентификации пользователей все нужно хранить в сесии пользователя, читай использовать сookies.
* Для красивого интерфейса использовать CSS фреймворк bootstrap ( http://getbootstrap.com/ )
* В качестве хранилища данных можно использовать что угодно ( redis/postgresql/файлы )
* Если соберетесь делать javascript - использовать jquery.


2015-216
=============

# Домашка 1

Необходимо написать некоторое подобие утилиты `sl`. Для того чтобы иметь представление что делает данная утилита, для ubuntu можно поставить ее через `sudo apt-get install sl` и после завершения установки написать в терминале `sl`. Если вы упали со стула потому что на вас поехал паровоз - вы на правильном пути.

В данном домашнем задании мы не ограничиваем вас только поездом, в общем случае это должна быть какая-то ASCII-картинка которая будет как-то дергаться.

# Домашка 2.1

Необходимо написать утилиту `gemfiler`, которая будет показывать отфильтрованные версии гемов. 

Входные параметры: 
* Имя gem'а
* Указание версий в формате, совместимом с Gemfile

Вывод на консоль:
* Все версии данной библиотеки, при этом красным цветом подсвечиваются отфильтрованные версии.

Требования:
* Утилита должна парсить входные параметры с использованием существующих библиотек.
* Все версии gem'ов должны браться путем парсинга страницы или через взаимодействите с rubygems API
* Утилита должна быть поделена на независимые модули, каждый должен быть представлен отдельным классом.
* Правильная обработка потока ошибок.

Примеры:
```
./gemfiler devise '~> 2.1.3'
./gemfiler rails '>= 3.1'
./gemfiler rails '>= 3.1' '< 4.0'
```

# Домашка 2.2

Создаем убийцу `grep`. Для тех кто не знает что это такое - советую пойти поиграться в консоль с этой утилитой. Если кратко - то это утилита для поиска строк, содержащих текст в файлах. Атомарной единицей для этой утилиты является строка. То есть при поиске если вы находите в строке искомый текст - она выдает вам обратно в STDOUT строку.

Если вы зайдете в мануал то увидите что формат команды примерно такой:

```
	grep [options] PATTERN [FILE...]
	grep [options] [-e PATTERN | -f FILE] [FILE...]
```

Первый формат означает что в команду сперва передаются опции, затем какой-то текст для поиска в файле и затем 1 или несколько файлов. Второй формат примерное такой же, но использует регулярные выражения для поиска по файлам.

## Требования

В результате домашнего задания вам нужно написать утилиту grep с несколько ограниченным функционалом. 
Необходимые опции которые вам надо реализовать:

* `-A` - опция которая выводит количество строк до и после найденной строки
* `-e` - опция которая позволяет вводить регулярные выражения вместо просто части строки
* `-R` - опция которая говорит искать строку не в одном файле, а рекурсивно во всех файлах в папке
* `-z` - опция указывающая что файлик является сжатым и сначала его надо разжать и только потом искать по нему. 
 
## Немного примеров

Для примера будем использовать файлик 1.txt со следующим содержанием:

```
aa
bb
cc
abc
bcd
cde
ggg
```

Результаты выполнения:

```
grep a 1.txt 
=> aa
=> abc
```


```
grep -A 1 ab 1.txt 
=> cc
=> abc
=> bcd
```

```
grep -A 1 b 1.txt 
=> aa
=> bb
=> cc
=> cc
=> abc
=> bcd
=> abc
=> bcd
=> cde
```


```
grep -e "a[^b]" 1.txt 
=> aa
```

## Этапы

Для того чтобы вы сразу не писали огромную утилиту разобьем ее имплементацию на несколько этапов:

* Сделайте утилиту которая просто без опций находит строки в файле.
* Добавьте возможность искать по нескольким файлам, aka `grep a 1.txt 2.txt`
* Добавьте опцию `-A` которая выводит соседние строки.
* Добавьте опцию `-e` которая ищет по регуляркам
* Добавьте опцию `-R` которая будет искать по всем файлам в папке
* Добавьте опцию `-z` которая будет искать по сжатому через gzip файлу


## Проверка

Задания принимаются __только__ ввиде ссылки на гитхаб.

# Домашка 3

Необходимо написать консольное приложение, которое позволяет посмотреть отзывы о преподователях БГУИР в этом семестре по номеру учебной группы. Выводить отзывы на преподавателей разными цветами, в зависимости от настроения отзыва. Хороший - зеленым цветом, плохой - красными цветом, нейтральный - белым. Настроение отзыва определять по ключевым словам, которые загружаются из YAML файла `keywords.yml` в корне программы.
Список преподавателей для конкретной группы необходимо получать с сайта `http://www.bsuir.by/schedule/schedule.xhtml`. Отзывы о преподавателях брать с сайта `http://bsuir-helper.ru/`. 

## Пример работы программы
```ruby
./bsuir-reviews 250501

Третьяков А. Г.
=====
Не найдено отзывов

Смирнов И. В.
=====
01/12/2014 - 17:49: Вёл ЭПр. Впринципе мужык довольно неплохой, хоть и странноватый немного. Автоматы ставит от 7-ми баллов, на экзамене для сдачи надо написать 2 вопроса и желательно решить задачу, хотябы в общем виде, чтобы небыло проблем. Дополнительные вопросы обычно задаёт по билету. Оценка на экзамене зависит от рекомендованой, если ответил хорошо - это + 1 балл к заходной. Сложность списывания зависит от того, когда сдаётся экзамен, если в начале сессии то вполне можно спалится, если уж слишком явно это делать, а в конце или тем более на пересдаче никаких проблем, пересдач обычно очень мало, да и если уже будет, сдать потом не особо проблематично.

Самаль Д. И.
=====
06/07/2014 - 23:38: Отличный преподаватель и замечательный человек ! Заменял у нас лекции по дисциплине "Алгоритмы компьютерной графики"(ПОИТ,2 курс). Отлично рассказывает материал не оторваны от реальности,с красочными примера и пояснениями. У него работает система бонусов - за ответы на лекциях и активное участие, как для нормальных студентов, так и для "галерки" :) В конце семестра подводит процентовку успеваемости, по итогам которой относит нашего брата к той или иной категории : 1)Automat 2)Зачет Light 3)Зачет Hard 4)Dead :D P.S.Помимо этого рассказал очень полезную информацию, касающуюся не только учебы , а жизни в целом ;)

10/12/2012 - 15:50: Самаль оставил после себя очень хорошее впечатление, МГ и СИФО предметы не из легких конечно, и требовал он чтобы все работало и правильно, 4 раза до 30 декабря одну лабу носили, ну не могли сделать правильно, но злости после себя не оставляет. Начинать собирать курсач из кусков реально лучше хотя бы за недели 3, тогда из кусков + готовых можно легко склепать нормальный вариант. По курсачу треть где-то тоже не успела сдать до сессии. По СИФО лучше стараться вытащить на контрольных автомат хотя бы 4, автоматов будет большинство. Если на экзамене не можешь ответить - только в следующий раз, прошарившись; билет тот же.
```

## Формат файла с ключевыми словами

```yml
negative:
  - плохой
  - скучный

positive:
  - хороший
  - мировой
  - великолепный
```

##  Требования
* Для парсинга обоих сайтов использовать гем `mechanize`. 
* Для вывода текста цветом использовать гем `colorize`
* Слова грузить из YAML файла, следуя формату выше
* Обязательно разбить все на разные классы
* Иметь опцию '-h', которая выводит подсказку для использования программы. Также выводить ее если не передано никаких аргументов в программу
* Иметь `Gemfile`, в котором будет список всех использованных вами гемов
* Предусмотреть ситуации когда у вас не будет интернета и утилита не заработает (обработка ошибок)

## Задание со звездочкой

Вместо сочинения файла keywords.yml можно придумать систему, которая бы брала эти слова из самих отзывов (достаточно напарсить все отзывы и взять 20+ самых популярных слов). Или найти какие-нибудь решения, которые анализируют текст на негативность. 
