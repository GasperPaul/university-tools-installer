# University Tools Installer

Цей репозиторій містить набір скриптів для Windows для автоматизованого встановлення програм, необхідних для курсів програмування на факультеті прикладної математики в КПІ.

# Як користуватися цим репозиторієм?

Перш за все, завантажте архів зі скриптами. Це можна зробити, натиснувши зелену кнопку Code вище та вибравши пункт [Download ZIP](https://github.com/GasperPaul/university-tools-installer/archive/main.zip), або скориставшись сторінкою [релізів](https://github.com/GasperPaul/university-tools-installer/releases).

Після цього, створіть у себе на комп'ютері папку, в яку ви хотіли би встановити усі необхідні вам програми. Бажано, аби шлях до папки не містив пробілів та нелатинських символів, тому стандартний шлях на кшталт `C:\Program Files\` — це погана ідея. Справа в тому, що деякі програми погано сприймають шляхи з пробілами, і можуть працювати некоректно. Крім того, якщо ви будете працювати із командним рядком, це вбереже вас від зайвих помилок та необхідності щоразу брати ім'я файлів у лапки. Прикладом хорошого шляху є `C:\Tools\` чи `D:\Programs\University`. Зверніть увагу, що папка не обов'язково має бути порожньою. 

Розпакуйте у цю папку скачаний архів. У результаті, у вас має утворитися структура файлів, подібна до наступної:

```
|-<ваша цільова папка>
  |
  |-university-tools-installer-main
    |
    |-7za.exe
    |-installer.ps1
    |-install-all.bat
    |-...
    |-README.md
  |
  |-...
```

Тепер, вам необхідно обрати, які програми ви хочете встановити і запустити відповідний скрипт. Наприклад, якщо ви хочете встановити Python, то вам необхідний скрипт `install-pyton.bat`. Його можна запустити або як зазвичай подвійним кліком, або ж викликавши з командного рядка.

> Хоч у цьому зазвичай і немає необхідності, ми рекомендуємо запускати скрипти з правами адміністратора. Для цього клікніть правою кнопкою на скрипті і у меню виберіть пункт Запустити з правами адміністратора/Run as Administrator. У вас може запитати пароль від вашгого акаунту Windows.

Після запуску, має відкритися вікно терміналу, у якому буде відображатися прогрес встановлення. Зверніть увагу, що це може зайняти деякий час, протягом якого краще не займати комп'ютер тяжкими обчисленнями, а піти розімнутися чи випити чаю. Про завершення встановлення програм скрипт повідомить у вікно терміналу.

Скрипт завантажує інсталятори останніх версій з офіційних сайтів відповідних програм, тому вам необхідно бути підключеними до інтернету.

Цей процесс можна повторити для усіх потрібних вам програм. Ми рекомендуємо перезавантажити комп'ютер перед використанням встановлених програм.

Програми встановлюються у папку, в яку ви скопіювали папку зі скриптами. Наприклад, якщо ви встановили Python, то ваше дерево папок має виглядати так:

```
|-<>
  |
  |-university-tools-installer-main
    |
    |-7za.exe
    |-...
    |-README.md
  |
  |-Python
    |
    |-...
  |
  |-...
```

Після встановлення усіх необхідних програм, папку `university-tools-installer-main` можна видалити.

## Перелік скриптів та доступних програм

Наразі, ми підтримуємо встановленя наступних програм:

- Python (`install-python.bat`) ~60 Мб

Стандартний інтерпретатор Python, який вам знадобиться у першому семестрі.

- VS Code (`install-vscode.bat`) ~450 Мб

Просте IDE для розробки, що підтримує Python та С.

- git (`install-git.bat`) ~250 Мб

Популярна система контролю версій, якою ми будемо користуватися. Серед іншого, цей сайт — це місце зберігання Git-репозиторіїв.

- GCC/MinGW (`install-gcc.bat`) ~450 Мб

Компілятор GCC — один із трьох найбільш популярних компіляторів для С — і середовище MinGW для його запуску. Воно містить бібліотеки для його адекватної роботи під Windows, оскільки базово GCC створювався під Linux. Він знадобиться вам у другому семестрі.

> Крім того, ви можете встановити відразу всі з цих програм (~1 Гб), використвуючи скрипт `install-all.bat`.


## Як перевірити, що все встановлено правильно?

Для того, щоб перевірити, що все встановлено правильно, ви можете виконати наступні команди у командному рядку:

- Python

Введіть у командному рядку `python --version`. Ви маєте побачити результат, подібний наступному:

```
> python --version
Python 3.9.1
```

- GCC

Введіть у командному рядку `gcc --version`. Ви маєте побачити результат, подібний наступному:

```
> gcc --version
gcc (x86_64-win32-seh-rev0, Built by MinGW-W64 project) 8.1.0 
Copyright (C) 2018 Free Software Foundation, Inc.
```

- git

Введіть у командному рядку `git --version`. Ви маєте побачити результат, подібний наступному:

```
> git --version
git version 2.29.2.windows.3
```

- VS Code

Якщо все встановлено правильно, то запуск `Code.exe` має відкрити головне вікно програми.

## Про налаштування VS Code

Детальніше пр налаштування VS Code для роботи з різними мовами можна прочитати тут:

- Python: https://code.visualstudio.com/docs/languages/python
- C: https://code.visualstudio.com/docs/languages/cpp

# Ліцензії

Цей репозиторій поширюється за умовами ліцензії Unlicense. Деталі ви можете прочитати у фаілі LICENSE.

Файл `7za.exe` є частиною програми 7-Zip та поширюєтся на умовах ліцензії GNU LGPL. Вихідний код та інша інформація доступні на https://www.7-zip.org
