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

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_1.png" alt="Ссылка"></p>
________________________________________________________________


  
</details>



