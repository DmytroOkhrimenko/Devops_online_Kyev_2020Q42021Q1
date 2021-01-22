Task2
Task assignment.
1) Analyze the structure of the /etc/passwd and /etc/group file, what fields are
present in it, what users exist on the system? Specify several pseudo-users, how
to define them?

[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/31.png)
etc/passwd  состоит из имени пользователя, пароля, юзер-идентификатора, идентификатора-груп, хом-директории юзера, имя программы интерпритатора
Например dima:x:1000:1000:dima,,,:/home/dima:/bin/bash
         arrivederlo:x:1001:1001:,,,:/home/arrivederlo:/bin/bash
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/31a.png)
etc/group  состоит из имени группы, пароля , идентификатор для группы , к какой группе принадлежит пользоваетль
Например		 dima:x:1000:
                        arrivederlo:x:1001:
Псевдоюзеров можно опрежелить по именам: daemon bin adm nobody  sshd.
		 
2) What are the uid ranges? What is UID? How to define it?

uid - это простое числовое обозначение отдельного пользователя. Обычно это положительное число, не более
чем 65535 . Некоторые идентификаторы зарезервированы для специального использования. К ним относятся 0 (Root),
1-999 (демоны, псевдопользователи, системные и зарезервированные пользователи), 1000+ (обычные пользователи).
В примере выше у пользователя Dima uid =1000


3) What is GID? 
gid - определяет идентификатор или имя группы, к которой принадлежит пользователь.
-g выбрать группу для логина
How to define it?
cat /etc/passwd
dima:x:1000:1000(группа пользователя):dima,,,:/home/dima:/bin/bash 


4) How to determine belonging of user to the specific group?
Можно использовать команду cat /etc/group 
dima:x:1000:group111   пользователь дима пренадлежит группе group111


5) What are the commands for adding a user to the system? What are the basic
parameters required to create a user?
useradd
Вам понадобиться выбрать: имя пользователя, пароль, есть возможность присоединить его к какой-то группе. 
Вам будет присвоено: уникальный идентификатор, появиться директория пользователя итд

6) How do I change the name (account name) of an existing user?
usermod -l ввести новое имя

7) What is skell_dir? What is its structure?
skel_dir - содержит файлы, которые необходимо скопировать в домашний каталог нового пользователя.

8) How to remove a user from the system (including his mailbox)?
userdel -r username

9) What commands and keys should be used to lock and unlock a user account?
passwd -l user_name          usermod -L user_name             chage -E 1 username
passwd -u user_name          usermod -U user_name             chage -E -1 username


10) How to remove a user's password and provide him with a password-free
login for subsequent password change?
sudo passwd -d имя пользователя

11) Display the extended format of information about the directory, tell about
the information columns displayed on the terminal.
ls -la /etc/
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/32.png)
первая строка общее количество блоков диск пространства 1164
первая колонка это тип файлового обьекта(например d директория) + права файла
Количество жестких ссылок. Далее идут имена владельца, группы, размер, дата последнего изменения и имя файла

12) What access rights exist and for whom (i. e., describe the main roles)?
Briefly describe the acronym for access rights.
Владелец - набор прав для владельца файла, пользователя, который его
 создал или сейчас установлен его владельцем. Обычно владелец имеет все права, чтение, запись и выполнение.
Группа - любая группа пользователей, существующая в системе и привязанная к файлу. 
Но это может быть только одна группа и обычно это группа владельца, хотя для файла можно назначить и другую группу.
Остальные - все пользователи, кроме владельца и пользователей, входящих в группу файла.

Изначально каждый файл имел три параметра доступа. Вот они:

Чтение - разрешает получать содержимое файла, но на запись нет.
Для каталога позволяет получить список файлов и каталогов, расположенных в нем;
Запись - разрешает записывать новые данные в файл или изменять существующие, 
а также позволяет создавать и изменять файлы и каталоги;
Выполнение - вы не можете выполнить программу, если у нее нет флага выполнения. 
Этот атрибут устанавливается для всех программ и скриптов, именно с помощью него система может понять, 
что этот файл нужно запускать как программу.

    --- - нет прав, совсем;
    --x - разрешено только выполнение файла, как программы но не изменение и не чтение;
    -w- - разрешена только запись и изменение файла;
    -wx - разрешено изменение и выполнение, но в случае с каталогом, вы не можете посмотреть его содержимое;
    r-- - права только на чтение;
    r-x - только чтение и выполнение, без права на запись;
    rw- - права на чтение и запись, но без выполнения;
    rwx - все права;
    --s - установлен SUID или SGID бит, первый отображается в поле для владельца, второй для группы;
    --t - установлен sticky-bit, а значит пользователи не могут удалить этот файл.

Спец пава:

    SUID - если этот бит установлен, то при выполнении программы, id пользователя, 
	от которого она запущена заменяется на id владельца файла. Фактически, это позволяет 
	обычным пользователям запускать программы от имени суперпользователя;
	
    SGID - этот флаг работает аналогичным образом, только разница в том, что пользователь 
	считается членом группы, с которой связан файл, а не групп, к которым он действительно принадлежит.
	Если SGID флаг установлен на каталог, все файлы, созданные в нем, будут связаны с группой каталога, 
	а не пользователя. Такое поведение используется для организации общих папок;
	
    Sticky-bit - этот бит тоже используется для создания общих папок. Если он установлен, то пользователи 
	могут только создавать, читать и выполнять файлы, но не могут удалять файлы, принадлежащие другим пользователям.


13) What is the sequence of defining the relationship between the file and the
user?
 Любой пользователь ( процесс ) Linux по отношению к любому файлу может выступать в трех ролях:
 как хозяин ( u ser), как член группы, которой принадлежит файл ( g roup), и как посторонний ( o ther), никаких 
 отношений собственности на этот файл не имеющий. Строка атрибутов – это три тройки " rwx ", описывающие права 
 доступа к файлу хозяина этого файла (первая тройка, " u "), группы, которой принадлежит файл (вторая тройка, " g ")
 и посторонних (третья тройка, " o "). Если в какой-либо тройке не хватает буквы, а вместо нее стоит " - ", значит, 
 пользователю в соответствующей роли будет в соответствующем виде доступа отказано.
 
 При выяснении отношений между файлом и пользователем, запустившим процесс, роль определяется так:

    Если UID файла совпадает с UID процесса, пользователь – хозяин файла
    Если GID файла совпадает с GID любой группы, в которую входит пользователь, он – член группы, которой принадлежит файл.
    Если ни UID, ни GID файла не пересекаются с UID процесса и списком групп, в которые входит запустивший его пользователь,
	этот пользователь – посторонний.


14) What commands are used to change the owner of a file (directory), as well
as the mode of access to the file? Give examples, demonstrate on the terminal.
Права доступа изменяются с помощью трех команд: chown ( ch ange own er, сменить владельца),
 chgrp ( ch ange gr ou p, сменить группу ) и chmod с расширенным форматом параметра: перед частью,
 определяющей доступ (перед знаком " + " или " - "), могут быть перечислены роли
 " u ", " g ", " o " и " a " ( a ll, что соответствует " ugo "), доступ для которых изменяется. 
 Кроме того, при задании доступа можно вместо " + " и " - " использовать " = ", тогда для заданных
 ролей указанные способы доступа разрешаются, а неуказанные – запрещаются. Вместо пары команд 
 chown хозяин файл ; chgrp группа файл можно применять одну: chown хозяин:группа файл, которая изменяет 
 одновременно и UID, и GID файла (каталога, ссылки и т. п.).

[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/33.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/33a.png)

15) What is an example of octal representation of access rights? Describe the
umask command.
Пример rwxrwxrwx(8штук) 
В операционных системах Linux и Unix все новые файлы создаются с набором разрешений по умолчанию. 
Утилита umask позволяет просматривать и устанавливать маску режима создания файла, который 
определяет разрешения бит для вновь создаваемых файлов или каталогов.

    Владелец: rwx=4+2+1 = 7
    Группа: r-x=4+0+1 = 5
    Другое: r-x=4+0+1 = 5


16) Give definitions of sticky bits and mechanism of identifier substitution. Give
an example of files and directories with these attributes.

Sticky Bit в основном используется для того чтобы избежать удаления папки и ее содержимого другими пользователями.
у них есть права на запись в содержимое папки. Если для папки включен бит залипания, содержимое папки
удаляются только владельцем, который их создал, и пользователем root. Никто другой не может удалить данные других пользователей в этой
папке (где установлен Sticky Bit). Это мера безопасности, позволяющая избежать удаления важных папок и их
содержимого (подпапки и файлы)
chmode +t file.txt или /home/dima/test добавить
chmode -t file.txt или /home/dima/test убрать
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.2/Screens/34.png)


17) What file attributes should be present in the command script?
append and immutable.
в команде chatt применяется 3 атрибута +добавить   -удалить     =сохранить 
