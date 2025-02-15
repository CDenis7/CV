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

Verificam disponibilitatea site-urilor http://drupal.localhost:1080 și http://phpmyadmin.localhost:1080. 
<img width="959" alt="Captură de ecran 2025-02-15 182051" src="https://github.com/user-attachments/assets/ec0431a8-7e22-4e05-908d-947615e011d7" />

<img width="959" alt="Captură de ecran 2025-02-15 182117" src="https://github.com/user-attachments/assets/c3f11d6a-87b9-4ff8-b8f1-096be2a5935a" />

Finalizam instalarea site-urilor.

<img width="959" alt="Captură de ecran 2025-02-15 193120" src="https://github.com/user-attachments/assets/0c2fbed0-2005-485f-b636-f9cb1fbf80f8" />

<img width="935" alt="Captură de ecran 2025-02-15 192148" src="https://github.com/user-attachments/assets/f7e39e89-7d07-4010-9be9-595e8b1df311" />

![image](https://github.com/user-attachments/assets/bcc8b82a-df33-42c2-b88e-4cf3f7988c58)


Cum se poate descărca un fișier în consolă cu ajutorul utilitarului wget?
Fișierele pot fi descărcate în consolă folosind comanda:

wget <URL-ul-fișierului>

De exemplu, pentru a descărca PhpMyAdmin:

wget https://files.phpmyadmin.net/phpMyAdmin/5.2.2/phpMyAdmin-5.2.2-all-languages.zip

De ce este necesar să creați pentru fiecare site baza de date și utilizatorul său?

Separarea bazelor de date pentru fiecare site asigură securitatea și izolarea datelor.
Permite gestionarea mai ușoară a drepturilor de acces.
Reduce riscul de interferență între aplicații diferite.

Cum se poate schimba accesul la sistemul de gestionare a bazei de date pe portul 1234?

Se editează fișierul de configurare MySQL/MariaDB:

sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf

Se modifică linia:

port = 1234

Se repornește serviciul MySQL/MariaDB:

sudo systemctl restart mariadb

Care sunt avantajele, din punctul dvs. de vedere, ale virtualizării?

Izolare: Fiecare VM rulează independent.
Eficiență: Permite utilizarea optimă a resurselor hardware.
Flexibilitate: Posibilitatea de a testa și implementa diverse sisteme.
Backup și restaurare rapide: Prin snapshot-uri și copii ale imaginii VM.

Pentru ce este necesar să se stabilească ora/zona de timp pe server?

Asigură sincronizarea corectă a fișierelor log.
Previne probleme de compatibilitate cu aplicațiile care depind de timp.
Evită erori în sarcinile programate (cron jobs).

Cât spațiu ocupă instalarea OS (disc virtual) pe mașina gazdă?

 Instalarea Debian pe un disc virtual de 8 GB ocupă inițial aproximativ 2-3 GB, dar poate crește în funcție de fișierele și aplicațiile adăugate.

Care sunt recomandările privind partiționarea discului pentru servere? De ce se recomandă să se particioneze discul în acest fel?

Partiționarea recomandată:
        / (root) – Sistemul de bază (~20-30 GB)
        /home – Datele utilizatorilor
        /var – Fișiere temporare, log-uri (~10 GB+)
        /swap – Spațiu swap (~RAM * 2)
        /boot – Bootloader (~1 GB)
    Motive:
        Separarea datelor critice reduce riscul de corupere a sistemului.
        Log-urile și fișierele temporare nu afectează performanța sistemului.
        Swap-ul ajută la prevenirea blocării sistemului în caz de consum excesiv de RAM.

Concluzii

În urma acestei lucrări de laborator, am reușit să configurăm un server virtualizat utilizând QEMU și să instalăm un mediu LAMP. Pe parcursul lucrării, am învățat:

Cum să descărcăm și să instalăm un sistem de operare pe o mașină virtuală.
Configurarea unui server web Apache și integrarea acestuia cu PHP și MySQL/MariaDB.
Instalarea și configurarea a două aplicații web: PhpMyAdmin și Drupal.
Crearea bazelor de date și configurarea utilizatorilor acestora pentru fiecare site.
Activarea și gestionarea gazdelor virtuale în Apache.

Această experiență ne-a oferit o înțelegere mai clară a modului în care serverele sunt configurate și administrate într-un mediu virtualizat, evidențiind avantajele utilizării virtualizării în testare și dezvoltare. De asemenea, am învățat importanța configurării corecte a rețelei și a securității sistemului.

Documentația oficială Debian – https://www.debian.org/doc/

Ghidul utilizatorului QEMU – https://www.qemu.org/documentation/

Documentația Apache HTTP Server – https://httpd.apache.org/docs/

Documentația oficială PhpMyAdmin – https://docs.phpmyadmin.net/

Documentația oficială Drupal – https://www.drupal.org/documentation

Comenzi utile Linux și administrare servere – https://linux.die.net/

Tutoriale și ghiduri pentru LAMP stack – https://www.digitalocean.com/community/tutorials
