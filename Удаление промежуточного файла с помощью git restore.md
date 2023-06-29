[<К содержанию](./%D0%9F%D1%80%D0%BE%D1%87%D1%82%D0%B8.md)

# Удаление промежуточного файла с помощью `git restore`

 Допустим, изменили два файла и хотите зафиксировать их как два отдельных изменения, но случайно ввели `git add *` и разместили их оба. Как можно отменить изменение одного из двух? `git status` Команда напоминает:

```bush=
$ git add *
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   CONTRIBUTING.md
	renamed:    README.md -> README
```

Прямо под текстом *“Изменения, которые необходимо зафиксировать”* написано использовать `git restore --staged <file>…`​ для изменения статуса. Итак, давайте воспользуемся этим советом, чтобы изменить статус `CONTRIBUTING.md` файла:

```bush=
$ git restore --staged CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	renamed:    README.md -> README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   CONTRIBUTING.md
```

`CONTRIBUTING.md` Файл изменен, но снова не сохранен.