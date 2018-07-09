### Чтобы вернуться к какому-то коммиту и исправить его
Для этого нужно перейти на негои создать новую ветку, затем работать с ней:
```
git checkout s739dw2
git branch fix s739dw2
```

### Восстановить удаленную ветку
При удалении ветки командой `git branch -d fix` мы получим сообщение:
```
Deleted branch fix (was f295691)
```
это хэш коммита, где была удаленная ветка. Чтобы её восстановить выполняем комманду:
```
git branch fix f295691
```
Если мы уже не можем найти этот хэш, то делаем следующие действия:
```
# git reflog

22dbb6d HEAD@{0}: checkout: moving from 76e5d28a217c0b6eccc8d39a9a5f9716660de901 to master
76e5d28 HEAD@{1}: checkout: moving from 22dbb6d952242737cdeed53808a3511513910076 to HEAD~
22dbb6d HEAD@{2}: checkout: moving from master to V10
22dbb6d HEAD@{3}: checkout: moving from f295691bb4f052728f406c6b5bf5e96c251ab061 to master
f295691 HEAD@{4}: checkout: moving from master to v1.0
22dbb6d HEAD@{5}: pull: Fast-forward
76e5d28 HEAD@{6}: commit: indev changes from mas
6b06f18 HEAD@{7}: checkout: moving from develop to master
b1c00e8 HEAD@{8}: commit: sss dev
3b5f20f HEAD@{9}: checkout: moving from master to develop
```
находим место где был наш коммит и выполняем комманду:
```
git branch fix HEAD@{1}
```
@{1} - это номер коммита. Т.е. это означает вернуться ко 2 (т.к. считается с 0) коммиту.

### Отменить несколько коммитов
Например мы работали над чем-то и ничего не получилось, мы можем просто удалить эти коммиты. Для этого сначала нужно посмотреть к какому коммиту нам вернуться командой `git reflog` и выполнить команду:
```
git reset --head HEAD@{4}
```
так мы вернулись на 5 коммитов назад. Но что делать, если вспомнили. что в каком-то из этих отмененных коммитов остался важныц код? Возвращаемся опять к нужным коммитам, которые содержат важный код:
```
git reset --head HEAD@{2}
```
создаем ветку с этого места:
```
git branch for_fix
```
возвращаем начальную ветку к нужному состоянию (где удалили всё ненужное):
```
git reset --head HEAD@{4}
```
потом забираем код из созданной ветки `for_fix` и вставляем его куда нам надо.
