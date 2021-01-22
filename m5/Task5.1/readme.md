Task1.Part1

1) Log in to the system as root.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/1.png)

2) Use the passwd command to change the password. Examine the basic
parameters of the command.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/1a.png) 
What system file does it change *? 
/etc/passwd 

3) Determine the users registered in the system, as well as what commands they
execute. What additional information can be gleaned from the command
execution?
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/2.png)

4) Change personal information about yourself.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/4.png)

5) Become familiar with the Linux help system and the man and info commands.
Get help on the previously discussed commands, define and describe any two
keys for these commands. Give examples.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/5.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/5a.png)

6) Explore the more and less commands using the help system.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/6a.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/6b.png)
View the contents
of files .bash* using commands.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/6c.png)

7) * Describe in plans that you are working on laboratory work 1. Tip: You should
read the documentation for the finger command.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/7.png)

8) * List the contents of the home directory using the ls command, define its files
and directories. Hint: Use the help system to familiarize yourself with the ls
command.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/8.png)



Task1.Part2

1) Examine the tree command. Master the technique of applying a template, for
example, display all files that contain a character c, or files that contain a
specific sequence of characters.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/9.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/9a.png)
 List subdirectories of the root directory up to
and including the second nesting level.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/9b.png)

2) What command can be used to determine the type of file (for example, text or
binary)? Give an example.
file *
file -i some-file
file -bi *
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/10.png)

3) Master the skills of navigating the file system using relative and absolute paths.
How can you go back to your home directory from anywhere in the filesystem?

cd ~

4) Become familiar with the various options for the ls command. Give examples
of listing directories using different keys. Explain the information displayed on
the terminal using the -l and -a switches.
ls=list 
ls -s=size  -i индексы
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/11.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/10a.png)
ls -a=all показывает показывает файлы и папки в директории в том числе скрытые
ls -l показывает разрешения файла, показывает UID и GID пользователя, дату, время, имя файла,
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/11.png)

5) Perform the following sequence of operations:
- create a subdirectory in the home directory;
- in this subdirectory create a file containing information about directories
located in the root directory (using I/O redirection operations);
- view the created file;
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/12.png)
- copy the created file to your home directory using relative and absolute
addressing.
- delete the previously created subdirectory with the file requesting removal;
- delete the file copied to the home directory.

cp /home/dima/Testdir/test.out /home/dima/test.out  абс
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/12a.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/12b.png)

6) Perform the following sequence of operations:
- create a subdirectory test in the home directory;
- copy the .bash_history file to this directory while changing its name to
labwork2;
- create a hard and soft link to the labwork2 file in the test subdirectory;
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/13.png)
- how to define soft and hard link, what do these
concepts;
soft: Имеет сходство с ярлыком. Содержит адрес ссылаемого файла. При удалении ссылаемого файла ссылка останеться но будет бесполезна.
hard: Файл размещен только в определенном месте жесткого диска. На файл могут ссылаться несколько ссылок. При перемещении ссылки она 
будет все равно работать 
- change the data by opening a symbolic link. What changes will happen and why
При изменении в файле относительной ссылки изменения вносяться в ссылаемый файл.
- rename the hard link file to hard_lnk_labwork2;
- rename the soft link file to symb_lnk_labwork2 file;
- then delete the labwork2. What changes have occurred and why?
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/13a.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/13b.png)
При удалении исходного ссылаемого файла-
Жесткая ссылка все еще активна(указывает на нужный участок диска и сама является файлом),
 а симводическая не работает(она содержала только адрес файла).

7) Using the locate utility, find all files that contain the squid and traceroute
sequence.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/14.png)


8) Determine which partitions are mounted in the system, as well as the types of these partitions.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/15.png)

9) Count the number of lines containing a given sequence of characters in a given file.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/16.png)

10) Using the find command, find all files in the /etc directory containing the
host character sequence.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/17.png)

11) List all objects in /etc that contain the ss character sequence. How can I
duplicate a similar command using a bunch of grep?
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/18.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/18a.png)

12) Organize a screen-by-screen print of the contents of the /etc directory. Hint:
You must use stream redirection operations.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/19.png)

13) What are the types of devices and how to determine the type of device? Give
examples.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/20.png)
Символьные (байт-ориентированные) устройства читают и записывают данные в виде потока байтов. 
Сюда входят последовательные и параллельные порты, накопители на магнитной ленте, терминалы и звуковые платы.

Блочные (блок-ориентированные) устройства читают и записывают данные блоками фиксированного размера. 
В отличие от символьных устройств блочные устройства предоставляют произвольный доступ к своим данным. 
В качестве примера можно назвать жесткий диск.

14) How to determine the type of file in the system, what types of files are there?
file * для опрежеления типа файлов в директории
file имя искомого файла
По распечатке списка файлов командой ls можно легко определить тип файла. 
Первый символ сообщает нам о типе, а именно '-' обозначает обычный файл, 
'd' — каталог, 'p' — именованный канал, 'l' — символическую ссылку, 
'c' и 'b' — символьные и блочные файлы устройств, 's' — сокет, 'D' - дверь. 

15) * List the first 5 directory files that were recently accessed in the /etc
directory.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.1/Screens/21.png)
