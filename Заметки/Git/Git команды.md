- `git checkout [filename]` вернуть 
 состояние файла из индекса(stage) 
 - `git checkout head [filename]` возращает версию файла из фиксации(commit) в рабочую папку и индекс 
 `git checkout [commitHash][filename]` либо `git checkout [refCom][filename]` возращает версию файла данного коммита(или коммита на который указывает ветка) в директорию и в индекс 
- `git checkout [branchName]` позволяет сменить ветку
- `git checkout -b[remoteBrancName]` создает ветку в локальном репо но без слежения за удаленной веткой
- `git checkout -b [branchName]` позволяет создать ветку и переключиться на нее.
- `git checkout -b [branchName][remoteRepo]/[remoteBranchName]` позволяет создать ветку  на основе удаленной ветки и создать отслеживающию ветку(т.е. при коммандах git push git pull эти действия из локальной ветки будет относиться к удаленной).
- `git checkout -B [branchName][hashCommit]` переместит указатель ветки на коммит и переключиться на ветку
- `git checkout --track [remoteRepo]/[remoteBranchName]`  позволяет создать ветку  на основе удаленной ветки и создать отслеживающию ветку но нельзя задать имя локальной ветки
- `git checkout -b [branchName][commitHash]` создает ветку указывающая на определенный коммит
- `git checkout @{-1}` возращаеться на предыдущую ветку с которой переключились
- `git reset` сбросить индекс
- `git reset [filename]` убрать файл из индекса
- `git reset --soft [refCom]` сдвигает указатель ветки на коммит при это сохраняя все данные  индекса и рабочей директории. Может использовать есть что то забыл сделать и случайно закомитил, можно вернуться со всеми данными к предыдущему(обычно) коммиту и подравить данные и сделать новых коммит.
- `git reset --mixed`  сдвигает указатель ветки на коммит при это сохраняя все данные в  рабочей директории.
- `get reset --hard`  сбрасывает все файлы в директории до состояния фиксации текущего коммита
- `get reset --hard [refCom]`  сдвигает указатель ветки коммит и сбрасывает состояние рабочей папки и индекса до данного коммита
- `git rm --cached [filename] .`  убрать отслеживание файла
- `git rm -r --cached .`  удалить все файлы из области отслеживания(но прежде надо выполнит фиксацию)???
- `git log [branchName]` показывает коммиты данной ветки
- `git log -5 HEAD` показывает последние 5 комитов
- `git log --decorate` позволяет узнать коммиты и куда нацелены указатели веток  
- `git log --graph [branchName]` позволяет вывести коммиты для определенной ветки
- `git log --graph --all` позволяет вывести все коммиты с ветками и увидет все ветвления
- `git log [commitHash] -p` подробная информация о коммите
- `git log --oneline --decorate --graph --all`
	также позволяет вывести все ветки с пересечениями но в короткой форме
- `git confing user.name` установить имя для текущего репо
- `git confing --global user.name` установить имя для всех действий системы
-  `git confing user.email` установить почту для текущего репо
- `git confing --global user.email` установить почту для всех действий системы
- `git config --global alias.[nameYourAl][gitCommand]` позволяет создать псевдоним для команды 
- `git config --global alias.[nameYourAl]["gitCommands"]` позволяет создать псевдоним для последовательности команд
-  `git config --global alias.[nameYourAl]["!outerCommands"]`  создание псевдонима для внешних команд, начинаеться с !
- `git ignore` позволяет игнорировать файлы который ненужны для добавления в репозиторий
- `git status` дает информации о статусах файлов в локальном репо
- `git status -s`  дает более короткую форму записи
файлы со знаком ?? неотслеживаемые.
Статусы файлов выводяться в два столбца, в первом указываться индексирован ли файл, а во втором вносились ли изменения
- `git show [refCommit]` показывает информацию о коммите
- `git show [refC]~` тильда и цифра показывает на сколько коммитов назад вернуться и показать инфо о коммите
-  `git show [refC]~2 --quiet` тильда и цифра показывает на сколько коммитов назад вернуться и показать инфо о коммите(не показывать изменения)
- `git show [refC]:[fileName]` выводит содержимое файла определенного коммита
- `git show :[fileName]` выводит содержимое файла в индексе
- `git show :/[message]` ищет коммит по описанию коммита
- `git diff` позволяет посмотреть изменения в рабочей папке относительно индекса
- `git diff [filename]` позволяет посмотреть изменения файла в рабочей папке относительно индекса
- `git diff head` показывает изменения в раб. папке относительно фиксации
- `git diff --stage`  показывает изменения между фиксацией и индексом
- `git diff [refCom1][refCom2]` показывает что сделано во второй ветки относительно первой ветки
-  `git diff [refCom1][refCom2][fileName]` показывает что сделано в файле во второй ветки относительно первой ветки
-  `git diff [refCom1]...[refCom2]` показывает что сделано во второй ветки после ее отвлетвления от первой ветки
- `git diff --name-only[refCom1][refCom2]`
показывает названия файлов в которых есть различия
- `git diff --no-index [file1][file2]` сравнивает два файла на компьютере 

- `git add` позволяет проиндексировать файлы и добавить в stage
-  `git add -p [fileName]` позволяет выбрать какую часть файла нужно добавить в индекс
- `git commit` позволяет фиксировать файлы
- `git commit -v` выводит  добавляемые изменения в фиксацию(Чтобы включит diff изменений в git commit по умолчанию можно исп. команду `git config --global commit.varbose true`)
- `git commit -c [refCom]` взять описания коммита из коммита.Если `-C` то без редактирования. Помимо описания коммита береться и автор и дата. Обычно используеться для исправления коммита. 
- `git commit -m [message]` позволяет фиксировать файлы с указанием сообщения сразу в команде
- `git commit -m [message][fileName]` индексирует файл и фиксирует(только отслеживаемые)
- `git commit -a` позволяет фиксировать отслеживаемые файлы без необходимости исп. команды индексации
-  `git commit --amend` перемещает указатель ветки на один коммит назад сохраняя данные с коммита тем самым позволяет создать новый коммит если ошибся
- `git mv file file_to` используеться чтобы переместить файл, также можно при этом переименовать файл
- `git restore --staged [fileName]` если случайно проиндексировал файл, позволяет убрать из stage.
- `git restore` если изменили файл и хотите вернуть к состоянию на момент фиксации.
- `git remote` чтобы просмотреть список исп. удаленных серверов,
-  `git remote -v` чтобы просмотреть список исп. удаленных серверов с url(в скобка будет показываться разрешенная для нас операция(запись или чтение))
- `git remote add [repoName] [Url]`  чтобы добавить удаленный репозиторий
- `git fetch [repoName]` нужен для скачивания веток и их объектов из репозитория.
- `git push [repoName][branch]` чтобы загрузить ветку с данными с локального репо на удаленный. Команда сработает если есть доступ на запись и за это время никто не отправлял туда свои данные.Прежде чем добавить свое нужно встроит  к себе данные того кто добавил прежде изменения.
- `git push [remoteRepo][branchName]:[remoteBranchName]` позволяет отправить ветку с новым именем удаленной ветки
- `git remote show [repoName]` для получения дополнительной информации о удаленном репо.
- `git remote rename [nameFrom][nameTo]` чтобы переименовать имя удаленного репо
- `git branch` позволяет показать все ветки
- `git branch [branchName]` позволяет создать новую ветку которая будет указывать на тот комит на который указывает текущая ветка(откуда создается ветка)
- `git branch --merged` показывает ветки объединенные с этой
- `git branch --no-merged` показывает ветки которые еще не слиты
- `git branch -v` показывает последний коммит каждой ветки
- `git branch -d [branchName]` позволяет удалить ветку.
- `git branch -f [branchName]` позволяет сдвинуть указатель ветки к указателю `head` .
- `git branch -f [branchName][commitHast]` позволяет сдвинуть указатель ветки к комиту .
- `git branch -u [branch]` отслеживать ветку
- `git branch --set-upstream-to [branch]` отслеживать ветку
- `git branch -vv` показыть ветки наблюдения и информацию о том насколько опережает или отстает коммитов от удаленной ветки(`ahead 3, behind 1` показывает что ЛР опережате УР на 3 коммита и отстает на 1 т.е. у УР есть незагруженный коммит который отсутствует в ЛР(Это локальная информаци т.е. если кто то загрузит комит, здесь не отобразиться)) 
- `git merge [branchName]` позволяет объеденить ветки текущию с 
- `git merge [remoteRepo]/[remoteBranchName]` позволяет объеденить ветку с удаленной веткой
- `git reflog` показывает историю перемещений указателей по коммитам(запись о перемещении рабочей ветки храниться 90 дней, а если ветка удалена то 30). Данные reflog храняться локально
- `git reflog --date=iso` показывает историю перемещений указателей по коммитам c датами
- `git pull` выполняет команды git fetch и git merge для веток у которых есть слежение
- `git stash` архивирует незакоммиченные изменения и возращает рабочую папку к моменту фиксации(полезно когда нужно переключиться но если изменения не закомитить то они пропадут) чтобы разархивировать изменения применяеться `git stash pop`
- `git stash pop` разархивирует изменения в любой ветки
- `git clean -dxf` удаляет из раб. директории d - директории, х - файлы в gitignore, f- вы уверены
- `git blame [file]` показывает информации кто коммитил каждую строку





- `rm [fileName]` позволяет удалить файл(linux)
- `del [fileName]` позволяет удалить файл(win)
- `cat .git/HEAD` показывает на что указывает head