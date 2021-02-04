
TASK5.3
Part1
1. How many states could has a process in Linux?

    *состояния выполнения
    *состояния ожидания
    *состояния готовности 
	
2. Examine the pstree command. 
Make output (highlight) the chain (ancestors) of the current
process.  Надеюсь правильно понял вопрос...
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/1.png)

3. What is a proc file system?
procfs -  виртуальная UNIX-подобная файловая система, которая предоставляет информацию
о процессах и другую системную информацию в иерархическом виде. Позволяет получить доступ 
к информации из ядра о системных процессах. Необходима для выполнения таких команд как ps, w, top.

4. Print information about the processor (its type, supported technologies, etc.).
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/2.png)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/2a.png)

5. Use the ps command to get information about the process. The information should be as
follows: the owner of the process, the arguments with which the process was launched for
execution, the group owner of this process, etc.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/3a.png)

6. How to define kernel processes and user processes?
ps aux | head   процесы ядра будут показаны в квадратных скобках [  ]
процес  init     прародитель всех процессов имеет pid1

7. Print the list of processes to the terminal. Briefly describe the statuses of the processes.
What condition are they in, or can they be arriving in?
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/5.png)
R - процесс выполняется или готов к выполнению (состояние готовности)
D - процесс в "беспробудном сне" - ожидает дискового ввода/вывода
T - процесс остановлен (stopped) или трассируется отладчиком
S - процесс в состоянии ожидания (sleeping)
Z - процесс-зобми
< - процесс с отрицательным значением nice
N - процесс с положительным значением nice
I - процес бездействует

Из состояния готовности процесс может перейти только в состояние выполнения 
Из состояния выполнения процесс может перейти либо в состояние ожидания или состояние готовности 
Из состояния ожидания в готовность


8. Display only the processes of a specific user.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/4.png)

9. What utilities can be used to analyze existing running tasks (by analyzing the help for the ps
command)?
ps -e или  ps -A  или ps -r
или top  для просмотра процессов в реальном времени

10. What information does top command display?
top (table of processes) — консольная команда, которая выводит список 
работающих в системе процессов и информацию о них. 
По умолчанию она в реальном времени сортирует их по нагрузке на процессор. 


11. Display the processes of the specific user using the top command.
top -u  имя_юзера
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/6.png)


12. What interactive commands can be used to control the top command? Give a couple of examples.
    [1] Отобразить всю статистику по всем ядрам.
    [c] Абсолютный путь расположения модуля команды и её аргументы.
    [h] Вывести справку о программе.
    [k] Уничтожить процесс. Программа запрашивает у вас код процесса и сигнал, который будет ему послан.
    [M] Сортировать по объёму используемой памяти.
    [n] Изменить число отображаемых процессов. Вам предлагается ввести число.
    [P] Сортировать по загрузке процессора.
    [r] Изменить приоритет процесса.
    [u] Сортировать по имени пользователя.
    [Z] Выбрать цвет подсветки.
    [z] Подсветить работающие процессы.
    [Пробел] Немедленно обновить содержимое экрана.
    
    
13. Sort the contents of the processes window using various parameters (for example, the
amount of processor time taken up, etc.)
top P
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/7.png)


14. Concept of priority, what commands are used to set priority?

nice
renice


15. Can I change the priority of a process using the top command? If so, how?
top r


16. Examine the kill command. How to send with the kill command
process control signal? Give an example of commonly used signals.
kill -s(сигнал)
kill id_process
kill -9
kill -15

17. Commands jobs, fg, bg, nohup. What are they for? Use the sleep, yes command to
demonstrate the process control mechanism with fg, bg.

jobs Отобразить список текущих фоновых задач.
bg   Продолжить выполнение программы в фоновом режиме.
fg или fg 1    Вывести задачу из фонового режима

top
ctrl+z остановить задачу
jobs   вывести список задач работающих в фоновом режиме
fg или fg 1 возобновит работу команды top
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/8.png)

Команда bg предназначена для восстановления работы остановленных процессов (задач) в фоновом режиме.
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/8a.png)

nohup   Данная команда позволяет запускать процессы, который будут оторваны от терминала если, терминал будет закрыт.


Part2

1. Check the implementability of the most frequently used OPENSSH commands in the MS
Windows operating system. (Description of the expected result of the commands +
screenshots: command – result should be presented)
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/9.png)


2. Implement basic SSH settings to increase the security of the client-server connection 
[](https://Screens2.github.com/).
![image of Dmytro](https://github.com/DmytroOkhrimenko/Devops_online_Kyev_2020Q42021Q1/blob/main/m5/Task5.3/Screens/10.png)
Мложно повысить безопасность несколькими способами:
Port 2222  сменить порт, по умолчанию 22  ssh ubuntu@192.168.0.46 -p 2222
PermitRootLogin no   отключить root-доступ
PasswordAuthentication no  отключить парольную аутентификацию
PermitEmptyPasswords no  отключить возможность залогинится с пустым паролем
Protocol 2   работать с протоколом ssh2
PubkeyAuthentication yes аутентификация на основе SSH2 RSA-ключей 
или 
sudo nano /etc/ssh/sshd_config   файл конфигурации можно раскоментить вручную

3. List the options for choosing keys for encryption in SSH. Implement 3 of them.
ssh-keygen -t rsa   создать паруключей
ssh root@REMOTE_SERVER mkdir -p .ssh создать каталог на удаленном сервере
cat /root/.ssh/id_rsa.pub | ssh root@REMOTE_SERVER 'cat >> /root/.ssh/authorized_keys'   скопировать ключ на сервер


4. Implement port forwarding for the SSH client from the host machine to the guest Linux
virtual machine behind NAT.
Not done

5*. Intercept (capture) traffic (tcpdump, wireshark) while authorizing the remote client on the
server using ssh, telnet, rlogin. Analyze the result.
Not done

