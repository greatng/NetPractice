# NetPractice

## Цель данного проекта научиться  настривать межсетевые подключения между компьютерами

<details>
<summary>Level_1</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_1.png" alt="Ссылка"></p>
________________________________________________________________
  
 ### Здесь нам нужно настроить компьютеры, в рамках одной домашней сети.
  
 ### Изначально подключение не работает, так как компьютер имеет

  ```
  Interface B1
  IP : 104.39.23.12
  Mask : 255.255.255.0
  ```
  ### Из этого следует что 
  
  ```
  Network:  104.39.23.0
  Diaposon: 104.39.23.1 - 104.39.23.254
  ```
  
  ### А у Компьютера А1  ```104.93.23.17 ``` Что не входит в данный диапозон. 
  
  ###  Поэтому меняем IP у A1 на подходящий из диапозона и вуаля... Анологично со вторым компьютером
  
 
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_2.png" alt="Ссылка"></p>

</details>

<details>
<summary>Level_2</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_1.png" alt="Ссылка"></p>
________________________________________________________________

 ### Очень похоже на первое задание, только здесь чтобы компьютеры могли коммуницировать между собой, они должны быть в рамках одной сети. 
 ### Чтобы понять какая сеть, возьмем маску от А1  и IP от B1 и подсчитаем какая сеть 
  ```
  IP : 192.168.20.222
  Mask : 255.255.255.224
  ```
### Получается 
  ```
  Network:  192.168.20.192
  Diaposon: 192.168.20.193 - 192.168.20.222
  ```
### Чтобы все заработало берем любой IP из диапозона и ставим в A1, а также  меняем маску у B1 на аналогучную A1  
  
#
  
### Компьютеры С1 и D1 не могут скомуницироваться так как диапозон ```127.0.0.1 - 127.255.255.254``` используется для коммуникации с самим собой (Addresses on Loopback)
  
### Для решения этой проблемы просто берем другое адресное пространство   
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_2.png" alt="Ссылка"></p>
  
</details>



<details>
<summary>Level_3</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_1.png" alt="Ссылка"></p>
________________________________________________________________

### Здесь у нас появляется новый обьект. Сетевой коммутатор (жарг. свитч, свич от англ. switch — переключатель) — устройство, предназначенное для соединения нескольких узлов компьютерной сети в пределах одного или нескольких сегментов сети.
### Очень важно коммутатор работает в рамках одной сети  
  
### Аналогично предыдущим заданиям берем маску от C1 и  IP от  A1 и строим подходящую сеть

  ### Получается 
  ```
  Network:  104.198.133.0
  Diaposon: 104.198.133.1 - 104.198.133.126
  ```
### Далее просто заполняем любым IP из диапозона и  не забываем про маски:) 

 ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_2.png" alt="Ссылка"></p>
________________________________________________________________
  
</details>

<details>
<summary>Level_4</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_1.png" alt="Ссылка"></p>
________________________________________________________________

 ### Здесь добавляется новый обьект Маршрутизатор 
 https://hobbyits.com/naznachenie-i-funkcii-marshrutizatora-v-lokalnoj-seti/
  
   
 ### В данном задании нам нужно Соеденить двух клиентов между собой и также каждый клиент с роутером, для нас доступны 3 интрфейса подключения к роутеру
 
 ### Чтобы все зараюотало, нам нужнл чтобы Оба клиента и интерфейс роутера были все в рамках одной сети (мы берем пустой интрфейс и подбираем ему подходящий  IP и маску, такую чтобы она включала клиента A1)
  
  ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_3.png" alt="Ссылка"></p>
________________________________________________________________

  
</details>

<details>
<summary>Level_5</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_1.png" alt="Ссылка"></p>
________________________________________________________________

#### Здесь у нас появилась новая графа, давайте разберемся что это
   
  ```
      client A: Machine A
      Routes :
      ... => ...
   ```
#### Эта штука называется статическим маршрутом
#### Статический маршрут используется, когда компьютер хочет связаться с кем-то вне своей сети.
Если пункт назначения соответствует левой части (0.0.0.0/0 в этом примере, что является "по умолчанию", что означает, что он соответствует всему), он попросит правую часть (192.168.0.254 здесь) переслать сообщение  
  
#### "Правую часть" называется шлюзом, у вас же на вашем собственном компьютере (ваш интернет-провайдер роутер) : каждый раз, когда вы хотите зайти в интернет, ваш компьютер спрашивает его, потому что он единственный, кто знает, куда идти.
во-первых, вам нужно настроить "правильный сети" :  
  
#### Вот пример как это работает
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_2.png" alt="Ссылка"></p>  
  
  
#### 1)Мы вроде немного с вами разобрались, давайте попробуем решить нашу задачу, укажем статическому маршруту кому будем отправлять (всем: 0.0.0.0/0), и через какой интрфейс (18.171.197.126) 

#### 2) Также интрфейс A1 и R1 должны быть в одной сети (мы это уже умеем делать :). )
  
#### 3) Также интрфейс B1 и R2 должны быть в одной сети (мы это уже умеем делать :). )  

#### 4) Ну и последнее, нам нужно настроить статичсекий маршрут для B (задать правый параметр, путь через интрфейс R2) 
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_3.png" alt="Ссылка"></p>  
  
  
</details>




<details>
<summary>Level_6</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl6_1.png" alt="Ссылка"></p>
________________________________________________________________
  
#### Здесь мы должны настроить свзяь с интернетом  

#### 1) Для начала настроим взаимодейсвие интрфейсов A1 и  R1 в одной сети (мы это уже с вами делали)
#### 2) Далее  в router R слева указыаем что отправляем всем сетям
  
#### 3) Ну и последнее  в internet I указыаем что будем отправлять нашей сети (83.71.194.129/25)
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl6_2.png" alt="Ссылка"></p>
  
</details>

<details>
<summary>Level_7</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl7_1.png" alt="Ссылка"></p>
________________________________________________________________
  
  #### Здесь нам нужно все настроить, чтобы два компьютера общались между собой, используя два маршрутизатора
  
  #### Здесь важно чтобы не было пересечения сетей 
  
  
  #### А) Сделайте интерфейс A1 и интерфейс R11 одной и той же маской подсети
  #### Чтобы настроить клиент A, перейдите в раздел Интерфейс A1 - > Интерфейс R11.
  #### (B) Интерфейс R12 и интерфейс R21 должны иметь одну и ту же маску подсети.
  #### В конфигурации roter R1 установите значение Интерфейс R12 -> Интерфейс R21.
  #### В конфигурации ротора R2 настройте Интерфейс R21 -> Интерфейс R12.
  #### (C) Интерфейс R22 и интерфейс C1 должны иметь одну и ту же маску подсети.
  #### В конфигурации клиента C настройте Интерфейс C1 -> Интерфейс R22.
  #### (A), (B) и (C) у каждого есть разные маски подсети
  #### Поскольку маршрутизатор подключается к другой сети, отображается IP-адрес в той же сети
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl7_2.png" alt="Ссылка"></p>
  
</details>

<details>
<summary>Level_8</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl8_1.png" alt="Ссылка"></p>
________________________________________________________________
  
  
 #### Интернет-маршруты заполняют сетевой адрес сети, подключенной к интерфейсу, подключенному к Интернету
 #### Частные IP-адреса нельзя использовать, если они подключены к Интернету
 #### 10.0.0.0 ~ 10.255.255.255 (10.0.0.0/8) (Класс А)
 #### 172.16.0.0 ~ 172.31.255.255 (172.16.0.0/12) (Класс B)
 #### 192.168.0.0 ~ 192.168.255.255 (192.168.0.0/16) (Класс C)
  
  
 #### 1) Настроим ```internet I ``` чтобы он отправлял запросы через ```Interface R12```
  
 #### 2) Теперь в ```Interface R13``` укажем сеть и маску, такую же через которую посылает ```router R2 ```
  
 #### 3) Теперь в ```Interface R21``` укажем сеть с которой свзяан ```Interface R13```
  
 #### 4) Теперь в ```router R1``` укажем чтобы пакеты шли через интрфейс ```Interface R21 ```
 
 #### 5) Теперь нужно ```Interface R23``` и ```Interface R22``` разделить на две подсети ```30.12.23.1``` и ```30.12.23.17```
  
 #### 6) Теперь нужно настроить  ```client D``` и ```client С``` чтобы работали с нашими интрфейсами
 
 #### 7) Теперь нужно настроить  ```Interface D1``` и ```Interface С1``` чтобы они были в одной сети с ```Interface R23``` и ```Interface R22```
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl8_2.png" alt="Ссылка"></p>
  
</details>


<details>
<summary>Level_9</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_1.png" alt="Ссылка"></p>
________________________________________________________________
  
## 1) В первую очередь выполним Goal 3 настроить чтобы работали meson need to communicate with Internet 

####  Для этого настроим ```Client A```, ```Interface A1```, ```Interface R11``` так чтобы они были в одной сети
  
#### Чтобы мы могли коммуницировать с   ```Internet``` , пропишем путь чтобы пакеты шли в нашу сеть
  
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_2.png" alt="Ссылка"></p> 
  

  
## 2) Теперь выполним Goal 1 : meson need to communicate with ion 

####  Для этого настроим ```client B```, ```Interface  B2```, ```Interface R11``` так чтобы они были в одной сети  
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_3.png" alt="Ссылка"></p>   
  
## 3) Теперь выполним Goal 2 : cation need to communicate with gluon
 
  
####  Для этого настроим ```client C:```, ```Interface  C1```, ```Interface R22``` так чтобы они были в одной сети  
  
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_4.png" alt="Ссылка"></p>   
  
</details>




