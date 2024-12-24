## Лабораторная работа X: команда `grep`
`grep` — это мощный инструмент для поиска строк в текстовых файлах на основе шаблона. 
Он поддерживает регулярные выражения и множество полезных опций, позволяя фильтровать и анализировать текстовые данные.

### Разминка
Необходимо потренироваться в использовании следующих опций (можно использовать готовые файлы `data*.txt`):

`-w` - искать шаблон как слово, отделенное пробелами или другими знаками препинания;

`-x` - искать шаблон как целую строку, от начала и до символа перевода строки;

`-i` - не учитывать регистр символов;

`-v` - вывести только те строки, в которых шаблон поиска не найден;

`-n` - вывести также номера строк, в которой был найден шаблон;

`-c` - вывести количество найденных строк;

`-m` - остановить поиск после того как будет найдено указанное количество строк;

`-r` - рекурсивный поиск по всем подпапкам;

`-o` - отображать только совпавшую часть, вместо отображения всей строки;

`-e` - альтернативный способ указать шаблон поиска, опцию можно использовать несколько раз, что позволяет указать несколько шаблонов для поиска файлов, содержащих хотя бы один из них;

`--include="*"` - позволяет искать только в определенных файлах;

`--exclude="*"` - позволяет не искать в определенных файла;

Например, выведем количество строк файла `data/data_wolf.txt`, в которых встречается "волк" или "когда":
```bash
cd InformaticsCustomLab/
grep -wc -e "когда" -e "волк" data/data_wolf.txt
>>> 16
```

Найдем во всех `data*.txt` файлах репозитория строки, содержащие "человек" (без учета регистра), выведем также номера этих строк в файле:
```bash
grep -rin --include="data*.txt" "человек" 
>>> InformaticsCustomLab/data/data_wolf.txt:26:Жизнь волка не легка, а жизнь человека запутана.
>>> InformaticsCustomLab/data/data_memes.txt:12:Тут был хороший борщ, с капусткой, но не красный. Так… Сосисочки. Еще есть какой-то непонятный салат, куда крошат морковку, капусту и яблоки с ананасами – вообще, он меня бесит. Еще че… Вкусный чай. Он так утоляет жажду, я чувствую себя человеком! Все.
```

Выведем первые 5 строк файла `data/data_wolf.txt`, которые не содержат слова "волк" (учитывая регистр) 
```bash
grep -v -m 5 "волк" data/data_wolf.txt
>>> Волки редко примиряются с постигшим их унижением – они просто забывают о нем.
>>> Волки – это люди, выбравшие свободу.
>>> Волк чужого не ищет. Волк довольствуется своим!
>>> Легко вставать, когда ты не ложился.
>>> Бегать за овцами — удел баранов. Я бегаю только за пивом.
```

### Задания

#### Регулярные выражения 

#### Пайплайны + `grep` = 

### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается: `"Use this template"` ⇒ `"Create a new repository"` (сделайте его `public`). 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы. Скриншотов не жалейте, они бесплатные)

#### Темы для защиты:
  - Основные опции команды `grep`.
  - Работа с регулярными выражениями: символы, диапазоны, логические операторы.
  - Пайплайны и использование `grep` в связке с другими командами (`sort`, `uniq`, `wc`).
  - Контекстный вывод результатов и поиск по нескольким шаблонам.

### Дополнительные источники

► [Ресурс](https://www.google.ru/), где можно найти (почти) всё
