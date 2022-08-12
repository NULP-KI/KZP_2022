# KZP_2022
# Cross-platform programming tools students repo #

## Як налаштувати git середовище ##
1. Зареєстуватися на github.com
2. Створити персональний токен доступу зігдно https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token.
3. Встановити на ком'ютер git клієнт (рекомендовано cygwin (при інсталяції перевірити чи git є серед пакетів, що інсталюються) або один з клієнтів перелічених на https://git-scm.com/download/gui/windows)
4. Налаштувати клієнт (на прикладі cygwin)
   1. Налаштувати ім'я: git config --global user.name "Ваще Прізвище і ім'я латиницею"
   2. Налаштувати e-mail: git config --global user.email username@domain.com
   3. Налаштувати шлях до програми редагування запитів на злиття (якщо не задано то стандартний буде використано): git config --global core.editor /c/path/to/your/editor
   4. Кажемо не використовувати режим fast-forward: git config --global merge.ff false
   5. Встановити програму для розв'язання мердж конфліктів (KDiff3: https://sourceforge.net/projects/kdiff3/)
   6. Налаштувати KDiff3:
git config --global merge.tool kdiff3
git config --global mergetool.kdiff3.path <pathto>/kdiff3.exe
git config --global diff.tool kdiff3
git config --global difftool.kdiff3.path <pathto>/kdiff3.exe
   7. Для Windows машини слід виконати: git config --global core.autocrlf true


## Коротка інструкція по роботі з GitHub ##

### Клонування репозиторію ###
Клонування репозоторію відбувається командою з командного рядка cygwin у поточну робочу директорію:  
git clone https://github.com/NULP-KI/KZP_2022.git

### Переключення на робочу гілку ##
Для переключення на гілку виконати з папки KZP_2022: git checkout <гілка>  
**Note:** гілка = назва групи латиницею. Наприклад KI33.

### Внесення змін і передача їх на GitHub ###
1. На гілці завантажити останні зміни: git pull
2. Внести зміни у власну папку (назва папки = прізвище латиницею)
3. Вибрати зміни для коміту: 
   1. Виконати: git status
   2. Вибрати файли які слід додати до коміту і додати їх командою: git add <file1> <file2> ... (або "git add ." щоб додати усі файли)
4. Створити коміт: git commit -m "Коментар до коміту"
5. Revers merge (синхронізуватися зі змінами зробленими іншими): git pull
6. У випадку конфліктів слід їх розв'язати. Для цього зручно використати команду "git mergetool" яка завантажить KDiff3 і відкриє файли які конфліктують для ручного розв'язання конфліктів.
7. Після роз'язання конфліктів виконати 3.2, 3.3.
8. Виконати: git push
9. Після запиту ввести ім'я користувача на GitHub.
10. Після запиту ввсести токен доступу.

*У разі успіху ви побачите повідомлення схоже на:*  
Enumerating objects: 4, done.  
Counting objects: 100% (4/4), done.  
Delta compression using up to 8 threads  
Compressing objects: 100% (2/2), done.  
Writing objects: 100% (3/3), 282 bytes | 47.00 KiB/s, done.  
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0  
To https://github.com/NULP-KI/KZP_2022.git  
   42455e3..ceea34c  <branch> -> <branch>  
