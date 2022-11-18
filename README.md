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


![image](https://user-images.githubusercontent.com/93308960/202801825-4cc2d399-4130-42a2-82e1-e00c345a152a.png)


![image](https://user-images.githubusercontent.com/93308960/202801786-68446e01-0563-4b6b-ab0c-fe1cf26b6588.png)


## b) nmap TCP SYN "used to be stealth" scan, -sS

![image](https://user-images.githubusercontent.com/93308960/202802112-27aafb5d-915b-4460-bc05-79fde6907c8a.png)


![image](https://user-images.githubusercontent.com/93308960/202802062-2387e935-768c-4841-8382-2ddfec3dc016.png)


## c) nmap ping sweep -sn

![image](https://user-images.githubusercontent.com/93308960/202803042-4810ba57-32b1-45d2-99c6-0eabc65c002c.png)


![image](https://user-images.githubusercontent.com/93308960/202803002-d42869e5-d42d-4eb2-bbf0-c3121a7fc5bb.png)

## d) nmap don't ping -Pn

![image](https://user-images.githubusercontent.com/93308960/202804307-b7c6e676-6420-4dda-8bd5-9f6e614bd79e.png)

![image](https://user-images.githubusercontent.com/93308960/202804354-c7320ca3-4910-465f-b48d-fdc23f397573.png)


## e) nmap version detection -sV

![image](https://user-images.githubusercontent.com/93308960/202804649-98a3b219-0d5d-4510-8296-96ab57577f25.png)

![image](https://user-images.githubusercontent.com/93308960/202804691-b4049d81-650b-46df-80bc-7116f30b0374.png)


## f) nmap porttien valinta -p1-100, --top-ports 5, -p-

![image](https://user-images.githubusercontent.com/93308960/202805920-5d40c09a-7bc8-4822-b3ef-42128b6324f4.png)


![image](https://user-images.githubusercontent.com/93308960/202805828-02549fe0-c98e-49fc-8f04-cd161454d0a2.png)


![image](https://user-images.githubusercontent.com/93308960/202805683-4a231770-6193-49a0-a9f1-4fa55450f9ec.png)



## g) nmap ip-osoitteiden valinta; luettelo, verkkomaskilla 10.10.10.0/24, alku- ja loppuosoitteella 10.10.10.100-130 

## h) nmap output files -oA foo

![image](https://user-images.githubusercontent.com/93308960/202806618-85795480-136f-40fa-b420-007a7643fd33.png)


## k) nmap ajonaikaiset toiminnot

## l) normaalisti 'sudo nmap'

![image](https://user-images.githubusercontent.com/93308960/202807010-eb8fcced-0b3e-48d1-b581-03435d9b0044.png)


## m) nmap, vertaile -A

## d) Ninjojen tapaan

# UDP-skannaus.

## e) Mitkä ovat tavallisimmat tai kiinnostavimmat palvelut, joita UDP-skannauksella voisi löytää? 

## f) Miksi UDP-skannaus on hankalaa ja epäluotettavaa?

# Lähteet

https://www.stationx.net/nmap-cheat-sheet/

https://explainshell.com/explain?cmd=nmap+-sT+-PN+-n

https://blog.eldernode.com/how-to-use-wireshark-in-nmap/
