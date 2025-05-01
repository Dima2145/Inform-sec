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
![Снимок253](https://github.com/user-attachments/assets/2148e833-2755-45e2-be6b-febca97295f2)

![Снимок247](https://github.com/user-attachments/assets/d42fe4f3-b05c-478d-91a6-1bd2c94bb3f5)

CVE-2010-4478 - https://vulners.com/cve/CVE-2010-4478;  
SSV:60292 - https://vulners.com/seebug/SSV:60292;  
CVE-2022-2795 - https://vulners.com/cve/CVE-2022-2795.  

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

* SYN/ACK(порт открыт)  
RST(порт закрыт)  
нет ответа (порт отфильтрован)

![Снимок247](https://github.com/user-attachments/assets/bf7f6101-1f10-49b0-9ff0-dfa2f7b892b5)

![Снимок246](https://github.com/user-attachments/assets/0d0616a7-a01b-4573-a7c6-460a07e50137)

* FIN - пакеты отправляются с флагом FIN. Такое сканирование может быть менее заметным и может помочь обойти некоторые фаерволы
  Возможные ответы: 
No response received (even after retransmissions) open|filtered  
TCP RST packet closed  
ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13) filtered


![Снимок249](https://github.com/user-attachments/assets/f4bc8c28-e3c1-44b6-8a18-b285e87d7690)
![Снимок248](https://github.com/user-attachments/assets/368ba6c1-df94-4da8-8d27-4c633ddd3fc7)

* Xmas - пакеты отправляются с флагами FIN, PSH, and URG.   
Возможные ответы:  
No response received (even after retransmissions) open|filtered  
TCP RST packet closed  
ICMP unreachable error (type 3, code 1, 2, 3, 9, 10, or 13) filtered

![Снимок251](https://github.com/user-attachments/assets/5c84134e-0b43-4795-98ad-0a79d0faff78)
![Снимок250](https://github.com/user-attachments/assets/17cc23fb-457f-4eae-bf44-b440be9a46c8)


* UDP - сканирование портов происходит по протоколу UDP.
* Возможные ответы:  
Any UDP response from target port - open  
No response received (even after retransmissions) - port open|filtered  
ICMP port unreachable error (type 3, code 3) - port closed  
Other ICMP unreachable errors (type 3, code 1, 2, 9, 10, or 13) - port filtered

![Снимок252](https://github.com/user-attachments/assets/6fa89445-f377-4667-b59b-bdfccc1569f9)


