### Удаление файлов из git

Если просто удалить файл закоммиченный файл командой `rm file.txt`, то он останется в гите.

Если мы добавили файл в индекс (git add), ***его можно удалить из индекса командой***:
```
git rm file.txt --cached
```
но он останется в файловой системе как файл.
***Чтобы удалить его и из индекса и с файловой системы:***
```
git rm file.txt -f
```
Если мы случайно удалили файл с ФС, но он был закоммичен, ***его можно восстановить коммандой:***
```
git checkout -- file.txt
```
