# linux commands
## Varios
`ctrl+alt+t` --> abrir terminal  
`man` --> manual page for exec programs  
`pwd` --> muestra ruta de trabajo  
`ls` --> lista elementos **-l, -la**  
`cd` --> cambia de directorio, rutas absolutas o relativas  
`cd ..` --> un directorio atrás  
`cd ../..` --> retrocedo 2 niveles  
`mkdir nombre` --> crea directorio  
`clear` --> limpia pantalla  
`touch nombre` --> crea archivo vacío  
`cp` --> copia **-i** iterativo **-p** atributos **-r** recursivo **carpeta/** solo contenido  
`mv` --> mover  
`rm` --> eliminar ** -r ** recursivo ** -f ** fuerza  
`export EDITOR="nombre"` --> cambiar editor por defecto  
`shutdown` --> apaga computadora un minuto después  
`shutdown -c` --> cancela apagado  
`init 0` --> paga computadora de inmediato  
`reboot` --> reinicia sistema  

## Permisos
- **modo octal:**  
$chmod [opcion] propietario, grupo, otros carpeta/archivo  
`$chmod [ ] 000 nombre`  

|valor|read|xrite|execute|
|-|-|-|-|
|7|r|w|x|
|6|r|w|-|
|5|r|-|x|
|4|r|-|-|
|3|-|w|x|
|2|-|w|-|
|1|-|-|x|
|0|-|-|-|

- **modo caracter:**  
`$chmod [ ] ugoa +-= rwx`  
u = usuario, g = grupo, o = otros, a = all-todos  
r = lectura, w = escritura, x = ejecución  

## Acceso a super usuario 
`sudo` --> super user do  
`sudo su` --> cambia de usuario  
`sudo passwd` usuario --> cambia password  
`whoami` --> saber que usuario soy  
`root@machine...#`  
**root** = usuario, **machine** = equipo, **#** = root, **$** = usuario normal  

## Symbolic links - accesos directos
`ln -s ruta-absoluta ruta-acceso-directo/nombre`  

## Edición de archivos
- **nano**  
`nano nombre archivo`  
ctrl + o --> guarda  
ctrl + x --> salir  
ctrl + w --> busca  
ctrl + k --> corta linea  

- **vim**  
`vim nombre archivo`  
modo navegación  
0 --> inicio de linea  
$ --> final de linea  
w --> salta palabras  
modo búsqueda / ?  
/ --> n --> siguiente iteración abajo  
? --> n --> siguiente iteración arriba  
modo inspección  
i --> insertar en el cursor  
a --> después del cursor, A --> al final de la linea  
o --> crea linea nueva abajo del cursor  
O -->crea linea nueva arriba del cursor  
modo comando :  
! --> ejecutar comando sin salir de vim  
q! --> salir sin guardar  
wq --> guarda  
x --> guarda  

## Encontrar ficheros
`find \[ruta] [expresión]` --> -name -perm -gid -uid  
`locate archivo`  
`whereis archivo`  
`which archivo`  

## instalación de paquetes y programas
- apt-get o apt  
`sudo apt-get install nombre` --> instala  
`sudo apt-get update`  
`sudo apt-get upgrade`  
`sudo apt-get remove nombre`  
`sudo apt-get remove \--purge nombre`  

- paquetes .deb  
`sudo dpkg -i nombre` --> instala  
`./nombre` --> corre programa  
`sudo dpkg -r nombre` --> remueve  

- tar.gz  
`tar -xvf nombre`  
localizar configure y asignar permisos de ejecución  
`./configure`  
`make`  
m`ake install`  
verificar instalación --> `nombre -v`  

## procesos en la terminal
PID --> process ID  
PPID --> padre de PID  
kill PID --> mata procesos  
ps --> manipula procesos  
pstree --> forma de árbol  

## información del sistema
free --> ver RAM libre  
lscpu --> ver hardware de CPU  
nproc --> numero de CPU disponibles  
dmidecode --> información del hardware  
uptime --> tiempo del sistema corriendo  
df --> ver espacio disponible de los HD o particiones  
uname -r --> versión del kernel Linux  

## CRON
permite ejecutar y controlar los procesos que se ejecutan en segundo plano  
crontab  
-l --> lista las tareas  
-r --> quita tareas  
-e --> edita archivo crontab  
- - - - - comando a ejecutar  

minuto (0-59)  
hora (0-23)  
día-mes (1-31)  
mes (1-12) o jan, feb, mar, apr  
día-semana (0-6) dom = 0 sun,mon  
\* --> todo  

## Visualización de ficheros
cat nombre --> concatenador de ficheros -b = mum de lineas, -E = muestra $, -n = numero lineas vaciás, -T = tabulaciones  
tac nombre --> al revés que cat  
grep --> busca y filtra  
head nombre --> 10 primeras lineas  
tail nombre --> 10ultimas lineas -f = comando no finaliza y muestra los cambios en vivo  
nl nombre --> numera lineas de ficheros -ba = todo, -bt = no lineas blancas  
uniq nombre --> muestra lineas repetidas y no repetidas -u = no rep, -d = rep  
sort name --> ordena -n = numérico, -r = invierte  
cut --> corta -d = delimitador, -f = columna del delimitador  
fmt nombre --> formatea texto caracteres por linea  

## Pipes (|) o tuberías y re-direcciones (>,>>)
conectar salidas de un programa con entradas de otro programa  
ls | sort --> ordena listado  
\> --> re-direcciona crea fichero o sustituye  
\>> -->  re-direcciona crea fichero o añade  
2> --> re-direcciona crea fichero o sustituye (error estándar)  
2>> --> re-direcciona crea fichero o añade (error estándar)  
&> --> unifica los anteriores  
\` --> comilla ejecutiva  

## Shell script
```bash
#!/bin/bash
echo "hola mundo"
```
