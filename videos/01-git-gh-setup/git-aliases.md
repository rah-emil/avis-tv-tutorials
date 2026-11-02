# Алиасы git: короткие команды

> Один раз настраиваем — дальше `git st` вместо `git status`. Работает одинаково на macOS, Windows и Ubuntu.

[← Назад к настройке git и gh](README.md)

## Как это работает

Алиас — это сокращение, которое git хранит в твоём `~/.gitconfig`:

```bash
git config --global alias.КОРОТКО "полная команда"
```

После этого `git КОРОТКО` = `git полная команда`. Кавычки нужны, если в команде есть пробелы.

## Основной набор

```bash
git config --global alias.st "status"
git config --global alias.co "checkout"
git config --global alias.cp "cherry-pick"
git config --global alias.ph "push origin HEAD"
```

| Алиас | Что запускается | Зачем |
|---|---|---|
| `git st` | `git status` | Что изменилось |
| `git co` | `git checkout` | Переключиться на ветку или коммит |
| `git cp` | `git cherry-pick` | Перенести коммит в текущую ветку |
| `git ph` | `git push origin HEAD` | Отправить текущую ветку в GitHub — без указания её имени |

## Ещё удобные сокращения

```bash
git config --global alias.cb "checkout -b"
git config --global alias.br "branch"
git config --global alias.sw "switch"
git config --global alias.ci "commit"
git config --global alias.cm "commit -m"
git config --global alias.df "diff"
git config --global alias.pl "pull --rebase"
git config --global alias.unstage "restore --staged"
git config --global alias.amend "commit --amend --no-edit"
git config --global alias.last "log -1 HEAD"
git config --global alias.lg "log --oneline --graph --decorate --all"
```

| Алиас | Что запускается | Зачем |
|---|---|---|
| `git cb имя` | `git checkout -b имя` | Создать ветку и сразу перейти в неё |
| `git br` | `git branch` | Список веток |
| `git sw имя` | `git switch имя` | Переключиться на ветку (современная замена `checkout`) |
| `git ci` | `git commit` | Коммит |
| `git cm "текст"` | `git commit -m "текст"` | Коммит с сообщением |
| `git df` | `git diff` | Показать изменения построчно |
| `git pl` | `git pull --rebase` | Забрать изменения без лишних merge-коммитов |
| `git unstage файл` | `git restore --staged файл` | Убрать файл из `git add` |
| `git amend` | `git commit --amend --no-edit` | Дописать изменения в последний коммит |
| `git last` | `git log -1 HEAD` | Последний коммит |
| `git lg` | `git log --oneline --graph --decorate --all` | История веток картинкой в терминале |

## Проверка

```bash
git config --global --get-regexp '^alias\.'
```

Команда печатает все твои алиасы. Попробуй `git st` в любой папке с репозиторием.

## Вместо команд — один файл

Всё то же самое можно вставить в `~/.gitconfig` (открыть: `git config --global --edit`):

```ini
[alias]
	st = status
	co = checkout
	cp = cherry-pick
	ph = push origin HEAD
	cb = checkout -b
	br = branch
	sw = switch
	ci = commit
	cm = commit -m
	df = diff
	pl = pull --rebase
	unstage = restore --staged
	amend = commit --amend --no-edit
	last = log -1 HEAD
	lg = log --oneline --graph --decorate --all
```

## Дальше

- [Шпаргалка по git](git-cheatsheet.md)
- [Шпаргалка по gh](gh-cheatsheet.md)
