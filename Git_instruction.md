![Logo](logo.png)
 # Работа с Git

 ## 1. Проверка наличия установленного Git
В терминале выполнить команду `git version`.

Если Git установлен, появится сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.

## 2. Установка Git
Загружаем последнюю версию Git с сайта
https://git-scm.com/downloads
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git 
При первом использовании Git необходимо представится. Для этого нужно ввести в терминале две команды:
```
git config --global user.name "Имя пользователя"
git config --global user.email "почта@pochta.com"
```

## 4. Инициализация репозитория 
Получить репозиторий можно двумя способами.
1. Чтобы создать новый репозиторий, нам нужно создать папку и выполнить команду: 
```
git init
```
2. Клонировать существующий репозиторий Git из любого места. Сделать это можно так:
```
git clone <адрес репозитория>
```

## 5. Запись изменений в репозиторий
Основной инструмент, используемый для определения, какие файлы в каком состоянии находятся это команда `git status`. Если вы выполните эту команду сразу после клонирования, вы увидите что-то вроде этого:
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```
Это означает, что у вас чистый рабочий каталог, другими словами — в нем нет отслеживаемых измененных файлов. Git также не обнаружил неотслеживаемых файлов, в противном случае они бы были перечислены здесь. Наконец, команда сообщает вам на какой ветке вы находитесь и сообщает вам, что она не расходится с веткой на сервере.
Добавьте в свой проект новый файл, для того чтобы начать отслеживать новый файл,
используется команда `git add имя файла`.
Теперь нужно выполнить команду `git commit -m "комментарий"` для фиксации изменений в файле проекта.
Для вывода изменений в файлах по сравнению с последним коммитом, используется `git diff`.Команда выводит изменения в файлах, которые еще не были добавлены в индекс. Сравнение происходит с последним коммитом. 
## 6. Просмотр истории коммитов
Для просмотров истории коммитов используется команда `git log`,
эта команда выводит список коммитов созданных в данном репозитории в обратном хронологическом порядке, отображает каждый коммит вместе с его контрольной суммой, именем и электронной почтой автора, датой создания и комментарием.
`git log --online` выводит сокращенный лог.
## 7. Перемещение между сохранениями 
Перемещаться между нашими "сохранениями" можно с помощью команды `git checkout`. Для этого достаточно применить команду `git checkout <номер коммита>`.
Можно отменить изменения с помощью команд `git revert` и `git reset git revert <номер коммита>` отменит изменения до указанной версии и создаст новый коммит. `git reset --hard <номер коммита>` отменит изменения до указанного коммита и затрёт всю историю изменений после этого коммита.
## 8. Игнорирование файлов
Игнорируемые файлы отслеживаются в специальном файле `.gitignore`, который регистрируется в корневом каталоге репозитория. В Git нет специальной команды для указания игнорируемых файлов: вместо этого необходимо вручную отредактировать файл `.gitignore`, чтобы указать в нем новые файлы, которые должны быть проигнорированы. Файлы `.gitignore` содержат шаблоны, которые сопоставляются с именами файлов в репозитории для определения необходимости игнорировать эти файлы.
## 9. Информацию по работе с ветками
### git branch перечисляет существующие ветки, отметив активную, активная ветка помечается(*).

 Для создания новой ветки используется команда: 
```
git branch <name>
```
Удаляет ветку, если та была залита (merged) с разрешением возможных конфликтов в текущую: 
```
git branch -d <name>
```
Удаляет ветку в любом случае:
```
git branch -D <name>
```
Переименовывает ветку:
```
git branch -m <name> 
```
### git checkout — переключение между ветками, извлечение файлов

### git merge — слияние веток, разрешение возможных конфликтов
`git merge` делает следующие шаги:
Проверяет, нет ли конфликтов, т.е. не удалят и не перепишут ли наши изменения какую-либо уже существующую информацию. Если возникает конфликт git merge останавливается, чтобы получить инструкции от пользователя.
### Информация о работе с удаленными репозиториями
## Настройка совместной работы
1. Создать аккаунт на GitHub.com
2. Создать локальный репозиторий
3. “Подружить” ваш локальный и удалённый репозитории.
4. Отправить (push) ваш локальный репозиторий в удалённый (на GitHub), при этом, возможно, вам нужно будет авторизоваться на удалённом репозитории
5. Провести изменения “с другого компьютера”
6. Выкачать (pull) актуальное состояние из удалённого репозитория
## Как предложить изменения на *GitHub* с помощью команды *pull request*
1. Делаем (ответвление) репозитория fork
2. Делаем git clone версии репозитория СВОЕЙ версии репозитория
3. Создаем новую ветку и в НЕЕ вносим свои изменения
4. Фиксируем изменения (делаем коммиты)
5. Отправляем свою версию в свой GitHub
6. На сайте GitHub нажимаем кнопку pull request