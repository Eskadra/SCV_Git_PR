# Работа с Git и Github
## 1. Проверка наличия установленного Git
В терминале выполнить команду `git version`.
Если Git установлен появиться сообщение о версии программы, иначе будет сообщение об ошибки.
## 2.Установка Git
Загружаем последнюю версию Git с сайта
[Установка Git](https://git-scm.com/downloads).
Устанавливаем с найстройками по умолчанию.
## 3. Настройка Git
При первом использовании Git необходимо представиться.
Для этого нужно ввести в терминале 2 команды:
````
git config --global user.name "Ваше имя английскими буквами"
git config --global user.email ваша почта@example.com
````
## 4. Инициализация репозитория
В терминале переходим к папке, в которой хотим создать репозиторий. Выполним команду:
````
git init
````
## 5. Запись изменений в репозиторий
 Для того чтобы начать отслеживать новый файл, используется команда:
 ````
 git add <название файла>
 ````
 или когда нужно захватить все файлы, используйте комманду:
  ````
 git add .
 ````
## 6. Просмотр истории коммитов
 После того, как вы создали несколько коммитов или же клонировали репозиторий с уже существующей историей коммитов, вероятно вам понадобится возможность посмотреть что было сделано — историю коммитов. Одним из основных и наиболее мощных инструментов для этого является команда:
 ````
git log
````
## 7. Перемещение между сохранениями 
Для перемещения между веток. Выполним команду:
````
git checkout <название ветки>
```` 
При переключении ветки происходит обновление файлов в рабочем каталоге в соответствии с версией, хранящейся в этой ветке, а Git начинает записывать все новые коммиты в этой ветке. Рассматривайте эту команду как способ выбрать направление своей разработки.

## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенные файлы или папки, необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответсвующие таким файлам или папкам.

## 9. Создание веток в Git
По умолчанию имя основной ветки в Git - *master*.
Создать ветку можно командой:
```
git branch <название для новой ветки>
```
Текущая ветка будет отмечена звездочкой **\* master**

## 10. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей нужно выполнить команду:
```
git merge <название выбранной ветки>
```
Если была изменена одна и та же часть файла в обеих ветках, то можеи возникнуть конфликт, который потребует участия пользователя. VSCode предлагает варианты разрешения. Чтобы разрешить конфликт, нужно выбрать один из вариантов, либо объеденить содержимое по своему. Для завершения слияния создайте новый коммит, после завершения конфликта. Для этого используйте следующую команду:
```
git commit -m <название коммита>
```

## 11. Удаление веток
Команда для удаления ветки в Git:
```
git branch -d  <название выбранной ветки>
```
Но есть нюанс, нельзя удалить ветку в которой находитесь поэтому следует перейти на другую ветку используя команду:
```
git switch <название выбранной ветки>
```
далее используя вышеупомянутую команду удалить нужную.

## 12. Работа с удаленными репозиториями
1. Для начала нужно зарегестрироваться на [GitHub](https://github.com/)
2. Создать локальный репозиторий
3. Создать удалённый репозиторий(Если требуется)
4. Связать удалённый репозиторий с локальным . Для этого используется команда:
```
git remote add <Имя репозитория> <url удалённого репозитория>
```
Для проверки наличия удалённого репозитория используется команда :
```
git remote
git remote -v для просмотра подробной информации
```
Далее нужно переименовать ветку master в main командой :
```
git branch -m main
```
Отправляем изменения в удалённый репозиторий командой :
```
git push -u <Имя репозитория> main
```
Если делает это впервые, то нужно авторизоваться на GitHub
Для получения и слияния изменений из удалённого репозитория используется команда :
```
git pull
```
## 13. Работа с чужим репозиторием
В своем аккаунте на GitHub создать копию репозитория из другого аккаунта с помощью кнопки **Fork**
Для того, чтобы клонировать репозиторий, необходимо перейти в свой аккаунт. Найти нужный репозиторий, перейти на вкладку **Code**, после чего скопировать адрес.

Для клонирования репозитория нам сперва в CMD нужно оказаться в той папке куда будет сохранен репозиторий. После чего используем команду:
```
git clone <скопированный путь к репозиторию с GitHub>
```
Далее следует создать новую ветку, в которой и будет вестись работа.

После завершения работы необходимо отправить **PullRequest**