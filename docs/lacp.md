# Настройка LACP на CentOS + Cisco


# Настройка CentOS
* Проверим наличие bonding модуля: `lsmod |grep -i bonding`

Если ответ пустой, то включим модуль: `modprobe bonding`

Создадим интерфейс:
```
/etc/sysconfig/network-scripts/ifcfg-bond1

DEVICE=bond1
TYPE=Ethernet
ONBOOT=yes
USERCTL=no
NM_CONTROLLED=no
MTU=1500
BOOTPROTO=static
IPADDR=179.254.0.2
PREFIX=16
DNS1=<DNS_IP>
BONDING_OPTS="mode=802.3ad miimon=100 lacp_rate=fast xmit_hash_policy=layer2+3"
```
Сделаем бэкап интерфейсов:
```
cd /etc/sysconfig/network-scripts/
mkdir backup-ifcfg
cp ifcfg-en{0..1}  backup-ifcfg/
```
Имена интерфейсов можно посмотреть командой `ip a`

Переведем интерфейсы к bond1:
```
/etc/sysconfig/network-scripts/ifcfg-en0

DEVICE=en0
BOOTPROTO=none
ONBOOT=yes
SLAVE=yes
USERCTL=no
NM_CONTROLLED=no
MASTER=bond1
```
Аналогичным будет конфиг интерфейса `en1`.

После этого необходимо сделать перезапуск сети: `service network restart`

# Настройка Cisco

Действия необходимо выполнять в режиме конигурации: `conf t`

## Создадим портгруппу 

```yml
interface Port-channel1
 description portname
 switchport access vlan XXXX
 switchport mode access
```
## Изменим первый интерфейс:
```yml
interface GigabitEthernet1/0/2
 switchport access vlan XXX
 description portname1
 switchport mode access
 channel-group 1 mode active
```
## Второй интерфейс
```yml
interface GigabitEthernet2/0/2
 description portname2
 switchport access vlan XXX
 switchport mode access
 channel-group 1 mode active
```
## Включение порта в портгруппу

`channel-group 1 mode active`