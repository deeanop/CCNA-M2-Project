Cerinte:
1. Configurati Vlan-urile in ambele site-uri conform topologiei.
2. Configurati WAN-ul respectand subnet-urile mentionate in
topologie.
3. In site "Customer Office" configurati port-channel folosind PAGP,
setati RSTP si HSRP-ul, astfel incat sa folositi cat mai optim reteaua.
4. In site "DataCenter" , configurati port-channel folosind LACP si
setati RSTP + HSRP optim.
5. Configurati RIP pentru routerele din "Internet" (ISP1 + ISP2 + CE1 + CE2)
6. Configurati rute statice default catre ISP astfel:
- R1 si R2, ruta default catre ISP1
- Core_SW1 si Core_SW2, ruta default catre ISP2
7. Configurati HSRP in partea de WAN astfel:
- R1 si R2 vor imparti un IP virtual din subnet 10.10.10.0/24
- Core_SW1 si Core_SW2 vor imparti un IP virtual din subnet 20.20.20.0/24
8. Configurati rute statice de la ISP-uri catre LAN astfel:
ISP1:
- catre subnet-urile 192.168.x.x
- catre subnet-urile 172.16.x.x
ISP2:
- configuratie similara cu ISP1
9. Configurati pe Core-SW1 DHCP pool-uri pentru vlan-urile din "Customer office" si adaptati
configuratia astfel incat PC-urile din acel site sa primeasca IP-uri via DHCP (atentie
la DNS server sa folositi in pool-uri IP-ul serverului din topologie)
10. Configurati SSH pe fiecare SW si Router din LAN-uri pentru access remote, folosind AAA,
userul si parola va fi configurat pe AAA. -> LASATI CERINTA CU AAA LA FINAL. Dati export la proiect, local, fara AAA si dupa sa va apucati de AAA si exportati din nou proiectul
11. Configurati port-security static pentru porturile de access din DataCenter si
port security dynamic pentru porturile de access din Customer cu maxim 3 MAC-uri permise.
12. Pe Switchurile ROSII configurati DHCP Snooping.
13. Pe Switchurile ROSII configurati Dynamic Arp Inspection.
14. Puneti admin down port-urile nefolosite de pe switch-uri.
15. Salvati running-config de pe echipamente pe serverul de TFTP.
