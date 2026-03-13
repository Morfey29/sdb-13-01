**Домашнее задание к занятию «Уязвимости и атаки на информационные системы» Дойков А.М.**

Задание 1

Скачайте и установите виртуальную машину Metasploitable: https://sourceforge.net/projects/metasploitable/.

Это типовая ОС для экспериментов в области информационной безопасности, с которой следует начать при анализе уязвимостей.

Просканируйте эту виртуальную машину, используя nmap.

Попробуйте найти уязвимости, которым подвержена эта виртуальная машина.

Сами уязвимости можно поискать на сайте https://www.exploit-db.com/.

Для этого нужно в поиске ввести название сетевой службы, обнаруженной на атакуемой машине, и выбрать подходящие по версии уязвимости.

Ответьте на следующие вопросы:

    Какие сетевые службы в ней разрешены?
    Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)

**Ответ:**

![alt text](https://github.com/Morfey29/sdb-13-01/blob/main/img/1.jpg)

Сетевые службы и ссылки на уязвимости

Порт 21: FTP (vsftpd 2.3.4)

Уязвимость: Backdoor Command Execution. При отправке имени пользователя, содержащего символы :), открывается доступ к шеллу с правами root .

Ссылка на Exploit-DB: https://www.exploit-db.com/exploits/49757 

Порт 22: SSH (OpenSSH)

Уязвимость: SSH Username Enumeration. Уязвимость позволяет перебирать имена пользователей на сервере, используя некорректные пакеты или timing-атаки .

Ссылка на Exploit-DB: Модуль в Metasploit: auxiliary/scanner/ssh/ssh_enumusers 

Порт 23: Telnet (Linux TelnetD)

Уязвимость: Buffer Overflow. Уязвимость в обработчике шифрования позволяет выполнить произвольный код (CVE-2011-4862) .

Ссылка на Exploit-DB: https://www.exploit-db.com/exploits/18280/ 

Порт 139/445: Samba (smbd 3.0.20-Debian)

Уязвимость: "Username map script" Command Execution. Позволяет выполнить произвольную команду без аутентификации (CVE-2007-2447) .

Ссылка на Exploit-DB: https://www.exploit-db.com/exploits/16320 

Порт 6667: IRC (UnrealIRCd 3.2.8.1)

Уязвимость: Backdoor. Дистрибутив содержит троян, позволяющий удаленно выполнять команды (CVE-2010-2075) .

Ссылка на Exploit-DB: https://www.exploit-db.com/exploits/13853 

Порт 8180: HTTP (Apache Tomcat 5.5)

Уязвимость: Default Credentials / WAR File Deployment. Возможность зайти в менеджер Tomcat с стандартными учетными данными (tomcat/tomcat) и развернуть вредоносный WAR-файл для получения reverse shell .

Ссылка на Exploit-DB: Модуль в Metasploit: auxiliary/scanner/http/tomcat_mgr_login и exploit/multi/http/tomcat_mgr_deploy 

Порт 1099: Java RMI

Уязвимость: Insecure Default Configuration. Уязвимость позволяет выполнить код, загружая удаленные классы через RMI Registry .

Ссылка на Exploit-DB: Модуль в Metasploit: exploit/multi/misc/java_rmi_server 


Задание 2

Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

Запишите сеансы сканирования в Wireshark.

Ответьте на следующие вопросы:

    Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?
    Как отвечает сервер?

Приведите ответ в свободной форме.

**Ответ:**