# Git

## Главное
`git config --global user.name` - показать имя<br/>
`git config --global user.name "test"` - изменить или задать имя<br/>
`git config --global user.mail` - показать почту

`git status` - определить статус рабочей папки<br/>
`git add test.js` - добавить отслеживаемый файл<br/>
`git add .` - добавить все файлы из директории<br/>
`git rm --cashed test.js` - перестать отслеживать файл<br/>
`git commit -m "test"` - создать коммит и задать ему имя<br/>
`git branch test` - создание ветки `test`<br/>
`git branch -D test` - удаление ветки `test`<br/>
`git checkout test` - переключение на ветку `test`<br/>
`git checkout -b test` - создание ветки и переключение на неё<br/>
`git merge test` - объединеяет ветку `test` с теущей веткой (создастся коммит)

`git remote add origin тестовая_ссылка_на_гит_репозиторий` - подписать проект на гит репозиорий<br/>
`git push -u origin master` - запушить на гит в мастер ветку `-u` - запоминает `origin master`<br/>
`git push` - все остальные разы

`git clone тестовая_ссылка_на_гит_репозиторий` - клонировать репозиторий локально<br/>
`git pull` - обновляет локальный репозиторий

## Разное
`ls -la` - `ls` - просмотреть файлы и папки в каталоге; `-l` - выводит файлы и папки в виде списка; `-a` - отобразит все скрытые файлы и каталоги<br/>
`touch app.js` - создает файл app.js

## Изменение конфига на разных уровнях
`git config --system` - конфиг для всех пользователей системы<br/>
`git config --global` - конфиг для конкретного пользователя системы<br/>
`git config --local` - конфиг для конкретного репозитория

## Создание/Регистрация пользователя
`git config --global user.name "тестовое_имя"`<br/>
`git config --global user.email "тестовый@мейл"`

## Основные команды git
`git init` - инициализация git<br/>
`git log` - история изменений/созданий коммитов<br/>
- `git log -p` - расширенный вид со свойствами коммита

`git status` - статус файлов<br/>
`git show тестовый_хэш_коммита` - открыть свойства коммита???<br/>
`git restore test.js` - откатывает изменения в файле до состояния последнего коммита<br/>
- `git restore --aged test.js` - откатывает индексированные файлы

`git diff test.js` - показывает в консоли изменения в файле с момента последнего коммита<br/>
- `git diff --staged` - показывает изменения файлов до индексирования

`git mv test.js ./src/index.js` - перемещает и переименовывает файл плюс команда `add`<br/>
`git rm test.js` - удаляет файл<br/>
- `git rm --cached` - удаляет, но кеширует файл???

`git branch -a` - показывает все ветки в репозитории<br/>
`git checkout develop` -

## untracked -> staged(индексированные файлы) -> commited
`git add test.js` - индексируем файл<br/>
`git commit -m "тестовое_название_коммита"` - коммитим файл<br/>
- `git commit -am "тестовое_название_коммита"` - объединяет `add` и `commit`

## Ветвление/слияние
`git branch тестовое_название_ветки` - создание новой ветки<br/>
`git checkout тестовое_название_ветки` - переключение на ветку<br/>
- `git checkout -d тестовое_название_ветки`- создает ветку и переключает на нее
- `git checkout -d тестовое_название_ветки тестовый_хэш_коммита` - создает ветку из определенного коммита и переключает на нее

`git checkout тестовый_хэш_коммита` - переключение на коммит<br/>
`git checkout test.js` - аналог `git restore`<br/>
`git merge тестовое_название_ветки` - слияет ветку `тестовое_название_ветки` с текущей веткой<br/>
`git branch -d тестовое_название_ветки` - удаляет ветку<br/>
`git reset --hard тестовый_хэш_коммита` - отменяет изменения до указанного коммита

## Работа с удаленными репозиториями
`git remote add origin тестовая_ссылка_на_гит_репозиторий` - связывает локальный репозиторий с локальным<br/>
- `git remote -v` - показывает все репозитории???
- `git remote rm origin`

`git push origin master` - отпрваляет локальный репозиторий в удаленный<br/>
- `git push --set-upstream origin master` - "привязывает" локальный реп к удаленному. В дальнейшем можно использовать просто `git push`

`git clone тестовая_ссылка_на_гит_репозиторий` - получаем локальный репозиторий с удаленного<br/>
`git pull` - синхронизирует локальные файлы с удаленного сервера<br/>
`git fetch origin` - скачивает недостающие коммиты???

`git rebase master` -

## .gitignore
`*.[jt]s` - игнормрует все файлы с расширением `js` или `ts`<br/>
`test/` - игнормрует папку test<br/>
`test/test.txt` - игнормрует файл `test.txt` в папкe `test`<br/>