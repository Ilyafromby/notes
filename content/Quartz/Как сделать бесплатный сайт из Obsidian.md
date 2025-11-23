---
title: Сайт из Obsidian
---
[Obsidian](https://obsidian.md/) - это бесплатное приложение для создания и хранения заметок. Устанавливается локально на компьютере пользователя. Заметки создаются в очень легком текстовом формате markdown. Каждая заметка доступна как отдельный файл в директории и может быть открыта любым совместимым редактором, например, [Sublime Text](https://www.sublimetext.com/).

Obsidian бесплатный, но за синхронизацию его с облаком потребуется оплатить подписку. Возможно, использовать Google Disk, OneDrive и другие облачные хранилища. 

Для того, чтобы сделать из заметок на компьютере статический сайт, используется приложение [Quartz, доступное на GitHub](https://github.com/jackyzha0/quartz). Ниже написал инструкцию, которую сам и использую.

## Руководство по установке на английском:

1. https://quartz.jzhao.xyz/
2. https://www.xda-developers.com/turned-obsidian-vault-into-website/

## Требуются приложения

1.  **[Node](https://nodejs.org/) v22**
2. `npm` v10.9.2
3. `git`

## Инициализация

``` sh
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```

## Контент

В директории `quartz` надо найти директорию `content`
В ней будет находится все содержание сайта
В Obsidian надо подключить эту директорию как vault
## Запустить сайт локально, для проверки

```
npx quartz build --serve
```

## GitHub

Create a new repository on GitHub.com. Do **not** initialize the new repository with `README`, license, or `gitignore` files.

``` sh
# list all the repositories that are tracked
git remote -v
 
# if the origin doesn't match your own repository, set your repository as the origin
git remote set-url origin REMOTE-URL
 
# if you don't have upstream as a remote, add it so updates work
git remote add upstream https://github.com/jackyzha0/quartz.git
```

In future updates, you can simply run `npx quartz sync` every time you want to push updates to your repository.
## GitHub Pages

[Руководство по созданию сайта на GitHub](https://quartz.jzhao.xyz/hosting#github-pages)

1. В директории Quartz сделать файл с конфигурацией quartz/.github/workflows/deploy.yml. Делал это через Sublime Text
2. Head to “Settings” tab of your forked repository and in the sidebar, click “Pages”. Under “Source”, select “GitHub Actions”.
3. Commit these changes by doing `npx quartz sync`. This should deploy your site to `<github-username>.github.io/<repository-name>`.

