### Рабочий процесс с git



#### Настройка

Установить git

Указать свои конфигурации:

`git config —global user.name yourGitHubName`

`git config —global user.email yourGitHubEmail`



#### Создание репозитория

Инициализация репозитория

`git init`

Добавление своего кода

 `git add fileName`

`git commit -m "some message"`



#### Настройка репозитория для членов команды

Сделать форм рабочего репозитория

Клонировать свой форк

`git clone https://github.com/yourGitName/project-name.git`



Добавить рабочий репозиторий в remotes

`git remote add centralRepo https://github.com/centralRepo/project-name.git`



В результате `git remote -v` у вас должно получиться следующее

```
origin	https://github.com/yourGitName/project-name.git (fetch)
origin	https://github.com/yourGitName/project-name.git (push)
centralRepo	https://github.com/centralRepo/project-name.git (fetch)
centralRepo	https://github.com/centralRepo/project-name.git (push)
```



#### Разработка нового функционала

- Убедитесь, что вы на ветке `master`.

  `git checkout master`


- Синхронизируйте свою копию с центральным репозиторием.

  `git pull centralRepo master`


- Создайте новую ветку для каждой новой фичи или бага.

  `git checkout -b new-awesome-feature`


- Напишите свой код и сделайте коммит. Не делайте много изменений в одном коммите. Пишите информативные сообщения коммита.

- Синхронизируйте с мастер веткой, чтобы убедиться, что все в порядке, потому что, пока вы писали свой код, кто-то другой мог внести изменения, которые конфликтуют с вашими.

  `git pull centralRepo master`

- Опубликуйте ветку на github

  `git push -u origin HEAD`

- Зайдите на github и сделайте PR.

- Когда PR успешно влит в центральный репозиторий

  ```
  git branch -d new-awesome-feature
  git push origin --delete new-awesome-feature

  ```

  ​
