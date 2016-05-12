## Домашнее задание ко второй лекции

1\. Генератор статей

В файле [articles_generator.py](/static/bmstu_py/data/articles_generator.py) есть функции `generate_title` и `generate_article`, которые генерируют заголовок и текст статьи с заданной темой при помощи [Яндекс.Рефератов](https://vesna.yandex.ru/referats/).

Нужно при помощи этих функций сгенерировать 100 статей для блога (см. задачу 6 практикума на лекции 1). На выходе - файл articles.json с сотней статей (у статьи должны быть поля title, text, author).

Статьи должны генерироваться при выполнении команды `python articles_generator.py`.

2\. Пагинированный вывод статей

Научиться выводить статьи в консоль и html-файл (как в задачах 6 и 7 практикума), но не все, а частями.

Функция output_articles вывода должна принимать на вход способ вывода статьи (консоль/путь к файлу), номер страницы и количество статей на одной странице.

Например, при выводе 6й страницы по 4 статьи должны быть выведены статьи 21-24.

3\. Поиск по статьям

Реализовать функцию `find_articles`, которая принимает на вход поисковый запрос и список статей, а возвращает только те статьи, которые содержат в названии поисковый запрос.

Опционально - добавить возможность расширенного поиска, в таком случае возвращаться будут статьи, в которые поисковый запрос содержится в названии или тексте.

4\. Сортировка файлов по размеру

Команда `ls -lah /` показывает список файлов и каталогов в корневой директории с указанием разных параметров (например, прав доступа и размера файла).

Вообще, команда `ls` умеет много всего, о всех возможностях можно почитать, выполнив `man ls`.

Если в Python выполнить следующий код:

<div>`import subprocess`</div>

<div>`raw_ls_data = subprocess.check_output(['ls', '-la', '/'])`</div>

то в переменной `raw_ls_data` будет строка, содержащая тот же текст, что выводится в результате работы `ls -la` в консоли.

Задача: вывести список файлов (только файлов, без директорий), отсортированных по размеру.

HINT: определителем того, является ли объект директорией, служит самый первый символ в строке. Для обработки строк стоит активно использовать метод [split](https://docs.python.org/2/library/stdtypes.html#str.split).

Опционально: сделать путь до исследуемой директории параметром функции.

NOTE: это учебная задача. На самом деле задача нахождения самых больших/маленьких файлов решается другими способами.

5\. Валидация пароля

Написать функцию, которая принимает на вход пароль и возвращает True или False в зависимости от того, удовлетворяет ли он необходимым требованиям.

Требования такие: в нём должны быть хотя бы одна строчная буква, хотя бы одна заглавная, хотя бы одна цифра и хотя бы один служебный символ; минимальная длина - 8 символов.

6\. Исследование данных

В файле [technical_education_moscow.json](/static/bmstu_py/data/technical_education_moscow.json) содержится данные о учебных заведениях Москвы научно-технического направления (данные взяты с [http://data.mos.ru/](http://data.mos.ru/)).

Для каждого заведения известны несколько параметров, в том числе район города, в котором это заведение находится.

Нужно вывести пятёрку районов, в которых больше всего учебных заведений.

