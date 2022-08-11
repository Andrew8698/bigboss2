# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
**Git** - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.

## Git version

Прежде чем создавать репозиторий и инициализировать Git, проверим текущую установленную версию пограммы. Необходимо выполнить команду *git version*.

## Подготовка репозитория
Для создания репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создадится репозиторий (появится скрытая папка .git).

## Команда ls -a
С помощью данной команды можно убедиться, что наша скрытая папка **.git** существует.


## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*. Для того, чтобы сохранить все файлы сразу, используйте *git add .*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

Есть более быстрый способ создания коммитов. Команда *git commit -am "<сообщение к коммиту>*. Она сочетает в себе команды *git add* и *git commit -m*.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с репозиторием следующим образом: *git checkout <номер коммита>*.

Команда так же позволяет перемещаться между ветками: вместо номера коммита указываем название ветки. А чтобы вернуться в ветку master, вызываем команду *git checkout master*.



## Журнал изменений
Для того, чтобы посмотреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием.

Когда создаем ветки, то удобно пользоваться командой *git log --graph*. Она выводит журнал изменений в виде витвлений и позволяет наблюдать все изменеия на всех существующих ветках. Чтобы отследить точную последовательность коммитов, то команда *git log --oneline* поможет нам с этим.

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git branch*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*. Для отслеживания, на какой ветке мы работаем, используется просто *git branch*. При вызове этой команды высвечиваются все ветки и подсвечивается название ветки, на которой мы находимся.

Чтобы создать и сразу перейти на ветку, выполним команду *git checkout -b <название новой ветки>*.

### Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <название  ветки>*.

В случае возникновения конфликта между версиями строк, можно воспользоваться командой *git merge --abort*. Она отменяет слияние и возвращает нас к состоянию до слияния.

### Удаление веток
Для удаления ветки ввести команду *git branch -d <название  ветки>*.

## Отслеживание изменений

Для того, чтобы увидеть, какие изменения произошли между коммитами, вызываем команду *git diff*. Она показывает сколько строк было удалено, добавлено или изменено.

## Работа с удаленными репозиториями

### git clone
Копировать внешний репозиторий на свой ПК можно командой *git clone [ссылка]*.

Команда git clone составная: она не только
загружает все изменения, но и пытается слить 
все ветки на локальном компьютере и в
удаленном репозитории.

### git pull

Эта команда позволяет скачать все 
из текущего репозитория и автоматически
сделать merge с нашей версией.

### git push

Отправить свою версию репозитория во
внешний репозиторий поможет команда git
push. При первом её использовании **нужна авторизация**.

## Как настроить совместную работу

1. Создать аккаунт на [GitHub.com](http://github.com/)

2. Создать локальный репозиторий

3. “Подружить” ваш локальный и удалённый репозитории.GitHub при создании нового репозитория подскажет, как это можно сделать

4. Отправить (push) ваш локальный репозиторий в удалённый (на GitHub), при этом, возможно, 
вам нужно будет авторизоваться на удалённом репозитории

5. Провести изменения “с другого компьютера”

6. Выкачать (pull) актуальное состояние из удалённого репозитория

## pull request


➜ команда для предложения изменений

➜ запрос на вливание изменений в репозитор

В больших компаниях один ответственный за проект создает аккаунт. Другие пользователи дают команду pull request. Предлагать изменения на GitHub нужно в отдельной ветке. Сначала
пользователь копирует репозиторий на свой компьютер, делает fork репозитория, затем
клонирует версию на своём ПК, создаёт ветку с предлагаемыми изменениями, отправляет
изменения командой push в свой аккаунт на GitHub и даёт команду pull request.

**Как сделать pull request**

- Делаем   (ответвление) репозитория fork
- Делаем git clone   версии репозитория СВОЕЙ
- Создаем новую ветку и в НЕЕ вносим свои изменения
- Фиксируем изменения (делаем коммиты)
- Отправляем свою версию в свой GitHub
- На сайте GitHub нажимаем кнопку pull request

## Дополнительная информация

Более подробно ознакомиться с Git можно в источниках. Ссылки: 
1. https://git-scm.com/book/ru/v2
2. https://www.atlassian.com/ru/git/tutorials/learn-git-with-bitbucket-cloud



Ты сильно устал, твоим глазам нужно отдохнуть. Выполни гимнастику.
![Гимнастика для глаз](Гимнастика.png)

## Немного мудрого

>"Успех не случайность. Это тяжелая работа, настойчивость, обучение, изучение, жертвоприношение и прежде всего, любовь, к тому что вы делаете или учитесь делать."
>
>Пеле