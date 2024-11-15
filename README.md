# networking-doc.md
  CHAPTER : 9
  #  <font color="YELLOW"> NETWORKING FUNDAMENTALS </font> 
         
## <font color="blue" align ="right"><center> CHAPTER LESSONS AND NAMES OF PEOPLE DOING THE PRESENTATION
<br>
1- FUNDAMENTALS OF NETWORK PROTOCOLS  ------> TCHANKOUMI USHER PHARELL BLONDI 



2- PERSISTENT NETWORK CONFIGURATION --------> CELINE-CORALIE ENI BINA 

 

3- BASIC NETWORK TROUBLESHOOTING -----------> TEGHA ROMEO.D



4- CONFIGURE CLIENT DNS </font>-------------> CELINE-CORALIE BINA AND TCHANKOUMI USHER PHARELL BLONDI    
  <br>


   ## <font color="grey" align="right"><center> LESSON 1 : FUNDAMENTALS OF PROTOCOLS  </font>
   <br>



  Hey everyone today we will discuss about Networking. We will see how it functions and key terms related to it.
 
 <br>
   At the end of this chapter the following objectives are to be achieve
  
  <br>

You should be able to                   
<br>

-    Know what is an IP address, a netmask address , a network address and a broadcast address and also how to calculate them
-    Know how to convert an ip address from binary to decimal and vice versa
-    Understand the OSI model
-    Know the differnt protocol use to transfer data
-    Differences between IPV4 and IPV6 address


<br>


### <font color="grey"><center> INTRODUCTION </font>
<br>
 We should know that for information to be send from one computer to another.  computer in the internet  essential requirements are needed.. among this we have 
  
  <br>
<font color="grey"> NETWORKING </font>
 
 <br> 

This refer to the designing,building and conceptuatising of software for infranstructures and networks . when we are talking of computer networking this refers to the interconnection of computers across the internet 

<br>


<br>
This is the unique identifier for every device connected to the internet  ..when a device is connected to the internet the DHCP(Dynamic Host Configure protocol) gives the device an IP adress.There exist two main types of ip  address that are PRIVATE and PUBLIC ADDRESS.<br>
Being the most used PUPLIC ip address are the one assigned to each computer on the internet but it is not very efficient because due to the fact that the population is increasing day after day the public ip have become too small to handle the ip of each other so a private IP have started be used 
<br>it is functioning just like a public IP by beeing assigning to any device in the internet but slightly differerent  in a way that when a public IP is giving to any device conncted to the internet ,it is given to any device conected in a LAN

  
  
  #### IPV4  AND IPV6 ADDRESS  

  
An ip address can be divided into two main types that is the IPV4 address and the IPV6 adresss..Firstly in the begining of the days the type of IP adress used was the IPV4 address but becuse of many DHCP configuration and  alot of population an IPV6 address which can take a very large population.

 #### CONVERSION FROM DECIMAL FORMAT TO BINARY 

For an address to be converted to binary each section on the ip address is reduced to binary that is ....as an example of an ip we can have 192.168.0.123  , so here the 192 is first converted to decimal  by deviding by 2 until its lowest form and recording the remainders an then at the end record the remainders in ascending orders .. so you will do these for all the sections of the ip address and then record their value in binary ..

#### CONVERSION FROM BINARY TO DECIMAL 
  If you want to convert to decimal take each binary section and place it arrays of bits ex..lets us consider the following the following binary IPV4 address 11100011.1100111.10100000.000000000 

- firstly this will be place in rows of bits that is
                      2^7   2^6  2^5   2^4  2^3    2^2     2^1  2^0
- Now you have to place the fist section of the IP address
  
        2^7     2^6     2^5    2^4      2^3     2^2    2     2^0
  
        1      1        0     0      0        0        0    0
  
- From here you will now take the digits and multiply them by the corresponding bits on which they are placed  and then add them that is
       
       1*2^7 + 1*2^6 + 0*2^5 + 0*2^4 + 0*2^3 +  0*2^2 + 0*2 + 0*2^0 = 192
- The same steps will be done on the rest of the binary digits until finnaly you will obtain a complete ip address in decimal


  Other exmaples of address are
1- NETMASK ADDRESS: This address is used to determine how many bits of IP address is the network address it is having a default value of 255.255.255.0.In the network address 02 bits are automatically assigned  that is the "0" for the network address and the 255 at the end for the broadscast adress. Each section on the netmask address is made up of 8 bits.
  
2- NETWORK ADDRESS : This is a special address that is used to define a paricular network.This address is obtained by  doing a bitwise AND (&) between the IP and the NETMASK ADDRESS  that is

   Let us take an ip address that is 192.168.0.128 and a Netmask address that is 225.255.255.0. So these addresses will be converted to   binary and  then bitwise AND (&) that is  255 converted to binary will give 11111111  and 192 will give 11000000
  
   so this can reprensented as

       1 1 1 1 1 1 1 1  
       1 1 0 0 0 0 0 0
Then a bitwise AND($) between the 02 will give me a result of  11000000 and that when converted to binary will give a reult of 192, the same process with be done and the second section of both address will be take..that is 

 168 on the ip address when converted to decimal will give 10101000 and the 255 on the netmask will still give 11111111..then the sane process will be done  

       1 1 1 1 1 1 1 1 
       1 0 1 0 1 0 0 0
 So when this two are bitwise AND (&) the result obtained is 10101000 that will still give me 168 when converted to decimalwhen we take the third section we have 255 given 11111111 and 0 given 00000000 this will give 00000000 when bitwise AND (&) so we will return a 0 on the third section and for the last section we will have 0000000 from the netmask address and  128 on the Ip address last coloumn will give 10000000 and this will still give 0 when bitwise
  Then at the end we will have 192.168.0.0 which will represent our Network address.We can realise that the first 03 section of the Ip address is given us our network address.This is the reason why an IP address is divided into 02 main part the network address that are the first 03 coloumn and the host address that is on the last coloumn.

3- BROADCAST ADDRESS : This is a special address that is used to send packets to other devices on the same network .This can be obtain by applying a not on the netmask adress and doing an OR operation on the IP address 

that is having an IP address 192.168.0.128 converted to binary give 11000000.10101000.00000000.10000000 and then negating the Netmask will give instead of 11111111.11111111.11111111.00000000 will be converted to 00000000.00000000.00000000.11111111 and then an OR operation will be aply with the IP address and the result obtained will be our Broadcast address.
  
   More information about our addresses can be seen through the ifconfig command 

   Know we will see how data is being transfer through the network and we will use one of the great model that has been used till up date called the OSI MODEL.

#### OSI MODEL(OPEN SYSTEM INTERCONNECTION)

This model ia a conception model of how internet works and is divided into seven layers. We can have  the following diagram for the different level of OSI MODEL  
 
   ![image](https://github.com/user-attachments/assets/e55cfd01-ccb8-4a8c-8c8d-92441a21c0aa) 

WE should note that  the OSI model is functioning fron sender to receiver and from receiver to sender .SO the explanation under the 7 layers are as follow 

- ##### APPLICATION LAYER

When data is  send from sender to reciever this is the first layer through which information pass..This layer function in sending data to the reiver and the reciever on its side will send back the end user .
   it layer provide the protocols that allow  software /apps to transmit data exmaples are 
HTTPS and HTTP,
FTP ,
POP & SMTP,
DNS,
TELNET,
DHCP,
-SMTP

- ##### PRESENTATION LAYER

This layer ensures that data is prepared for the application layer (receiving side) or for the network layer (sending side).It is responsible of some tasks like 
- data translation
- Encryption & decryption of data
- Compression of data
- Other data presentation items

- ##### SESSION LAYER

This layer creates and maintains the sessions that 02 systems neede inorder to speek to each other ... This layer take in charge the mode of data transmition being  duplex,half duplex and full duplex . This layer defines 
- when sessions are created and opened
- How long sessions remain open to sucessfully exchange data
- when to close sessions

- ##### TRANSPORT LAYER

  Also called as the heart of the OSI layer , this layer use the TCP(Transmition control protocol) and the UDP(User datagram protocol ) ,to manage network traffic between systems and ensure correct data transfers they function also in the followiing ways
  - On the sending side, it takes data from the session layer and breaks it into segments for the network layer.
  - On the receiving side, it reassembles the segments from the network layer and passes them on to the session layer.

This layer also handles flow control and error control, regulates transmission speed and requests retransmissions if needed. As we said this layer deals with this 02 maiin protocol that we will discuss below 
Vide
 - ###### Transmition control protocol

The transmission control protocol (TCP) is defined as a connection-oriented communication protocol that allows computing devices and applications to send data via a network and verify its delivery, forming one of the crucial pillars of the global internet.

 ![image](https://github.com/user-attachments/assets/5826d112-2d60-4c50-83cc-ae34a7083108) 
 
   example of  transmission control protocol in real life scenarios are 
  - email
  - text messaging
  - file transfers

- ###### USER DATAGRAM PROTOCOL
User datagram protocol (UDP) is a message-oriented communication protocol that allows computing devices and applications to send data via a network without verifying its delivery, which is best suited to real-time communication and broadcast systems.

![image](https://github.com/user-attachments/assets/5ec01dc3-b2bf-454d-be10-59fdec715531)

 examples of User datagram control protocol in real life are 
 - DNS lookup
 - Online games
 - Videos streaming

Both of these uses  PORT which is used to reach the corresponding device on a particular network

- ##### NETWORK LAYER

This layer decides which path the data will take so  as to reach the receiver in case it is coming from .its responsible for breaking up transport layer segmenst into smaller network packets foer tranmission and for reassembling those packets on the receining systems 

- ##### DATA LINK LAYER

This layer defines the format of data on the network .It and uses Media acess control for flow control and multiplexing between the 02 systems 

- ##### PHYSICAL LAYER

   This layer describes the  physical connection between devices in a network, here this layer deal with the material through which data is being received  or transfer . examples of device in the  physical connection layer is coax/fiber,wireless,hubs,repeaters
   SO 


this processses generalise how data is being transmitted on the network 


 
  











   
   

  
   
    



    
        
 























































   
