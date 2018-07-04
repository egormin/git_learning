### Создание алиасов
***Создать алиас:***
```
git config --global alias.st status
```
Эта команда создаст алиас в глобальном конфиге. Алиас будет называться `st`, а заменять будет команду `status`.

Чтобы его вызвать, пишем:
```
git st
```
Занесём в алиас команду для вывода лога в удобном виде:
```
git config --global alias.getlog "log --pretty=format:'%h %Cgreen<%an>%Creset %s %Cred%cr%Creset' --graph"
```
Алиас модет расширяться параметрами, также как и команда:
```
git getlog -5
```
Чтобы посмотреть созданные алиасы:
```
git config --get-regexp alias
```
Выполнение внешних команд в алиасе гита:
```
git config alias.com '!git add . && git commit -a'
```
Воспользоваться можно: `git com "test commit"`

Удалить алиас:
```
git config --unset alias.st
```
