[Настройки Git](#настройка-git)
[Базовые команды в консоли](#базовые-команды-в-консоли)
[Базовые команды в Git](#базовые-команды-в-Git)


# **Настройка Git**
```bash
$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках

$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email 
```
---

# **Базовые команды в консоли**


### **Навигация**
* `pwd` (от англ. **p**rint **w**orking **d**irectory, «показать рабочую папку») — покажи, в какой я папке;
* `ls` (от англ. **l**i**s**t directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
* `ls -a` — показать также скрытые файлы и папки, названия которых начинаются с символа `.`;
* `cd project` (от англ. **c**hange **d**irectory, «сменить директорию») — перейди в папку `project`;
* `cd project/html` — перейди в папку `html`, которая находится в папке `project`;
* `cd ..` — перейди на уровень выше, в родительскую папку;
* `cd ~` — перейди в домашнюю директорию (`/Users/Username`);
* `cd /` — перейди в корневую директорию.


### **Работа с файлами и папками**

#### **Создание**
* `touch index.html` (от англ. touch, «коснуться») — создай файл `index.html` в текущей папке;
* `touch index.html style.css script.js` — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
* `mkdir project` (от англ. **m**a**k**e **dir**ictory, «создать директорию») — создай папку с именем `project` в текущей папке;
* `mkdir -p dir/dir_inside/project` — создай целую структуру дерикторий, используя флаг `-p`;

#### **Копирование и перемещение**
* `cp file.txt ~/my-dir` (от англ. **c**o**p**y, «копировать») — скопируй файл или список файлов (перечисленных через пробел) в другое место;
* `mv file.txt ~/my-dir` (от англ. **m**o**v**e, «переместить») — перемести файл или список файлов (перечисленных через пробел) в другое место.

#### **Чтение**
* `cat file.txt` (от англ. con**cat**enate and print, «объединить и распечатать») — распечатай содержимое текстового файла `file.txt`.

#### **Удаление**
* `rm about.html` (от англ. **r**e**m**ove, «удалить») — удали файл about.html;
* `rmdir images` (от англ. **r**e**m**ove **dir**ectory, «удалить директорию») — удали папку `images` (если она пустая);
* `rm -r project` (от англ. **r**e**m**ove, «удалить» + **r**ecursive, «рекурсивный») — удали папку `project` и всё, что она содержит.


### **Полезные возможности**
* Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (`&&`).
* У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (`↑`) и вниз (`↓`).
* Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать `Tab`. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке `dev`. Начните вводить `cd first` и дважды нажмите `Tab`. Если папка `first-project` есть внутри `dev`, командная строка автоматически подставит её имя. Останется только нажать `Enter`.
---

# **Базовые команды в Git**


### **Инициализация репозитория**
* `git init` (от англ. **init**ialize, «инициализировать») — инициализируй репозиторий;
* `rm -rf .git` — «разгитить» папку (удаляем скрытую подпапку .git со всем ее содержимым).
    * ключ `-r` (от англ. **r**ecursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;
    * ключ `-f` (от англ. **f**orce — «заставить») избавит нас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».

### **Синхронизация локального и удалённого репозитория**
* `git remote add origin URL (HTTPS или SSH)` (от англ. **remote**, «удалённый» + **add**, «добавить») — привяжи локальный репозиторий к удалённому с URL;
* `git remote -v` (от англ. **v**erbose, «подробный») — проверь, что репозитории действительно связались;
* `git push -u origin master` (от англ. **push**, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.
* `git push` (от англ. **push**, «толкать») — загрузи коммиты в удалённый репозиторий после того, как он был привязан с помощью флага `-u`.

### **Подготовка файла к коммиту**
* `git add todo.txt` (от англ. **add**, «добавить») — подготовь файл todo.txt к коммиту;
* `git add --all` (от англ. **add**, «добавить» + **all**, «всё») — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;
* `git add .` — подготовь к коммиту текущую папку и все файлы в ней.

### **Создание и публикация коммита**
* `git commit -m "Комментарий к коммиту."` (от англ. **commit**, «совершать», фиксировать» + **m**essage, «сообщение») — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения сделаны;
* `git push` (от англ. **push**, «толкать») — добавь изменения в удалённый репозиторий.

### **Просмотр информации о коммитах**
* `git log` (от англ. **log**, «журнал [записей]») — выведи подробную историю коммитов;
* `git log --oneline` (от англ. **log**, «журнал [записей]» + oneline, «одной строкой») — покажи краткую информацию о коммитах: сокращённый хеш и сообщение.

### **Просмотр состояния файлов**
* `git status` (от англ. **status*, «статус», «состояние») — покажи текущее состояние репозитория.
`git status` показывает только следующие состояния файлов:
    * `staged` (`Changes to be committed`, «Изменения, которая необходимо закоммитить» в выводе `git status`);
    * `modified` (`Changes not staged for commit`, «Изменения, не подготовленные для коммита»);
    * `untracked` (`Untracked files`, «Неотслеживаемые файлы»);
* `git status --ignored` — покажи текущее состояние репозитория, включая файлы папки `.gitignored`.

### **Добавление изменений в последний коммит**
* `git commit --amend --no-edit` (от англ. amend, «исправить») — добавь изменения к последнему коммиту и оставь сообщение прежним;
* `git commit --amend -m "Новое сообщение"` — измени сообщение к последнему коммиту на `Новое сообщение`.

### **«Откат» файлов и коммитов**
* `git restore --staged hello.txt` (от англ. restore, «восстановить») — переведи файл `hello.txt` из состояния `staged` обратно в `untracked` или `modified`;
* `git restore hello.txt` — верни файл `hello.txt` к последней версии, которая была сохранена через `git commit` или `git add`;
* `git reset --hard <commit hash>` (от англ. reset, «сброс», «обнуление» + hard, «суровый») — удали все незакоммиченные изменения из staging и «рабочей зоны» вплоть до указанного коммита.

### **Просмотр изменений**
* `git diff` (от англ. **diff**erence, «отличие», «разница») — покажи изменения в «рабочей зоне», то есть в `modified`-файлах;
* `git diff --staged` — покажи изменения, которые добавлены в `staged`-файлах;
* `git diff a9928ab 11bada1` — выведи разницу между двумя коммитами.



### **Файл `HEAD`**
Файл `HEAD` (англ. «голова», «головной») — один из служебных файлов папки `.git`. Он указывает на коммит, который сделан последним (то есть на самый новый).

### **Статусы файлов в Git**
#### **Статусы** `untracked`/`tracked`, `staged` и `modified`
* `untracked` (англ. «неотслеживаемый»)  
Новые файлы в Git-репозитории помечаются как `untracked`, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. У `untracked`-файла нет предыдущих версий, зафиксированных в коммитах или через команду `git add`.

* **`staged`**/`indexed`/`cached` (англ. «подготовленный»)  
После выполнения команды `git add` файл попадает в staging area (от англ. stage — «сцена», «этап [процесса]» и area — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`.

* `tracked` (англ. «отслеживаемый»)  
Состояние `tracked` — это противоположность `untracked`. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы, которые были добавлены в staging area командой `git add`. То есть все файлы, в которых Git так или иначе отслеживает изменения.
modified (англ. «изменённый»)

* Состояние `modified` означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.

### **Игнорирование файлов в Git**
`.gitignore` — это файл в корне репозитория, в который указывают все файлы, которые нужно игнорировать (по одному имени на строку).
#### **Шаблоны**
* **Комментарий** (`#`)  
Если строка начинается с `#`, то это комментарий, и `.gitignore` не будет его учитывать.
    ```bash
    # вот так можно писать комментарии;
    # они ничего не значат для .gitignore,
    # но они могут быть полезны, чтобы понять, зачем было добавлено то или иное правило 
    ```

* **Звёздочка** (`*`)  
Символ звёздочки (`*`) соответствует любой строке, включая пустую.
    ```bash
    # игнорировать все файлы, которые заканчиваются на .jpeg
    *.jpeg
    
    # игнорировать все файлы "tmp" во всех подпапках папки docs
    docs/*/tmp 
    ```
    
* **Вопросительный знак** (`?`)  
Вопросительный знак `?` соответствует одному любому символу.
    ```bash
    file?.txt
    # будут проигнорированы, например, файлы: fileA.txt, file1.txt и тд.
    ```

* **Квадратные скобки** (`[…]`)  
Квадратные скобки, как и вопросительный знак, соответствуют одному символу. При этом символ не любой, а только из списка, который указан в скобках.
    ```bash
    # игнорировать файлы file0.txt, file1.txt и file2.txt
    # при этом не игнорировать file3.txt, file4.txt, ...
    file[0-2].txt
    ```
    В скобках можно либо перечислить символы (`[abc]`), либо задать диапазон (`[a-z]`).
    
* **Слеш** (`/`)  
Если шаблон в .gitignore начинается со слеша (`/`), то Git проигнорирует файлы или каталоги только в корневой директории.
    ```bash
    # игнорировать todo.txt в корне репозитория
    /todo.txt
    
    # для сравнения: spam.txt будет игнорироваться во всех папках
    spam.txt
    ```

    Если шаблон заканчивается слешем, то правило применится только к папке.
    ```bash
    # игнорировать папку build
    build/
    ```

* **Парные звёздочки** (`**`)  
Функция парных звёздочек (**) похожа на функцию одинарной (*). Отличие в том, как они работают с вложенными папками. Двойная звёздочка может соответствовать любому количеству таких папок (в том числе нулю). Одинарная может соответствовать только одной.
    ```bash
    # игнорировать файлы "docs/current/tmp", "docs/old/tmp",
    # а также "docs/old/saved/a/b/c/d/tmp"
    # и даже "docs/tmp", потому что ноль вложенных папок тоже подходит
    docs/**/tmp
    
    # игнорировать только "docs/current/tmp" и "docs/old/tmp"
    # файл "docs/old/saved/a/b/c/d/tmp" не попадает в правило
    docs/*/tmp 
    ```

* **Восклицательный знак** (`!`)  
Любое правило в файле .gitignore можно инвертировать с помощью восклицательного знака (`!`).
    ```bash
    # игнорировать все JPEG-файлы
    *.jpeg
    
    # но только не мем с Doge
    !doge.jpeg 
    ```

