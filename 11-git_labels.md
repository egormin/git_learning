### Метки
Git имеет возможность помечать (tag) определённые моменты в истории как важные. Как правило, эта функциональность используется для отметки моментов выпуска версий (v1.0, и т.п.).


***Просмотр меток:***
```
git tag
```
***Когда меток очень много, можно использовать просмотр меток по шаблону:***
```
git tag -l 'v1.*'
```

### Создание меток
Git использует два основных типа меток: ***легковесные*** и ***аннотированные***.

***Легковесная метка*** — это что-то весьма похожее на ветку, которая не меняется — это просто указатель на определённый коммит.

А вот ***аннотированные метки*** хранятся в базе данных Git’а как полноценные объекты. Они имеют контрольную сумму, содержат имя поставившего метку, e-mail и дату, имеют комментарий и могут быть подписаны и проверены с помощью GNU Privacy Guard (GPG). Обычно рекомендуется создавать аннотированные метки, чтобы иметь всю перечисленную информацию; но если вы хотите сделать временную метку или по какой-то причине не хотите сохранять остальную информацию, то для этого годятся и легковесные метки.

***Аннотированные метки:***
```
git tag -a v1.4
git tag -a v1.4 -m 'my version 1.4'
```
с помощью `-m` можно добавить сообщение к метке.

***Легковесные метки:***
Для создания легковесной метки не передавайте опций `-a`, `-s` и `-m`:
```
git tag v1.4
```
***Просмотр информации о метке:***
```
git show v1.2
```
***Выставление меток на предыдущие коммиты***
```
git tag -a v1.2 9fceb02
```
***Удаление меток***
```
git tag -d v1.2
```
***Отправка меток на удалённые серверы***
```
git push origin v1.5
```
если нужно отправить сразу все:
```
git push origin --tags
```
***Переход на метку:***
В действительности вы не можете переходить на метки в Git, поскольку они не могут быть перемещены. Если вы хотите установить версию вашего репозитория в рабочую директорию, которая выглядит, как определенная метка, вы можете создать новую ветку с определенной меткой:
```
git checkout -b version2 v2.0.0
```
Будет создана ветка `version2` из коммитов тэга `v2.0.0`.


