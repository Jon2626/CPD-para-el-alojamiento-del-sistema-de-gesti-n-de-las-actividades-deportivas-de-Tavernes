![](Pictures/1000000100000586000007D0B3483033.png){width="20.999cm"
height="29.7cm"}

[]{#anchor}1. Informe
=====================

[]{#anchor-1}1.2. Objetivo del informe
--------------------------------------

El propósito de este informe es detallar el proceso de instalación y
configuración de un servidor Windows con RAID 5, así como la creación de
una red LAN. Se pretende describir cada fase, de la implementación,
tocando aspectos técnicos del hardware, la configuración del sistema
operativo, la gestión del almacenamiento en RAID 5 y la organización de
la red.

[]{#anchor-2}2. Materiales usados
=================================

[]{#anchor-3}2.1. Materiales usados
-----------------------------------

### []{#anchor-4}2.1.1 Hardware

-   Ordenador:

    -   Placa base: Asus PRIME B250M-A.
    -   Procesador: Intel® CPU G45560 @3.50GHz.
    -   RAM: Cruzial 4096MB 2666MHz.

![](Pictures/100000000000060000000800F2AC6934.jpg){width="6.174cm"
height="8.23cm"}![](Pictures/1000000000000600000008003ACBDD4C.jpg){width="6.186cm"
height="8.248cm"}

-   Discos:

    -   3 discos con almacenamiento de 500GB
    -   1 Disco SSD de 120GB.

-   Otros:

    -   Adaptador: NFHK Cable adaptador USB 3.0 a SATA 3.
    -   USB: 3.0 de 32GB.
    -   Tarjeta controladora RAID.

### []{#anchor-5}2.1.2 Software

-   Ventoy
-   ISO Windows Server 2022
-   GParted

[]{#anchor-6}3. Instalación de Windows Server
=============================================

[]{#anchor-7}3.1. Instalación con uso de Ventoy
-----------------------------------------------

[]{#anchor-8}Haciendo uso del Ventoy y la iso de Windows Server 2022,
llevaremos acabo la instalación de este.

La instalación comienza con la elección del idioma, que permanecerá
durante la instalación y el sistema operativo, en este caso Español.

![](Pictures/10000001000003FE00000303D8DD0F68.png){width="11.523cm"
height="8.692cm"}

![](Pictures/1000000100000405000003086577D84F.png){width="12.31cm"
height="9.282cm"}

En esta
ve![](Pictures/10000001000004080000030437D2581C.png){width="13.249cm"
height="9.91cm"}ntana se debe introducir la clave del producto.

Ahora escogeremos el sistema operativo Windows Server 2022 Datacenter
(experien![](Pictures/10000001000003FE0000030266A7152D.png){width="13.399cm"
height="10.095cm"}za escritorio).

Aceptamos términos y condiciones.

![](Pictures/100000010000040000000302C11AC2D3.png){width="12.294cm"
height="9.245cm"}

La instalación la haremos sobre un disco de 500GB

![](Pictures/1000000100000402000002FEFB7FAA8B.png){width="12.43cm"
height="9.28cm"}

Esperamos a que la instalación termine y podemos continuar.

![](Pictures/1000000100000401000002FF37BB3347.png){width="13.344cm"
height="9.985cm"}

Cuando la instalación se complete escogeremos la contraseña del
administrador.

![](Pictures/10000001000004020000030749C28007.png){width="13.095cm"
height="9.892cm"}

Finaliz![](Pictures/10000001000003FF00000317EB23F157.png){width="13.582cm"
height="10.5cm"}ada la instalación del Sistema Operativo Windows Server.

[]{#anchor-9}4. Configuración del RAID 5
========================================

[]{#anchor-10}4.1. Mediante Hardware
------------------------------------

### []{#anchor-11}4.1.1. Primer intento

Con una tarjeta controladora de RAID, proporcionada por el profesor.

#### []{#anchor-12}4.1.1.1 Problemas

La tarjeta controladora no era compatible con la placa base. No se pudo
encontrar solución a esto asi que buscamos otra opción

### []{#anchor-13}4.1.2. Segundo Intento

Haciendo uso de la funcionalidad de Windows para crear RAIDs se intento
conectar 4 discos a la maquina, siendo uno el del Sistema operativo y
los tres para el RAID 5.

#### []{#anchor-14}4.1.2.1 Problemas

La fuente de alimentación solo puede dar energía máximo a tres discos
duros a la vez, no tiene capacidad para admitir un cuarto disco.

### 

### []{#anchor-15}4.1.3. Tercer Intento

También se intento fue conectar tres discos duros a la fuente de
alimentación y haciendo uso de un adaptar de USB 3.0 a SATA 3, se
instalo en una SSD de 120GB el Sistema operativo Windows Server,
conectado al adaptador.

![](Pictures/100000000000080000000600C295986E.jpg){width="11.709cm"
height="8.781cm"}

#### []{#anchor-16}4.1.3.1 Problemas

El ordenador no tiene la capacidad para poder iniciar por BOOT el USB,
dando pantallazos azules sin poder proseguir con el RAID 5 y perdiendo
acceso al Windows Server.

### []{#anchor-17}4.1.4 Conclusión

Se llego a la conclusión que no era posible hacer un RAID 5 mediante
Hardware, optando a realizar un RAID 5 por Software.

[]{#anchor-18}4.2. Mediante Software
------------------------------------

4.2.1.Grupos de Almacenamiento

Usamos un disco extra para realizar el RAID 5, primero hay que
inicializar el disco. Esto se realizad des de Administración de Discos.

![](Pictures/100000010000019E000001345E516CD4.png){width="10.85cm"
height="8.07cm"}

Se debe crear un nuevo volumen simple.

![](Pictures/10000001000002F2000000E0E96DA04A.png){width="17cm"
height="5.05cm"}

Tambien hay que reducir el tamaño del disco del sistema operativo o
añadir un nuevo disco. Y añadir un disco vacio

![](Pictures/10000001000001BF0000017DBC050C87.png){width="9.476cm"
height="8.077cm"}

![](Pictures/10000001000002E100000067C821C232.png){width="17cm"
height="2.374cm"}

La letra asignada sera la D.

![](Pictures/10000001000002EF0000006A05419D67.png){width="17cm"
height="2.399cm"}

Ahora crearemos 3 unidades vhd en el apartado Acción.

![](Pictures/1000000100000144000000DEA899CC35.png){width="8.573cm"
height="5.874cm"}

Examinaremos donde queremos crear y guardar los archivos y el tamaño.

![](Pictures/1000000100000185000001D69E2AB5BE.png){width="8.491cm"
height="10.261cm"}

![](Pictures/1000000100000267000001F5CD2DCED6.png){width="11.698cm"
height="9.53cm"}

Ahora ya tenemos los discos creados.

![](Pictures/10000001000002AA0000012DD3133B20.png){width="17cm"
height="7.504cm"}

Para continuar con en el Administrador del servidor nos dirigiremos a
Servicios de archivos y de almacenamiento.

![](Pictures/1000000100000243000001116CCE2D28.png){width="13.339cm"
height="6.288cm"}

Dentro a Grupo de almacenamiento.

![](Pictures/1000000100000152000000CCE7086B09.png){width="8.251cm"
height="4.979cm"}

Debemos actualizar para buscar el grupo primordial.

![](Pictures/10000001000003D0000000CE4447EA66.png){width="17cm"
height="4.932cm"}

Ahora nuevo grupo.

![](Pictures/10000001000002950000008C2189FADC.png){width="17cm"
height="3.6cm"}

Y ahora los pasos mas importantes.

Asignar un nombre a el grupo:

![](Pictures/10000001000003880000024F8CAACB4C.png){width="13.224cm"
height="8.625cm"}

Seleccionar el disco físico.

![](Pictures/100000010000038A0000024F2A5A9357.png){width="13.344cm"
height="8.703cm"}

Crear el grupo de volúmenes.

![](Pictures/10000001000003860000024E6FCC61E3.png){width="15.695cm"
height="10.266cm"}

Esperamos que el proceso termine y cerramos la ventana.

![](Pictures/1000000100000375000002533DDF5039.png){width="14.462cm"
height="9.724cm"}

Lo siguiente seria ir a Discos virtuales, donde tenemos que añadir el
grupo que habíamos creado.

![](Pictures/1000000100000175000000A8B36A7EF7.png){width="9.871cm"
height="4.445cm"}

![](Pictures/10000001000002A9000001347D410657.png){width="17cm"
height="7.687cm"}

Ahora crearemos un nuevo disco virtual. Estas acciones las haremos para
los tres discos.

Nombre:

![](Pictures/10000001000002F50000022FA4C4A8A5.png){width="13.157cm"
height="9.716cm"}

La distribución debe ser simple para que funcione.

![](Pictures/10000001000002F60000022B008F1DA9.png){width="13.561cm"
height="10.014cm"}

Aprovisionamiento Fijo.

![](Pictures/10000001000002F800000230383064A1.png){width="14.298cm"
height="10.534cm"}

El tamaño que deseamos o máximo.

![](Pictures/10000001000002F6000002306FFB4DFC.png){width="12.975cm"
height="9.585cm"}

Luego seria crear.

![](Pictures/10000001000002F60000022D268C55BA.png){width="14.273cm"
height="10.488cm"}

Ahora en administrador de discos.

Podemos crear un RAID5 y ver el procedimiento de este.

![](Pictures/100000010000037600000177EC844FA9.png){width="17cm"
height="7.195cm"}
