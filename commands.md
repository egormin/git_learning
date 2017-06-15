Чтобы проинициализировать Git репозиторий введите команду. Будет создана папка /.git/. Репозиторий - это скрытая папка, в которой работает Git. 
```
git init
```
Чтобы добавить в Git все файлы:
```
git add .
```
Чтобы добавить один конкретный файл:
```
git add text.txt
```
Посмотреть статус
```
git status
```
Чтобы сохранить изменения и добавить сообщение (m - message), надо выполнить комманду:
```
git commit -m "first commit"
```
Чтобы сохранить изменения для всех файлов (a - all), надо выполнить комманду:
```
git commit –a –m "new comment here"
```
Чтобы посмотреть лог коммитов:
```
git log
```
Посмотреть сконфигурированное имя пользователя:
```
git config user.name
```
Сконфигурировать имя пользователя:
```
git config user.name Vasya
```
Посмотреть сконфигурированный email пользователя:
```
git config user.email
```
Сконфигурировать email пользователя:
```
git config user.email vasya@tut.by
```
Чтобы посмотреть удаленные репозитории
```
git remote -v
```
Чтобы добавить удаленный репозиторий
```
git remote add origin https://github.com/egormin/ansible_sonar.git
```
Посмотреть дополнительную информацию о репозитории:
```
git remote show origin
git remote show https://github.com/egormin/ansible_sonar.git
```

