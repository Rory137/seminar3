# **Инструкция по работе с GIT**
![Эмблема Git](git.png)

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.
## **Создание репозитория**

Для того, чтобы создать (инициализировать) новый репозиторий нужно находясь в соотвеествующей папке через терминал ввести команду: 
        
    git init
       
  ## **Проверка состояния репозитория** 

  Для того, чтобы посмотреть состояние репозитория используется команда: 
        
         git status
 Для это необходимо в папке с репозиторием написать команду описанную выше, и вы увидите были ли изменения в файлах, или их не было.

  ## **Создание коммитов**

  ### ***GIT ADD***
  Для добавления изменений в коммит используется команда:

    git add  
 Для использование команды напишите: 
    
      git add <filename>   
 C указанием имени вашего файла  
    
  ### ***Создание коммита*** 
  Для того, чтобы создать коммит(сохранения) необходимо выполнить команду: 
    
    git commit
После чего откроется текстовый редактор, для описания нашего коммита.
    
 #### ***git commit -m "message"*** 
   Для быстрого создания коммита с комментарием используется команада:
      
      git commit -m "message"
 При передаче параметра ***-m*** текстовый редактор не открывается, а используется подставленный комментарий.   
    
  #### ***git commit -a***
 Для выполнение коммита состояния со всеми изменениями в рабочем каталоге используется команда:  
      
    git commit -a 
Эта команда включает только изменения отслеживаемых файлов (тех, которые были в какой-то момент добавлены в историю с помощью команды *git add*).    
    
  #### ***git commit -am "message"***
  Команда с параметрами ***-a*** и ***-m***. Эта комбинация параметров создает коммит всех проиндексированных изменений и добавляет к коммиту подставленный комментарий. Для этого используется команда:
     
     git commit -am "message

  ## **Сравнение изменений**   
  Для анализа измений в текущем состояние репозитория используется команда:

    git diff
 Это функция, анализирующая два входных набора данных и отображающая различия между ними.   

  ## **Просмотр истории коммитов**

  ### **git log** 
   Для просмотра истории коммитов которые были выполнены ранее используется команда:
    
    git log
  ### **git log --oneline**  
     
     Для более удобного просмотра истории коммитов используется команда:

      git log --oneline
  Флаг ***--oneline*** записывает каждый коммит в одну строку. По умолчанию отображаются только идентификаторы коммитов и первые строки комментариев к ним.
    
  ### **--all**

  Для просмотра истории коммитов по всем ветками испольется флаг ***--all***
    
  Пример команды с флагом ***--all***
    
    git log --all --oneline
Данная команда позволяет посмотреть историю коммитов по всем веткам, где каждый коммит записан в одну строку.

    git log --all
Данная команда позволяет посмотреть историю коммитов по всем веткам. 

## **Ветвление в Git**

Ветвления нужны для того, чтобы программисты могли вести совместную работу над проектом и не мешать друг другу при этом. При создании проекта, Git создает базовую ветку. Она называется master веткой. Она считается центральной веткой, т.е. в ней содержится основной код приложения.

### **Просмотр всех веток**

Чтобы просмотреть список всех имеющихся веток нужно ввести команду: 

    git branch

### **Создание новой ветки** 

Для того чтобы создать новую ветку необходимо ввести команду:

    git branch <branch name>
### **Переключение веток** 
Для того чтобы переключиться из любой нашей ветки на любую другую созданную ветку нужно использовать команду: 

    git checkout <branch name> 

### **Cлияние веток** 
Для того чтобы произвести слияние веток необходимо ввести команду:


    git merge <branch name>
Где имя ветки, та ветка с которой мы собираемся производить слияние.
Слияние принимает содержимое ветки источника и объединяет их с целевой веткой. В этом процессе изменяется только целевая ветка. История исходных веток остается неизменной.
#### **Исправления ошибок во время слияния веток**
 Для того чтобы исправить конлифкт во время слияние веток , где есть неразрешённые конфликты слияния, перечисляется как неслитое. В конфликтующие файлы *Git* добавляет специальные маркеры конфликтов, чтобы вы могли исправить их вручную или же воспользовались встроенным функционалом который предоставляет ***"Visual Studio Code"*** 
 Исправление при помощи ***"Visual Studio Code"***  представлены на изображение ниже.
 ![Скриншот исправление ошибки VSC](git_debug.png)
* **Accept Current Change** - Кнопка которая применяет изменения из нашей текущей ветки 
* **Accept Incoming Change** - Кнопка которая применяет изменения с побочной ветки
* **Accept Both Changes** - Кнопка которая применяет изменения из двух наших веток
* **Compare Changes** - Кнопка для сравнения измений с двух веток


## **Игнорирование файлов**

Игнорируемые файлы отслеживаются в специальном файле
    
    .gitignore
который регистрируется в корневом каталоге репозитория. В Git нет специальной команды для указания игнорируемых файлов: вместо этого необходимо вручную отредактировать файл __*.gitignore*__, чтобы указать в нем новые файлы, которые должны быть проигнорированы. Файлы 
__*.gitignore*__ содержат шаблоны, которые сопоставляются с именами файлов в репозитории для определения необходимости игнорировать эти файлы.

## **Работа с удаленными репозиториями**

### __Как подключиться к удаленному репозитарию?__

Для загрузки данных в удаленный репозитариq сначала нужно к нему подключиться. Пользователь может создать собственный удаленный репозиторий на GitHub или другом подобном сервисе. Это занимает некоторое время, однако в дальнейшем полностью себя оправдывает, тем более, что подобные службы имеют пошаговые инструкции для правильно выполнения нужных действий.

Для того, чтобы связать созданный нами локальный репозитарий с удаленным, выполним такую команду:

    git remote add origin <link to our remote repository>

На скришоте ниже можем ознакомиться с примером нашей ссылки: 
![Наш пример](example_git.png)

Главный репозиторий принято называть origin.

### __Как отправить изменения в удаленный репозиторий__
Теперь, когда у нас в локальном репозитарии создан коммит и мы подключились к удаленному, можем отправить его на сервер. Мы это будем делать каждый раз, когда хотим обновить данные в удаленном репозитарии.

Отправка коммита осуществляется с помощью команды 
      
      git push origin main

которая имеет два параметра - имя удаленного репозитория (в нашем случае origin) и ветку, в которую необходимо внести изменения (main — это ветка по умолчанию для всех репозиториев).

### **Клонирование удаленного репозитория**

Если у других пользователей возникла необходимость клонировать удаленный репозитарий, они могут получить полностью работоспособную копию при помощи команды clone:

    git clone <link remote repository>


GitHub автоматически создаст новый локальный репозитарий в виде удаленного на собственном сервере.

### __Запрос изменений из удаленного репозитория__ 

В случае, если другим пользователям нет необходимости делать клон удаленного репозитария, а нужно просто получить информацию об изменениях, это можно сделать с помощью команды

    git pull 

Она скачивает новые изменения из удаленного репозитория , после чего делает merge веток.


Так-же для связи с удаленным репозиторием сущесвует команда 

    git fetch 
Она делает тоже самое что и __*git pull*__ но без merge веток.

## __Изменения названия основной ветки__ 
Если наша основная ветка имеет отличное от **main** название , то можно воспользоваться командой:

               git branch -M main
               
Для соблюдение новых стандаров ***Git*** .

## __Создание ответвлений fork + pull__
### __FORK__ 
Если вы хотите вносить свой вклад в уже существующие проекты, в которых у нас нет прав на внесения изменений путём отправки (push) изменений, вы можете создать своё собственное ответвление (fork) проекта. Это означает, что GitHub создаст вашу собственную копию проекта, данная копия будет находиться в вашем пространстве имён и вы сможете легко делать изменения путём отправки (push) изменений.

Таким образом, проекты не обеспокоены тем, чтобы пользователи, которые хотели бы выступать в роли соавторов, имели право на внесение изменений путём их отправки (push). Люди просто могут создавать свои собственные ветвления (fork), вносить туда изменения, а затем отправлять свои внесённые изменения в оригинальный репозиторий проекта путём создания запроса на принятие изменений (Pull Request), сами же запросы на принятие изменений (Pull Request) будут описаны далее. Запрос на принятие изменений (Pull Request) откроет новую ветвь с обсуждением отправляемого кода, и автор оригинального проекта, а так же другие его участники, могут принимать участие в обсуждении предлагаемых изменений до тех пор, пока автор проекта не будет ими доволен, после чего автор проекта может добавить предлагаемые изменения в проект.

Для того, чтобы создать ответвление проекта, зайдите на страницу проекта и нажмите кнопку «Создать ответвление» («Fork»), которая расположена в правом верхнем углу.

Через несколько секунд вы будете перенаправлены на собственную новую проектную страницу, содержащую вашу копию, в которой у вас есть права на запись.

### __PULL__
pull request — предложение изменения кода в чужом репозитории.

Вы делаете форк чужого репозитория (который иногда и сам может быть форком) → производите изменения в своём форке → посредством pull request предлагаете изменения владельцам репозитория, чей форк Вы сделали. На GitHub pull request в публичный репозиторий может осуществить любая/ой зарегистрированная/ый участница/участник.