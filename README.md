# Java_OOP <img src="https://github.com/blackcater/blackcater/raw/main/images/Hi.gif" height="32"/>

<h3>Владимир Бурусов</h3>
<h4>КН-201</h4>

<div align="center">

# ROBOT 🤖

​​​​​​ [![Button](https://user-images.githubusercontent.com/80776324/234415221-021db78d-8949-4da8-bf54-f9ae21628d41.png)](https://github.com/Naberno/Java_OOP_2/fork) [![Discord](https://user-images.githubusercontent.com/80776324/234414710-496d8ec0-992f-409e-a0c7-bf70df85d948.png)](https://discord.gg/rRAqRDVHcc)

</div>

# 📌 Меню

- [<kbd>Описание</kbd>](#-описание)
- [<kbd>Как запустить</kbd>](#-как-запустить)
- [<kbd>Задание 5</kbd>](#-задание-5)
- [<kbd>Задание 4</kbd>](#-задание-4)
- [<kbd>Задание 3</kbd>](#-задание-3)
- [<kbd>Задание 2</kbd>](#-задание-2)
- [<kbd>Задание 1</kbd>](#-задание-1)



`Возможности`
* Какие-то будут

# 📌 Описание

Это приложение написанное на Java 

# 📌 Как запустить

1. Напиши в консоль:
```
git clone https://github.com/Naberno/Java_OOP_2.git
```
2. Запустить файл RobotsProgram.java

# 📌 Задание 5

Сделать так, чтобы приложение было локализовано (то есть обеспечить
возможность выбора языка, на котором работает пользовательский интерфейс).
Для упрощения задачи можно сделать следующие допущения:
- Локализацию проводим только для собственных компонент программы
  (сообщения в готовых диалогах Swing переводить не нужно);
- Считаем, что должны поддерживаться два языка: русский (выводится в
  обычном русском алфавите) и транслит (русский язык, выводимый латинницей).

# 📌 Задание 4

Придумать и реализовать структуру данных для хранения записей,
отображаемых в окне протоколирования. В исходной версии кода в качестве
такой структуры использован ArrayList без какой-либо самоочистки. В
реальности же обычно требуется, чтобы размер хранимой (и отображаемой в  
окне) части протокола был ограничен. Но если просто удалять из ArrayList
старые записи, это приведет к неэффективной реализации (добавление записи
будет работать за O(N), поскольку придется удалять устаревшие записи из
начала структуры) и к проблемам с конкурентным доступом (возникает
состояние гонки между добавлением данных и итерированием существующих).

Соответственно, структура для хранения протокола должна обладать
следующими свойствами:

- Имела ограниченный размер (старые записи вытесняются)
- Должна быть потокобезопасной (запись и чтение порождают состояние гонки)
- Должна быть возможность доступа к части данных (сегмент смежных записей)
  по индексам начала и конца (такая операция, по идее, нужна для
  эффективного отображения данных в окне, чтобы не читать полный лог)

- Добавление данных (с потенциальным удалением старых) и чтение уже
  хранящихся должны быть быстрыми (т.е. никаких O(n))
- Должна возвращать потокобезопасный итератор (то есть добавление данных
  во время итерирования не должно разрушать итератор)

Первые 3 пункта могут быть реализованы на любой структуре (стэк, очередь,
массив), но потребуется сделать структуру потокобезопасной (конкурентные
чтение и запись).

Последние 2 пункта - усложненная версия задачи, позволяющая
познакомиться, например, с темпоральными структурами данных.

# 📌 Задание 3

- Реализовать новое окно (например, на основе диалоговых компонент), в
  котором будут отображаться текущие координаты робота
- Для этого придется разделить логику отображения робота
  (визуализацию) и модель робота (код получения координат и
  моделирования движения)
- Модель нужно будет описать как обозреваемый объект (Observable),
  чтобы затем окно могло подписаться на уведомления от модели и
  обновлять свое состояние
- С использованием этого нового окна и/или окна протоколирования нужно
  исправить ошибку в логике управления роботом (сейчас при определенном
  взаимном расположении робота и целевой точки робот уходит в
  противоположном направлении).

# 📌 Задание 2

- В методе выхода из приложения нужно сохранить (в файл) положения окошек
  (положение на экране, развернутое/свернутое состояние)
- При запуске приложения следует восстановить геометрию окошек приложения
  (положение на экране, развернутое/свернутое состояние)

# 📌 Задание 1

- Требуется добавить пункт меню, позвлояющий закрыть приложение
- Требуется собрать обработку события выхода из приложения в один метод
  и сделать так, чтобы в этом методе выдавался запрос на подтверждение
  выхода (см. класс JOptionPane)

Дополнительное задание:
- Сделать так, чтобы диалог на основе JOptionPane выдавал текст на кнопках
  на русском языке.
