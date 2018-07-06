### Создание Git-репозитория

Для создания Git-репозитория существуют два основных подхода. 
Первый подход — импорт в Git уже существующего проекта или каталога. 
Второй — клонирование уже существующего репозитория с сервера.

***1) Создание репозитория в существующем каталоге***
```
git init
```
Создать репозиторий с именем (будет создана дирректория в текущей папке):
```
git init newrepo.git
```
Рекомендуется использовать `.git` в названии папки с репозиторием

**Добавить под версионный контроль**
```
git add *.c
git add README
git commit -m 'initial project version'
```

***2) Клонирование существующего репозитория***
```
git clone git://github.com/schacon/grit.git
```
Эта команда создаёт каталог с именем `grit`, инициализирует в нём каталог `.git`, скачивает все данные для этого репозитория и создаёт (checks out) рабочую копию последней версии. Если вы зайдёте в новый каталог grit, вы увидите в нём проектные файлы, пригодные для работы и использования. Если вы хотите клонировать репозиторий в каталог, отличный от `grit`, можно это указать в следующем параметре командной строки:
```
git clone git://github.com/schacon/grit.git mygrit
```
Эта команда делает всё то же самое, что и предыдущая, только результирующий каталог будет назван `mygrit`.

Для того, чтобы при клонировании не создавался дополнительный каталог, используется команда:
```
git clone git://github.com/schacon/grit.git .
```