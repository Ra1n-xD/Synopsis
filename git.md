# Основные команды гита
 `git init `– инициализация проекта
 `git config --local(global) user.name user.name “Ivan”` <br>
  `git config --local(global) user.email example@gmail.com` – информация о разработчике
 `git status`– статус гита
 `git add -A (или названия файла)` – все добавить файлы
 `git commit –m ”commit”` – коммит
 `git log` – посмотреть историю коммитов
 `git remote add origin https://github.com/ссылка` - добавить репозиторий (origin) гитхаба
 `git push -u origin master` – запушить файлы в репозиторий (origin)
 `git push` – запушить файлы в репозиторий, который мы выбрали командой выше
 `git remote set-url origin “url”` – изменить репу
 `git remote` – удалить привязку к репу

# Работа с разных устройств
- `cd "название папки"` - для начала зайти в нужную папку
- `git clone` https://github.com/ссылка на репозиторий НазваниеПапки - клонирование репозитория в локальную папку
- `git pull` – установка самой свежей версии кода из репозитория
- `git reset --hard origin` – установка самой свежей версии кода из репозитория