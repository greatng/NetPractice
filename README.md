# NetPractice

## The purpose of this project is to learn how to configure internet connections between computers

<details>
<summary>Level_1</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_1.png" alt="Ссылка"></p>
________________________________________________________________
  
 ### Here we need to set up computers within the same home network.
  
 ### Initially, the connection does not work because the computer has

  ```
  Interface B1
  IP : 104.39.23.12
  Mask : 255.255.255.0
  ```
  ### It follows that
  
  ```
  Network:  104.39.23.0
  Diaposon: 104.39.23.1 - 104.39.23.254
  ```
  
  ### And Computer A1 has ```104.93.23.17 ``` Which is not included in this range.
  
  ### Therefore, we change the IP of A1 to a suitable one from the range and voila ... Similarly with the second computer
  
 
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl1_2.png" alt="Ссылка"></p>

</details>

<details>
<summary>Level_2</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_1.png" alt="Ссылка"></p>
________________________________________________________________

 ### Very similar to the first task, only here, in order for computers to communicate with each other, they must be within the same network.
 ### To understand which network, take the mask from A1 and IP from B1 and calculate which network
  ```
  IP : 192.168.20.222
  Mask : 255.255.255.224
  ```
### It turns out
  ```
  Network: 192.168.20.192
  Diaposon: 192.168.20.193 - 192.168.20.222
  ```
### To make it work, we take any IP from the range and set it to A1, and also change the mask of B1 to the same A1
  
#
  
### Computers C1 and D1 cannot communicate because the range ```127.0.0.1 - 127.255.255.254``` is used to communicate with itself (Addresses on Loopback)
  
### To solve this problem, we simply take a different address space
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl2_2.png" alt="Ссылка"></p>
  
</details>



<details>
<summary>Level_3</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_1.png" alt="Ссылка"></p>
________________________________________________________________

### Here we have a new object. Network switch (slang. switch, switch from the English. switch - switch) - a device designed to connect several nodes of a computer network within one or more network segments.
### It is very important that the switch works within the same network
  
### Similar to the previous tasks, we take the mask from C1 and IP from A1 and build a suitable network

  ### It turns out
  ```
  Network: 104.198.133.0
  Diaposon: 104.198.133.1 - 104.198.133.126
  ```
### Next, just fill in any IP from the range and don't forget about masks :)

 ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl3_2.png" alt="Ссылка"></p>
________________________________________________________________
  
</details>

<details>
<summary>Level_4</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_1.png" alt="Ссылка"></p>
________________________________________________________________
### A new Router object is added here
 https://hobbyits.com/naznachenie-i-funkcii-marshrutizatora-v-lokalnoj-seti/
  
   
 ### In this task, we need to Connect two clients to each other and also each client to a router, 3 interfaces for connecting to a router are available for us
 
 ### In order for everything to work, we need both clients and the router interface to be all within the same network (we take an empty interface and select a suitable IP and mask for it, such that it includes client A1)
  
  ________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl4_3.png" alt="Ссылка"></p>
________________________________________________________________

  
</details>

<details>
<summary>Level_5</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_1.png" alt="Ссылка"></p>
________________________________________________________________

#### Here we have a new column, let's see what it is
   
  ```
      client A: Machine A
      Routes :
      ... => ...
   ```
#### This thing is called a static route
#### A static route is used when a computer wants to contact someone outside its network.
If the destination matches the left side (0.0.0.0/0 in this example, which is "default", which means it matches everything), it will ask the right side (192.168.0.254 here) to forward the message
  
#### The "right side" is called the gateway, on your own computer (your ISP router): every time you want to access the internet, your computer asks it because it's the only one that knows where go.
First, you need to set up the "correct network" :
  
#### Here is an example of how it works
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_2.png" alt="Link"></p>
  
  
#### 1) We sort of figured it out a bit, let's try to solve our problem, specify the static route to whom we will send (to everyone: 0.0.0.0/0), and through which interface (18.171.197.126)
  
#### 2) Also, A1 and R1 interfaces must be in the same network (we already know how to do this :). )
  
#### 3) Also, the B1 and R2 interfaces must be on the same network (we already know how to do this :). )

#### 4) And finally, we need to set up a static route for B (set the right parameter, the path through the R2 interface)
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl5_3.png" alt="Ссылка"></p>  
  
  
</details>




<details>
<summary>Level_6</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl6_1.png" alt="Ссылка"></p>
________________________________________________________________
  
#### Here we have to set up internet connection

#### 1) First, let's set up the interaction between the A1 and R1 interfaces in the same network (we already did this with you)
#### 2) Next, in router R on the left, specify what we send to all networks
  
#### 3) Well, the last thing in internet I indicate what we will send to our network (83.71.194.129/25)
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl6_2.png" alt="Ссылка"></p>
  
</details>

<details>
<summary>Level_7</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl7_1.png" alt="Ссылка"></p>
________________________________________________________________
  
#### Here we need to configure everything so that two computers communicate with each other using two routers
  
  #### Here it is important that there is no intersection of networks
  
  
  #### A) Make interface A1 and interface R11 the same subnet mask
  #### To set up client A, go to Interface A1 -> Interface R11.
  #### (B) R12 interface and R21 interface must have the same subnet mask.
  #### In roter R1 configuration, set R12 Interface -> R21 Interface.
  #### In the R2 rotor configuration, configure Interface R21 -> Interface R12.
  #### (C) R22 interface and C1 interface must have the same subnet mask.
  #### In client C configuration, configure Interface C1 -> Interface R22.
  #### (A), (B) and (C) each have different subnet masks
  #### Since the router is connected to a different network, the IP address on the same network is displayed
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl7_2.png" alt="Ссылка"></p>
  
</details>

<details>
<summary>Level_8</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl8_1.png" alt="Ссылка"></p>
________________________________________________________________
  
  
 #### Internet routes populate the network address of the network connected to the interface connected to the Internet
 #### Private IP addresses cannot be used if they are connected to the Internet
 #### 10.0.0.0 ~ 10.255.255.255 (10.0.0.0/8) (Class A)
 #### 172.16.0.0 ~ 172.31.255.255 (172.16.0.0/12) (Class B)
 #### 192.168.0.0 ~ 192.168.255.255 (192.168.0.0/16) (Class C)
  
  
 #### 1) Set up ```internet I ``` to send requests via ```Interface R12```
  
 #### 2) Now in ```Interface R13``` we specify the network and mask, the same through which ```router R2 ``` sends
  
 #### 3) Now in ```Interface R21``` specify the network with which ```Interface R13``` is connected
  
 #### 4) Now in ```router R1``` we specify that the packets go through the interface ```Interface R21 ```
 
 #### 5) Now you need to split ```Interface R23``` and ```Interface R22``` into two subnets ```30.12.23.1``` and ```30.12.23.17```
  
 #### 6) Now we need to configure ```client D``` and ```client C``` to work with our interfaces
 
 #### 7) Now you need to configure ```Interface D1``` and ```Interface C1``` to be on the same network as ```Interface R23``` and ```Interface R22```
  
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl8_2.png" alt="Ссылка"></p>
  
</details>


<details>
<summary>Level_9</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_1.png" alt="Ссылка"></p>
________________________________________________________________
  
## 1) First of all, let's configure Goal 3 to work meson need to communicate with Internet

#### To do this, configure ```Client A```, ```Interface A1```, ```Interface R11``` so that they are on the same network
  
#### So that we can communicate with the ```Internet``` , we will write the path so that the packets go to our network
  
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_2.png" alt="Ссылка"></p> 
  

  
## 2) Now execute Goal 1 : meson need to communicate with ion

#### To do this, configure ```client B```, ```Interface B2```, ```Interface R11``` so that they are on the same network
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_3.png" alt="Link"></p>
  
## 3) Now execute Goal 2 : cation need to communicate with gluon
 
  
#### To do this, configure ```client C:```, ```Interface C1```, ```Interface R22``` so that they are on the same network

#### You also need to configure ```client D: gluon:```, ```Interface D1```, ```Interface R23``` so that they are on the same network
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_4.png" alt="Link"></p>
 
## 4) Goal 4 : meson need to communicate with gluon

#### To do this, configure ```router R2: boson```, ```Interface R21```, ```Interface R13``` so that they are on the same network
  
#### You also need to set the gateway in ```router R1: proton```
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_5.png" alt="Link"></p>
 
## 5) As we can see, since we configured it correctly, we also got Goal 5 : ion need to communicate with cation
  
## 6) Goal 6 : cation need to communicate with Internet
  
#### To do this, configure ```router R1: proton```, ```internet I: Internet``` (We will write all the paths)
    
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl9_6.png" alt="Ссылка"></p>  
  
</details>


<details>
<summary>Level_10</summary>

________________________________________________________________

<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_1.png" alt="Ссылка"></p>
________________________________________________________________
  
## 1) Goal 1 : Host one need to communicate with Host two
  
#### To do this, configure ```Interface H21```, ```Interface H11``` so that they are on the same network
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_2.png" alt="Link"></p>

## 2) Goal 2 : Host three need to communicate with Host four
  
#### To do this, configure ```Interface R23```, ```Interface R22``` so that they are on the same network
  
#### Also ```Interface H31```, ```client H3: Host three``` so that they are on the same network 
  
  
<p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_3.png" alt="Link"></p>
  
## 3) Goal 3 : Host one need to communicate with Internet
  
#### To do this, change ```internet I: Internet ``` so that all traffic goes to our networks
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_4.png" alt="Link"></p>
 
## 4) Goal 4 : Host one need to communicate with Host four
  
#### To do this, configure ```Interface R13``` so that they are on the same network
  
#### We also decided Goal 7
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_5.png" alt="Link"></p>
  
## 5) Goal 5 : Host two need to communicate with Host three
  
   #### To do this, configure ```router R1: Router one``` so that packets go to all
  
  <p><img src="https://github.com/ifanzilka/NetPractice/blob/master/image/lvl10_6.png" alt="Link"></p>
  
</details>

If I helped you, put an star)



