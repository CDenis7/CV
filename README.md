IWNO1: Server virtual
Realizat de: Crudu Denis I2301
Data:15.02.2025
Scop
Am descarcat distributivul Debian pentru servere pentru arhitectura x64 (fără interfață grafică) și sistemul de virtualizare (hypervizor) QEMU.
Executare

Am creat directorul lab01. În acest director am creat directorul dvd și fișierul readme.md. În directorul dvd am plasat imaginea ISO a distributivului Debian.

<img width="584" alt="Captură de ecran 2025-02-14 102007" src="https://github.com/user-attachments/assets/9a12fd41-b61f-4125-bb18-3c970be9ae84" />

În consolă am creat în directorul lab01 imaginea discului pentru mașina virtuală de dimensiune 8 GB și format qcow2, folosind utilitarul qemu-img:

![image](https://github.com/user-attachments/assets/62e7dbcf-183e-49df-bf3a-2bedf0871e4e)

Am instalat SO Debian pe mașina virtuală. Pentru aceasta am executat comanda:

![image](https://github.com/user-attachments/assets/760d6570-6e31-4dc7-90ef-a1c739d266dc)

![image](https://github.com/user-attachments/assets/868fec43-fa3f-4729-bdb6-ad7b350e1c65)

Repornim mașina virtuală. Pentru a reporni mașina virtuală, am executat comanda:

![image](https://github.com/user-attachments/assets/8cd9d1fd-3c62-4414-a2b1-212a0a69a425)

Am instalat LAMP în mașina virtuală. Pentru aceasta, am schimbat profilul utilizatorului pe superutilizator.
Descarcam SGBD PhpMyAdmin si CMS Drupal.
Dezarhivam fișierele descărcate:

<img width="854" alt="Captură de ecran 2025-02-12 181758" src="https://github.com/user-attachments/assets/dd5ef4b5-3871-42f1-a4ea-5e45f7f2a6bd" />

Creeam din linia de comandă baza de date drupal_db și utilizatorul bazei de date:

<img width="563" alt="Captură de ecran 2025-02-12 192616" src="https://github.com/user-attachments/assets/49987e1a-1f72-4664-bb5c-042c9883b470" />

În directorul /etc/apache2/sites-available am creat fișierul 01-phpmyadmin.conf , cu următorul conținut:

<img width="850" alt="Captură de ecran 2025-02-12 193646" src="https://github.com/user-attachments/assets/8c37f59f-382d-4611-b307-f0ed55cc18d7" />

<img width="808" alt="Captură de ecran 2025-02-12 194527" src="https://github.com/user-attachments/assets/71e01c3c-3d6e-40c0-b801-acefc589ecf2" />

În directorul /etc/apache2/sites-available creați fișierul 02-drupal.conf

<img width="853" alt="Captură de ecran 2025-02-12 193331" src="https://github.com/user-attachments/assets/c62b49e7-1c8a-4f86-8d63-6ccc031c6485" />

Pentru a activa configurațiile, am executat comenzile:

<img width="419" alt="Captură de ecran 2025-02-12 195413" src="https://github.com/user-attachments/assets/900f285d-4278-4f09-a5dd-83e52613466c" />

<img width="411" alt="Captură de ecran 2025-02-12 195319" src="https://github.com/user-attachments/assets/6f00c0df-21d1-4861-ba66-527de628bbd4" />

Am repornit Apache HTTP Server:

<img width="368" alt="Captură de ecran 2025-02-12 195506" src="https://github.com/user-attachments/assets/e00a2438-76a7-4b7f-92cf-d23e72c01454" />

Am adăugat în fișierul /etc/hosts următoarele linii:

<img width="747" alt="Captură de ecran 2025-02-12 195746" src="https://github.com/user-attachments/assets/32ceba9e-5217-4ec2-b4c4-38f8bd6010dd" />

Pornire și testare
În consolă executați comanda:
uname -a
    Ce se afișează pe ecran în urma executării acestei comenzi?
Reporniți Apache Web Server.
    Cum se poate reporni Apache Web Server?
<img width="689" alt="Captură de ecran 2025-02-12 200247" src="https://github.com/user-attachments/assets/ecd1aa12-ff50-41c1-a576-b145a87cad1f" />








