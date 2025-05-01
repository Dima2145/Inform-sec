# Inform-sec
## Задание 1
* Скачайте и установите виртуальную машину Metasploitable: https://sourceforge.net/projects/metasploitable/.
* Это типовая ОС для экспериментов в области информационной безопасности, с которой следует начать при анализе уязвимостей.
* Просканируйте эту виртуальную машину, используя nmap.
* Попробуйте найти уязвимости, которым подвержена эта виртуальная машина.
* Сами уязвимости можно поискать на сайте https://www.exploit-db.com/.
* Для этого нужно в поиске ввести название сетевой службы, обнаруженной на атакуемой машине, и выбрать подходящие по версии уязвимости.
* Ответьте на следующие вопросы:

* Какие сетевые службы в ней разрешены?
* Какие уязвимости были вами обнаружены? (список со ссылками: достаточно трёх уязвимостей)
* Приведите ответ в свободной форме.
## Решение 1
![Снимок242](https://github.com/user-attachments/assets/c12ca605-52f6-4ab6-bafb-23f4eee3f30d)   

Zabbix Agent (порт 10050/tcp

https://ubuntu.com/security/CVE-2017-2824

8090/tcp  open  opsmessaging

https://nvd.nist.gov/vuln/detail/cve-2023-46604

SSH (порт 22/tcp)

https://access.redhat.com/security/cve/cve-2023-38408


## Задание 2
* Проведите сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

* Запишите сеансы сканирования в Wireshark.

* Ответьте на следующие вопросы:

* Чем отличаются эти режимы сканирования с точки зрения сетевого трафика?
* Как отвечает сервер?
* Приведите ответ в свободной форме.

## Решение 2
Режим SYN - режим опроса портов по протоколу TCP, когда посылается пакет с флагом SYN на определенный порт
Возможные ответы:

SYN/ACK(порт открыт)
RST(порт закрыт)
нет ответа (порт отфильтрован)
FIN - пакеты отправляются с флагом FIN. Такое сканирование может быть менее заметным и может помочь обойти некоторые фаерволы
Возможные ответы:

No response received (even after retransmissions) open|filtered
TCP RST packet closed
ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13) filtered
Xmas - пакеты отправляются с флагами FIN, PSH, and URG.
Возможные ответы:

No response received (even after retransmissions) open|filtered
TCP RST packet closed
ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13) filtered
UDP - сканирование портов происходит по протоколу UDP.
Возможные ответы:

Any UDP response from target port - open
No response received (even after retransmissions) - port open|filtered
ICMP port unreachable error (type 3, code 3) - port closed
Other ICMP unreachable errors (type 3, code 1, 2, 9, 10, or 13) - port filtered
