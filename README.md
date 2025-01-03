# Лабораторная работа

### ФИО: Нгуен Динь Нам - К3140

### Тема: Команда grep

---

Для решения понадобится установить VirtualBox или другие аналоги.

Команда `grep` в Linux (**_Global Regular Expression Print_**) — это утилита, предназначенная для поиска заданного шаблона или регулярного выражения в текстовых файлах и вывода всех строк, в которых был найден соответствующий фрагмент.

## Разминка

1. Создайте 3 файла, содержащих следующий текст:

```
echo -e "This is file one.\nError detected here.\nNo issues found." > file1.txt
echo -e "Another file.\nSome warnings.\nCritical error on line 3.\nFile corruption detected." > file2.txt
echo -e "Logs:\nNo errors.\nError found again.\nPermissions updated." > file3.txt
```

2. Создайте новый файл с именем `script.bash`:

```
    touch script.bash
```

3. Откройте созданный файл `script.bash` для редактирования.

```
    gedit script.bash
```

4.  Добавьте код в скрипт:

```
#!/bin/bash

for file in *.txt
do
    echo "Searching in $file:"
    grep -i "error" "$file"
    echo ""
done

```
- Просмотреть все файлы с расширением txt в текущем каталоге.
- Используйте команду `echo` для вывода текущего просматриваемого файла и команду `grep` для поиска «error» в этом файле.
- Параметр `-i` в grep используется для поиска строк в файле независимо от регистра.
5. Сохраните файл. Закройте текстовый редактор `gedit`. Запустите bash-скрипт, выполнив в терминале

```
bash script.bash
```

6.  Скрипт выполнит поиск слова «error» во всех текстовых файлах в текущем каталоге и выведет на терминал следующее:

```
Searching in file1.txt:
Error detected here.

Searching in file2.txt:
Critial error on line 3.

Searching in file3.txt:
NO errors.
Error found again.
```

## Задание лабораторной работы - Анализ и статистика системных журналов

1. Клонировать репозиторий с GitHub.

- Сначала нужно клонировать репозиторий, содержащий файл syslogs.txt

```
git clone https://github.com/namloga/Informatic-lab
```

2. После завершения клонирования перейдите в директорию репозитория:

```
cd Informatic-lab
```

3. Скопируйте файл `syslogs.txt` в рабочую папку с помощью команды `cp`.

```
cp syslogs.txt /PATH/
```

_Файл `syslogs.txt` содержит информацию об ***ошибках*** и ***важных событиях*** с 20 по 23 декабря 2024 г._

<br>
Необходимо проанализировать системный журнал, содержащий информацию об ошибках и важных событиях в файле <code>syslogs.txt</code>. После анализа нужно выполнить несколько автоматических действий:

<br>

- Подсчитайте количество ошибок(Большие буквы): WARNING, ERROR за день.
- Вывести дни, в которых **_Disk error_** (не учитывая регистр) возникала 3 или более раз с 20 по 23 декабря 2024 г.
- Создание отчета с статистикой ошибок и событий по уровню важности (INFO, WARNING, ERROR). (Записать в файл `log_report.txt`)

## Дополнительные источники

1. [man-страница для команды grep.](https://man7.org/linux/man-pages/man1/grep.1.html)
2. [Использование grep в блоках кода и параметрах grep.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#GREPREF)
3. [Учебник по uniq.](https://losst.pro/komanda-uniq-linux)
4. [Учебник по date.](https://losst.pro/komanda-date-v-linux)
5. [Проверка условий.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#TESTS)
6. [Циклы.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#LOOPS1)
7. [Использование трубы](https://www.geeksforgeeks.org/piping-in-unix-or-linux/)
8. stackoverflow.com
