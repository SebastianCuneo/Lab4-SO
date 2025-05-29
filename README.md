# Lab4-SO
Laboratorio 4 Sistemas Operativos UCU 2025

Scripts:
mkdir -p /home/seba/so-lab4/fuente	
Intento inicial de crear directorio completo (falló por permisos, usuario incorrecto).
mkdir -p /home/seba/so-lab4/destino	
Igual que el anterior, para la carpeta destino (también falló).
sudo mkdir -p /home/seba/so-lab4/fuente	
Creó la carpeta bajo /home/seba usando privilegios de root.
sudo mkdir -p /home/seba/so-lab4/destino	
Idem anterior, para la carpeta destino.
find /home/seba/so-lab4/fuente -type f -mtime -1 -exec cp --parents {} /home/seba/so-lab4/destino/ \;	
Buscó archivos modificados en 24 h en /home/seba/.../fuente y los copió con toda la ruta absoluta.
ls -R /home/seba/so-lab4/destino/	
Listó recursivamente el contenido del destino (mostró toda la jerarquía /home/seba/...).
mkdir -p ~/so-lab4/fuente ~/so-lab4/destino	
Creó correctamente las carpetas fuente y destino dentro de tu home real (/home/aroti/so-lab4/...).
ls -ld ~/so-lab4 ~/so-lab4/{fuente,destino}	
Verificó permisos y propietario de las carpetas creadas.
sudo chown -R $(whoami):$(whoami) ~/so-lab4	
Ajustó recursivamente propietario y grupo de so-lab4 para tu usuario.
chmod -R u+rwx ~/so-lab4	
Dio permisos de lectura, escritura y ejecución a tu usuario sobre todo so-lab4.
echo "hola" > ~/so-lab4/fuente/archivo1.txt	
Generó un archivo de prueba en fuente con contenido “hola”.
find ~/so-lab4/fuente -type f -mtime -1 -exec cp --parents {} ~/so-lab4/destino/ \;	
Buscó y copió archivos modificados en 24 h, dentro de tu home, replicando la ruta completa desde ~/so-lab4.
ls -R ~/so-lab4/destino/	
Listó recursivamente el contenido de la carpeta destino y mostró la jerarquía copiada.
cd ~/so-lab4	
Se situó en el directorio padre para usar rutas relativas.
find fuente -type f -mtime -1 -exec cp --parents {} destino/ \;	
Variante usando ruta relativa: buscó en fuente y copió solo fuente/... bajo destino, sin recrear toda la ruta /home.
