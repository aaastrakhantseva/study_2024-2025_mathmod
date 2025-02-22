---
## Front matter
lang: ru-RU
title: "Лабораторная работа №1"
subtitle: "Работа с git"
author: 
  - Астраханцева А. А.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 февраля 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Астраханцева Анастасия Александровна
  * НФИбд-01-22, 1132226437
  * Российский университет дружбы народов
  * [1132226437@pfur.ru](mailto:1132226437@pfur.ru)
  * <https://github.com/aaastrakhantseva>

:::
::: {.column width="30%"}

![](./image/nastya.jpg)

:::
::::::::::::::

# Вводная часть

## Цели лабораторной работы

Приобретение навыков работы с git и markdown.

# Выполнение ЛР

## Подготовка

![Параметры установки окончаний строк](image/1.jpg){#fig:001 width=70%}

##  Создание проекта

```
mkdir hello
cd hello
touch hello.html
echo "Hello, World!" > hello.html
```

##  Создание проекта
```
git init
git add hello.html
git commit -m "Initial Commit"
git status
```
##  Создание проекта

![Создание файла, репозитория и добавление файлов в репозиторий](image/2.jpg){#fig:002 width=70%}

## Внесение изменений 

```
<h1>Hello, World!</h1>
```
Проверим состояние рабочего каталога.
```
git status
git add hello.html
git status
```
## Внесение изменений 

![Изменение файла, создание комита](image/3.jpg){#fig:003 width=70%}

## Создание коммита
```
git commit
git status
```

## Изменим файл hello.html

```
<html>
<body>
<h1>Hello, World!</h1>
</body>
</html>
```
```
git add hello.html
```

## Изменение файл hello.html

```
<html>
<head>
</head>
<body>
<h1>Hello, World!</h1>
</body>
</html>
```

```
git status
```
## Просмотр состояния

![Изменение файла и создание коммита](image/4.jpg){#fig:004 width=70%}

## Просмотр истории

![Просмотр истории](image/5.jpg){#fig:005 width=70%}

## Просмотр истории

![Варианты просмотра лога](image/6.jpg){#fig:006 width=70%}

## Возврат к определенной версии репозитория

![Возвращение к версии репозитория используя хэш](image/7.jpg){#fig:007 width=70%}

##  Создание тэгов и переключение по ним

![Создание тэгов и переключение по ним](image/8.jpg){#fig:008 width=70%}

##  Создание тэгов и переключение по ним

![Переключение по тэгам](image/9.jpg){#fig:009 width=70%}

##  Создание тэгов в логе

![Имена тэгов в логе](image/10.jpg){#fig:010 width=70%}

## Изменение файл hello.html

```
<html>
<head>
</head>
<body>
<h1>Hello, World!</h1>
<!-- This is a bad comment. We want to revert it. -->
</body>
</html>
```

## Проверим состояние рабочего каталога:

```
git status
git checkout hello.html
git status
cat hello.html
```
## Изменение файл hello.html

```
<html>
<head>
<!-- This is an unwanted but staged comment -->
</head>
<body>
<h1>Hello, World!</h1>
</body>
</html>
```

## Индексация и отмена индексации

```
git add hello.html
git status
```
```
git reset HEAD hello.html
```

## Индексация и отмена индексации

![Отмена индексации файла](image/11.jpg){#fig:011 width=70%}

Переключимся на версию коммита: 
```
git checkout hello.html
git status
```

## Изменение файл hello.html

```
<html>
<head>
</head>
<body>
<h1>Hello, World!</h1>
<!-- This is an unwanted but committed change -->
</body>
</html>
```

## Отмена коммита

```
git add hello.html
git commit -m "Oops, we didn't want this commit"
```
```
git revert HEAD
```
## Отмена коммита

![Отмена коммитов](image/12.jpg){#fig:012 width=70%}

## Удаление коммитов из ветки
 
```
git log
git tag oops
git reset --hard v1
git log
```

## Удаление коммитов из ветки

![Удаление коммитов](image/13.jpg){#fig:013 width=70%}

##  Удаление тега 

```
git tag -d oops
git log --all
```
##  Удаление тега 

![Удаление тэга](image/14.jpg){#fig:014 width=70%}

## Внесение изменений в коммиты
 
```
git add hello.html
git commit --amend -m "Add an author/email comment"
```

## Внесение изменений в коммиты

![Изменение коммита](image/15.jpg){#fig:015 width=70%}

## Перемещение файлов

```
mkdir lib
git mv hello.html lib
git status
git commit -m "Moved hello.html to lib"
```
## Добавление файла index.html в репозиторий
```
<html>
<body>
<iframe src="lib/hello.html" width="200" height="200" />
</body>
</html>
```
## Перемещение файлов

![Перемещение файла средствами git](image/16.jpg){#fig:016 width=70%}

## Git внутри: Каталог .git

![Структура git](image/17.jpg){#fig:017 width=70%}

## Работа непосредственно с объектами git 

![Содержание git/HEAD](image/18.jpg){#fig:018 width=70%}

## Работа непосредственно с объектами git 

![Работа с объектами git](image/19.jpg){#fig:019 width=70%}

## Работа непосредственно с объектами git 

![Работа с объектами git](image/21.jpg){#fig:020 width=70%}

##  Создание ветки 

![Создание ветки, редактирование файлов](image/22.jpg){#fig:021 width=70%}

##  Просмотр лога

![Просмотр лога](image/23.jpg){#fig:022 width=70%}

##  Создание отличий в ветках

![Создание отличий в ветках](image/24.jpg){#fig:023 width=70%}

##  Просмотр графа

![Просмотр графа](image/25.jpg){#fig:024 width=70%}

## Слияние 

![Просмотр графа](image/28.jpg){#fig:025 width=70%}

## Сброс ветки 

![Сброс ветки](image/32.jpg){#fig:026 width=70%}

## Перебазирование 

![Перебазирование](image/33.jpg){#fig:027 width=70%}

## Клонирование репозиториев


![Клонирование репозитория](image/35.jpg){#fig:028 width=70%}

## Просмотр истории репозитория

![История репозитория](image/36.jpg){#fig:029 width=70%}

## Что такое origin?

![Origin](image/37.jpg){#fig:030 width=70%}

## Извлечение изменений 

![Извлечение изменений](image/40.jpg){#fig:031 width=70%}

## . Слияние извлеченных изменений

![Различные команды git](image/43.jpg){#fig:032 width=70%}

23. Отправка изменений 

![Различные команды git](image/44.jpg){#fig:032 width=70%}


# Выводы

В ходе выполнения лабораторной работы я приобрела навыки работы с git и markdown.



# Спасибо за внимание!
