# Команды Git  
---  
### Навигация:
  * **pwd** (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;
  * **s** (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
  * **ls -a** — покажи также скрытые файлы и папки, названия которых начинаются с символа .;
  * **cd** first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;
  * **cd first-project/html** — перейди в папку html, которая находится в папке first-project;
  * **cd ..** — перейди на уровень выше, в родительскую папку;
  * cd ~  — перейди в домашнюю директорию (/Users/Username);
  * **cd /** — перейди в корневую директорию.  

---  
### Работа с файлами и папками:  

#### Создание:  
  * **touch** index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;
  * **touch index.html style.css script.js** — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
  * **mkdir second-project** (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.  

#### Копирование и перемещение:  

  * **cp file.txt ~/my-dir** (от англ. copy, «копировать») — скопируй файл в другое место;
  * **mv file.txt ~/my-dir** (от англ. move, «переместить») — перемести файл или папку в другое место.  

#### Чтение:  
* **cat file.txt** (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.

#### Удаление:
* **rm about.html** (от англ. remove, «удалить») — удали файл about.html;
* **rmdir images** (от англ. remove directory, «удалить директорию») — удали папку images;
* **rm -r second-project** (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.

#### Полезные возможности
* Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (**&&**).
* У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (**↑**) и вниз (**↓**).
* Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать **Tab**. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
* Например, вы находитесь в папке dev. Начните вводить **cd first** и дважды нажмите **Tab**. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.

#### Инициализация репозитория:
* **git init** (от англ. initialize, «инициализировать») — инициализируй репозиторий.

#### Подготовка файла к коммиту:
* **git add todo.txt** (от англ. add, «добавить») — подготовь файл todo.txt к коммиту;
* **git add --all** (от англ. add, «добавить» + all, «всё») — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;
* **git add .** — подготовь к коммиту текущую папку и все файлы в ней.

#### Создание коммита:
* **git commit -m** "Комментарий к коммиту." (от англ. commit, «совершать», «фиксировать» + message, «сообщение») — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения внесены. 

#### Отправить изменения на удалённый репозиторий — git push
* **git push**

В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории, так же и здесь нужно дополнительно связать ветки.
**git push -u origin main** 


#### Просмотр информации о коммитах:
* **git log** (от англ. log, «журнал [записей]») — выведи подробную историю коммитов.

#### Просмотр состояния файлов:
* **git status** (от англ. status, «статус», «состояние») — покажи текущее состояние репозитория.
С этим набором команд вы сможете самостоятельно инициализировать проект и начать отслеживать в нём изменения. Фундамент знаний о Git заложен!

* **ls -la .ssh/ #** вывод списка созданных ключей.

* Для генерации SSH-пары можно использовать программу **ssh-keygen**. Откройте терминал и введите следующую команду:
  **$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"**

Готово! Теперь осталось проверить, что ключи действительно сгенерировались. Для этого вызовите следующую команду:
  **ls -a ~/.ssh**

* **git remote add** Привязать удалённый репозиторий к локальному.
Откройте консоль, перейдите в каталог локального репозитория и введите команду  **git remote add** (от англ. remote — «удалённый» и add — «добавить»).
Пример:  
 **$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git**

* Убедиться, что репозитории связаны, —  **git remote -v**

* Клонировать репозиторий —  **git clone**
Убедитесь в том, что репозитории связаны, командой git remote -v.

Хеш — идентификатор коммита
---
В процессе работы с Git вам будет часто встречаться понятие «хеш коммита». Эти странные строчки с бессмысленным (на первый взгляд) набором букв и цифр вы могли видеть, когда вызывали команду git log и выводили историю коммитов.

__Хеширование__ (от англ. hash, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. fingerprint).

__Информация о коммите__ — это набор данных: когда был сделан коммит, содержимое файлов в репозитории на момент коммита и ссылка на предыдущий, или родительский (англ. parent), коммит. Git хеширует (преобразует) эту информацию с помощью алгоритма SHA-1 (от англ. Secure Hash Algorithm — «безопасный алгоритм хеширования») и получает для каждого коммита свой уникальный хеш — результат хеширования.
