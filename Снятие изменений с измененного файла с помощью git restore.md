[<К содержанию](./%D0%9F%D1%80%D0%BE%D1%87%D1%82%D0%B8.md)

# Снятие изменений с измененного файла с помощью `git restore`

Что, если поймете, что не хотите сохранять изменения в `CONTRIBUTING.md` файле? Как можно легко отменить модификацию — вернуть ее к тому, как она выглядела при последней фиксации? К счастью, `git status` также рассказывает, как это сделать. В последнем примере вывода нестационарная область выглядит следующим образом:

```bush=
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   CONTRIBUTING.md
```

В нем довольно четко указано, как отменить внесенные изменения. Давайте сделаем то, что в нем сказано:

```bush=
$ git restore CONTRIBUTING.md
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	renamed:    README.md -> README
```
***
###### <font color="red">Важно:</font>
###### Важно понимать, что `git restore <file>` это опасная команда. Все локальные изменения, которые внесли в файл, исчезли — *Git* просто заменил этот файл последней подготовленной или зафиксированной версией. Никогда не используйте эту команду, если точно не знаете, что не нужны эти несохраненные локальные изменения.
***
