
# Corregir la ubicación de la librería libpng12.so.0 para MX Linux 19 (Debian 10 Buster)

	sudo apt installl gedit

Descomprimir el contenido del instalador .deb poner en la terminal:

	dpkg-deb -x libpng12-0_1.2.50-2+deb8u3_i386.deb tmpdir

borrar el archivo (enlace simbólico a /lib/i386-linux-gnu/libpng12.so.0.50.0):

/tmpdir/usr/lib/i386-linux-gnu/libpng12.so.0

mover los dos archivos siguientes:

/tmpdir/lib/i386-linux-gnu/libpng12.so.0
/tmpdir/lib/i386-linux-gnu/libpng12.so.0.50.0

a la carpeta:

/tmpdir/usr/lib/i386-linux-gnu/

borrar la carpeta:

/tmpdir/lib 

prepara el archivo control para poderlo editar:

	dpkg-deb --control libpng12-0_1.2.50-2+deb8u3_i386.deb tmpdir/DEBIAN

abrir el archivo control:

	gedit tmpdir/DEBIAN/control

Cambiar el nombre del desarrollador por el mío

	dpkg -b tmpdir libpng12-0_1.2.50-2+deb8u3_i386_ok.deb 

Problema corregido

Washington Indacochea Delgado  
wachin.id@gmail.com  
2023
