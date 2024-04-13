# Домашнее задание к занятию «Инструменты Git»

Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде.

Инструкция к заданию
1. Склонируйте репозиторий с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.

### Задание

В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

git show aefea

commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/1.jpg)

2. Ответьте на вопросы.

* Какому тегу соответствует коммит 85024d3?

git show 85024d3

tag: v0.12.23

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/2.jpg)

* Сколько родителей у коммита b8d720? Напишите их хеши.

git show b8d720

Merge: 56cd7859e0 9ea88f22fc

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/3.jpg)

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.

git show v0.12.23

git show v0.12.24

git log --since="2020-03-05T20:56:10-07:00" --until "2020-03-19T15:04:05-07:00" --pretty=format:"%h - %cd - %s"

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/4.jpg)

* Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так: func providerSource(...) (вместо троеточия перечислены аргументы).

git grep --p "func providerSource"

git log -S "func providerSource(configs" --pretty=format:"%h - %an - %ad"

5af1e6234a - Martin Atkins - Tue Apr 21 16:28:59 2020 -0700

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/5.jpg)

* Найдите все коммиты, в которых была изменена функция globalPluginDirs.

git log -S globalPluginDirs --oneline
65c4ba7363 Remove terraform binary
125eb51dc4 Remove accidentally-committed binary
22c121df86 Bump compatibility version to 1.3.0 for terraform core release (#30988)
7c7e5d8f0a Don't show data while input if sensitive
35a058fb3d main: configure credentials from the CLI config file
c0b1761096 prevent log output during init
8364383c35 Push plugin discovery down into command package

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/6.jpg)

* Кто автор функции synchronizedWriters?

git log -S synchronizedWriters --pretty=format:"%h - %an - %ad"

5ac311e2a9 - Martin Atkins - Wed May 3 16:25:41 2017 -0700

![alt text](https://github.com/MaratKN/git-04-tools/blob/main/7.jpg)

В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.