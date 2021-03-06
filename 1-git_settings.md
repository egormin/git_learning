### Настройки Git

- Файл `/etc/gitconfig` содержит значения, общие для всех пользователей системы и для всех их репозиториев. Если при запуске git config указать параметр `--system`, то параметры будут читаться и сохраняться именно в этот файл.
- Файл `~/.gitconfig` хранит настройки конкретного пользователя. Этот файл используется при указании параметра `--global`.
- Конфигурационный файл в каталоге Git'а `.git/config` в том репозитории, где вы находитесь в данный момент. Эти параметры действуют только для данного конкретного репозитория. 

Настройки на каждом следующем уровне подменяют настройки из предыдущих уровней, то есть значения в `.git/config` перекрывают соответствующие значения в `/etc/gitconfig`.
<br><br><br>
***Чтобы посмотреть текущие настройки Git:***
```
git config --system --list
git config --global --list
git config --list
```
***Посмотреть имя и email пользователя:***
```
git config --global user.name
git config --global user.email
```
***Установить имя и email пользователя:***
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```
***Установить имя и email пользователя для одного текущего репозитория:***
```
git config user.name "John Doe"
git config user.email johndoe@example.com
```
***Посмотреть и сконфигурировать редактор:***
```
git config --global core.editor
git config --global core.editor nano
```
***Посмотреть и сконфигурировать утилиту сравнения:***
```
git config --global merge.tool
git config --global merge.tool vimdiff
```
***Запоминать учетные данные при подключении по https:***
```
git config --global credential.helper cache
```
