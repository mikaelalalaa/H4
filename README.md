# H4

Tunkeutumistestaus kurssin kotiläksy H4 Intelligence cap. Alkuperäisen tehtävä anto löytyy [opttajan sivuilta.](https://terokarvinen.com/2022/tunkeutumistestaus-ict4tn027-3010-syksylla-2022/#h4-intelligence-cap)

## z)  Lue artikkelit/katso videot ja muistiinpanot

[€ Santos et al: The Art of Hacking (Video Collection)](https://learning.oreilly.com/videos/the-art-of/9780135767849/9780135767849-SPTT_04_00/)


[Lyon 2009: Nmap Network Scanning](https://nmap.org/book/nmap-overview-and-demos.html)

[]()


[]()

[]()


# Miten nmap toimii? Testejä, liikenteen sieppaamista snifferillä (wireshark) ja tuloksien analysointi.

Harjoituksissa tehdään paljon porttiskannausta niin katsotaan aluksi että molemmista koneista on netti pois päältä. Se saadaan varmistettua `ping` komennolla.

Molemmista konesta saatiin `network is unreachable` eli voidaan aloittaa harjoitusten tekeminen.

![image](https://user-images.githubusercontent.com/93308960/202796458-c6bfa503-5027-43a9-83b3-28a07885be64.png)



## a) nmap TCP connect scan -sT

Aloitettiin TCP yhteyden skannaamisella, laitoin wiresharkin taustalle ja ajoin komennon `sudo nmap -sT -p 80 192.168.56.107`, jotta ei tulis liikaa dataa niin kohdensin skannauksen yhteen porttiin eli -p 80.

![image](https://user-images.githubusercontent.com/93308960/202801825-4cc2d399-4130-42a2-82e1-e00c345a152a.png)

TCP yhteyden skannaamisella luodaan täys yhteys kohteeseen 

![image](https://user-images.githubusercontent.com/93308960/202801786-68446e01-0563-4b6b-ab0c-fe1cf26b6588.png)


## b) nmap TCP SYN "used to be stealth" scan, -sS

Skannataan SYN portteja. Wireshark taakselle käyntiin ja ajettiin komento `sudo nmap -sS -p 80 192.168.56.107`

![image](https://user-images.githubusercontent.com/93308960/202802112-27aafb5d-915b-4460-bc05-79fde6907c8a.png)


![image](https://user-images.githubusercontent.com/93308960/202802062-2387e935-768c-4841-8382-2ddfec3dc016.png)


## c) nmap ping sweep -sn

Otin tähän esimerkkinä komennon `sudo nmap -sn 192.168.0/24`. Tässä ei portti skannata vain katsotaan mitä host koneita on kyseisessä verkossa. Tuloksesta voidaan päätellä

 *  IP-osoite
 *  MAC osite
 *  Onko host käynnissä vai ei

![image](https://user-images.githubusercontent.com/93308960/202803042-4810ba57-32b1-45d2-99c6-0eabc65c002c.png)

Wireshark oli taas taustalla. Tässä tuloksena tuli vain ARP paketteja

![image](https://user-images.githubusercontent.com/93308960/202803002-d42869e5-d42d-4eb2-bbf0-c3121a7fc5bb.png)

## d) nmap don't ping -Pn

![image](https://user-images.githubusercontent.com/93308960/202804307-b7c6e676-6420-4dda-8bd5-9f6e614bd79e.png)




## e) nmap version detection -sV

![image](https://user-images.githubusercontent.com/93308960/202804649-98a3b219-0d5d-4510-8296-96ab57577f25.png)

![image](https://user-images.githubusercontent.com/93308960/202804691-b4049d81-650b-46df-80bc-7116f30b0374.png)


## f) nmap porttien valinta -p1-100, --top-ports 5, -p-

![image](https://user-images.githubusercontent.com/93308960/202805920-5d40c09a-7bc8-4822-b3ef-42128b6324f4.png)


![image](https://user-images.githubusercontent.com/93308960/202805828-02549fe0-c98e-49fc-8f04-cd161454d0a2.png)


![image](https://user-images.githubusercontent.com/93308960/202805683-4a231770-6193-49a0-a9f1-4fa55450f9ec.png)



## g) nmap ip-osoitteiden valinta; luettelo, verkkomaskilla 10.10.10.0/24, alku- ja loppuosoitteella 10.10.10.100-130 

![image](https://user-images.githubusercontent.com/93308960/202850000-6af21bb1-c682-4d50-acc8-4ba32795c785.png)


## h) nmap output files -oA foo

![image](https://user-images.githubusercontent.com/93308960/202806618-85795480-136f-40fa-b420-007a7643fd33.png)


## k) nmap ajonaikaiset toiminnot


![image](https://user-images.githubusercontent.com/93308960/202848918-00dee716-8bbf-4217-9d2e-9a66e365210c.png)

![image](https://user-images.githubusercontent.com/93308960/202848965-eb61fba4-9516-41c7-bf4f-c42944137180.png)

![image](https://user-images.githubusercontent.com/93308960/202848970-3af957f4-1c72-4cc8-b1a8-b11921472e3c.png)

![image](https://user-images.githubusercontent.com/93308960/202848998-ffbb86b1-8831-43c0-8561-3506030ec28d.png)

![image](https://user-images.githubusercontent.com/93308960/202849008-83bb6615-f75b-431e-880b-24e0fd54f308.png)


## l) normaalisti 'sudo nmap'

![image](https://user-images.githubusercontent.com/93308960/202807010-eb8fcced-0b3e-48d1-b581-03435d9b0044.png)


![image](https://user-images.githubusercontent.com/93308960/202849200-5a39b27f-bf03-46f1-a0bd-403d5972124a.png)


![image](https://user-images.githubusercontent.com/93308960/202849190-fae71e4d-8827-4aca-92a1-b6ffaedaa2f4.png)


![image](https://user-images.githubusercontent.com/93308960/202849294-0989813f-fd4c-4d51-a713-4870be9b7aba.png)


![image](https://user-images.githubusercontent.com/93308960/202849276-682dca90-fc6d-4376-a0d4-cbb82e007150.png)


## m) nmap, vertaile -A

![image](https://user-images.githubusercontent.com/93308960/202849747-4a27fc8d-1635-4241-a571-63f6bc31475b.png)

![image](https://user-images.githubusercontent.com/93308960/202849768-0cc1159f-0100-498c-9aac-0c7f8e6a3f1c.png)

![image](https://user-images.githubusercontent.com/93308960/202849812-de7bc27b-87c4-4a9b-9823-b5a2e9acf60b.png)


## d) Ninjojen tapaan

Asennettiin apache palvelin linuxeen. Aloitettiin perus `sudo apt update & sudo apt upgrade` komennolla. 

Pakettien päivityksien jälkeen asennetteiin itse apache `sudo apt install apache2 -y`, mutta se löytykin jo koneelta. 

![image](https://user-images.githubusercontent.com/93308960/202850527-7486b12f-5e71-487b-9631-ec1691d55787.png)

Sitten laitettiin palvelu käyntiin ja katsottiin sen tila.

```
sudo service apache2 start

&

sudo service apache2 status
```

Active kohdalla näkyy running tila eli apache on käynnissä 

![image](https://user-images.githubusercontent.com/93308960/202850574-e24fd584-352e-49f4-a2a9-662d5b9b8bbd.png)

Tarkistetaav vielä että se on oikeastin käytössä kirjoittamalla koneen ip-osoitteen selaimeen, jolloin avatuu apache2 oletus sivu

![image](https://user-images.githubusercontent.com/93308960/202850660-380f2eab-b32a-4a9c-9fc1-a58703cefcf4.png)


![image](https://user-images.githubusercontent.com/93308960/202850952-0e55605a-d111-4bb0-be4a-a88256c714ae.png)


![image](https://user-images.githubusercontent.com/93308960/202851496-ee539068-b4de-4f59-bd62-91f52eb06a68.png)


![image](https://user-images.githubusercontent.com/93308960/202851514-13842c6d-b9c3-42d8-a68f-e9f4764c3d55.png)


![image](https://user-images.githubusercontent.com/93308960/202851594-f0305d1c-f5e9-49e3-9dec-0a06720581e7.png)


# UDP-skannaus.

## e) Mitkä ovat tavallisimmat tai kiinnostavimmat palvelut, joita UDP-skannauksella voisi löytää? 

Palveluita jota saattaiasi löytyä UDP portti skannauksella

 *  DNS (domain name system) 
 *  NFS (network file system) 
 *  NTP (network time protocol) 
 *  DHCP (dynamic host configuration protocol)

## f) Miksi UDP-skannaus on hankalaa ja epäluotettavaa?

Isoin syy on palomuuri, se estää ulos menevää ICMPv4 type 3 code 3 viestejä jolloin portti näyttää olevan auki. Tästä syntyy *false-positives* vale positiivisia tuloksia joita on vaikea erottaa oikeista aukinaisista olevista porteista. Myös udp portti skannaus kestää kauemmin kun tcp portti skannaus, koska se on connectionless protokolla.

**ICMPv4 type 3 code 3 viesti tarkoittaa destination unreachable. [researchgate](https://www.researchgate.net/figure/ICMP-error-message-format-ICMP-error-messages-of-Type-3-represent-a-destination_fig1_332993177) sivulta löytyi selitys**

#### --reason flag ja UDP

UDP ei käytä lippuja (flags) joten se ei seuraa porttien tilaa tai niihin liittyviä tietoja. `--reason` komento stten kertoo nämä tiedot, kertoo syyn jotta saadaan selville porttien oikea tila.

# Lähteet

https://www.stationx.net/nmap-cheat-sheet/

https://explainshell.com/explain?cmd=nmap+-sT+-PN+-n

https://blog.eldernode.com/how-to-use-wireshark-in-nmap/

https://www.ibm.com/docs/en/qsip/7.4?topic=practices-scan-duration-ports-scanning

https://www.researchgate.net/figure/ICMP-error-message-format-ICMP-error-messages-of-Type-3-represent-a-destination_fig1_332993177
