# Просмотр таблицы MAC-адресов коммутатора  
## Задание  
> "Часть 1"  
* Создание и настройка сети
> "Часть 2"
* Изучение таблиц MAC-адресов коммутатора

## Топология  

![image](https://github.com/user-attachments/assets/38a5911e-73f7-4cee-a424-edca3ad8be8d)  

## Таблица адресации  
Устройство | Интерфейс | IP-адрес | Маска
---------- | --------- | -------- | -----
S1 | Vlan1 | 192.168.1.11 | 255.255.255.0
S2 | Vlan2 | 192.168.1.12 | 255.255.255.0
PC-A | NIC | 192.168.1.1 | 255.255.255.0
PC-B | NIC | 192.168.1.2 | 255.255.255.0

## Решение  

* Настройка имени устройств в соответствии с топологией

S1
 
![image](https://github.com/user-attachments/assets/bf7db104-a3fc-4b91-a1c3-15ed07feb620)  

S2

![image](https://github.com/user-attachments/assets/2070f0be-cbbd-46cd-b222-0e0e4779a8bc)

* Настройка IP-адреса, как указано в таблице адресации

S1
 
![image](https://github.com/user-attachments/assets/f78e8f35-327d-45c5-80cc-746737b19c28)  

S2
 
![image](https://github.com/user-attachments/assets/3c10e06d-d5a1-4460-bed5-e7ce5803b201)

* Назначаем cisco в качестве паролей консоли и VTY

S1
 
![image](https://github.com/user-attachments/assets/20c0d3e6-bae3-41ef-bf7c-7d6408a4865f)  

S2

![image](https://github.com/user-attachments/assets/8470eae2-1aa4-497b-a68f-92a2c7b09b1a)  

* Назначаем class в качестве пароля доступа к привилегированному режиму EXEC

S1  

![image](https://github.com/user-attachments/assets/6dc0bf60-c444-4ff1-9b4b-b62a04e13edb)  


S2  

![image](https://github.com/user-attachments/assets/63ce3340-ddcf-4700-baf5-930e5af652b7)

* Настойка truk между коммутаторами

S1  

![image](https://github.com/user-attachments/assets/529c0de5-329a-4f84-ac35-9f2f6ede3da9)

S2  

![image](https://github.com/user-attachments/assets/b30b8d67-fee7-4395-95ef-3401c4e5fd43)

__Записываем MAC-адреса сетевых устройств__  

PC-A  

![image](https://github.com/user-attachments/assets/0b7f5a37-3311-47f8-9524-545652f38bf3)

PC-B

![image](https://github.com/user-attachments/assets/9f5ef41b-7032-4e6d-8ac9-00eee1c2aa74)

МАС-адрес коммутатора S1 Fast Ethernet 0/1: 

![image](https://github.com/user-attachments/assets/90f17cff-e475-4d88-8a14-6c63103c9235)  

МАС-адрес коммутатора S2 Fast Ethernet 0/1:  

![image](https://github.com/user-attachments/assets/bdd8d50f-01d5-41df-b42e-91a3371591f9)  

Смотрим на S2 таблицу MAC-адресов  

![image](https://github.com/user-attachments/assets/77d33d3b-4b3c-4b2e-be33-e4cadabe6695)

**Записаны ли в таблице МАС-адресов какие-либо МАС-адреса?**  
_Да_  
**Какие МАС-адреса записаны в таблице?**  

_PC-B, PC-A, S1_

![image](https://github.com/user-attachments/assets/39c7b76a-5d94-4b79-911f-d04833f92159)

  
**С какими портами коммутатора они сопоставлены и каким устройствам принадлежат?**  

![image](https://github.com/user-attachments/assets/a8c464ac-8bec-4e96-80a3-55289cdda9f0)

**Если вы не записали МАС-адреса сетевых устройств в шаге 1, как можно определить, каким устройствам принадлежат МАС-адреса, используя только выходные данные команды show mac address-table?**  
_Посмотреть, какие MAC-адреса связаны с какими портами__

**Работает ли это решение в любой ситуации?**  
_Нет, если MAC-адреса не были записаны ранее или таблица пуста, определить принадлежность устройств нельзя. Таблица показывает только активные MAC-адреса, которые передавали трафик. Если MAC-адреса статические или таблица не обновлялась, информация может быть устаревшей._

__Очищаем таблицу MAC-адресов коммутатора S2 и отображаем таблицу MAC-адресов__  

![image](https://github.com/user-attachments/assets/e620d0a2-cfea-4a39-84c2-66c9ccbb7da3)  

Cколько пар IP- и МАС-адресов устройств было получено через протокол ARP?

![image](https://github.com/user-attachments/assets/a3a68a75-eade-4ed0-8073-ff627df8861f)

**Из командной строки PC-B отправьте эхо-запросы на компьютер PC-A, а также коммутаторы S1 и S2.**  
_От всех ли устройств получены ответы?_  
_Да_

![image](https://github.com/user-attachments/assets/30a7285f-1934-4145-9a4c-96c8d500f5d4)  
![image](https://github.com/user-attachments/assets/344a6f45-0922-4602-aa47-fe8d0632a0fd)  
![image](https://github.com/user-attachments/assets/098f909e-d298-412b-8a34-fbc4fd598228)

**На коммутаторе S2, введим команду show mac address-table**  
**Добавил ли коммутатор в таблицу МАС-адресов дополнительные МАС-адреса?**

![image](https://github.com/user-attachments/assets/444ac636-fda8-412d-bb0f-6a3a4b97429c)

**На компьютере PC-B откройте командную строку и еще раз введите команду arp -a**  
**Появились ли в ARP-кэше компьютера PC-B дополнительные записи для всех сетевых устройств, которым были отправлены эхо-запросы?**  

![image](https://github.com/user-attachments/assets/1894899c-0d4e-48c0-abb3-a9098aa4e40d)


**В сетях Ethernet данные передаются на устройства по соответствующим МАС-адресам. Для этого коммутаторы и компьютеры динамически создают ARP-кэш и таблицы МАС-адресов. Если компьютеров в сети немного, эта процедура выглядит достаточно простой. Какие сложности могут возникнуть в крупных сетях?**  
_В больших сетях колличество утройств значительно больше, что требует больших ресурсов памяти и процессорного времени для обработки и обновления данных. Увеличение широковещательного тарифка может увеличить нагрузку на сеть и снизить ее производительность. При большом количестве узлов увеличивается вероятность коллизий и задержек в передаче данных, а также усложняется управление таблицами коммутации, что может привести к снижению пропускной способности и увеличению времени отклика. Большие таблицы MAC-адресов сложнее контролировать, что повышает риск ошибок, конфликтов адресов и атак типа MAC-флудинга._

