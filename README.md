# Clase_practica
Clase_practica: 
a collection of codes for genomes assembly and cleaning compiled and designed by Victor Jimenez (vr.jimenez.vs@gmail.com)

# THE CODE

# Práctica : estrategias para la obtención de árboles de máxima verosimilitud.
![tree](https://github.com/user-attachments/assets/425d0792-076d-4832-b468-f3575de9dfd2)
```r

#MATERIAL DE LA CLASE: https://drive.google.com/drive/folders/1c1Bpuv89giPX1doxID6SzfzZOjxgGIf6?usp=drive_link

#paso 0 : visualizar secuencias
- descargar ALIVIEW desde la carpeta "software"
- descomprimir la carpeta 

#paso 1 : alineamiento

- descargar MAFFT desde la carpeta "software"
- descomprimir la carpeta y abrir el programa "mafft-signed.exe"
- alinear las secuencias "peru.fasta" empleando como molde el genoma de referencia "reference.fasta"

mafft --add peru.fasta --nomemsave --keeplength --thread 4 --retree 1 --adjustdirection --reorder reference.fasta > output.fasta ;

#paso 2 : visualizar secuencias alineadas
- abrir el resultado "output.fasta" en un visualizador de secuencias como "aliview" o "MEGA 7"

#paso 3 : filogenia
- descargar RAXML desde la carpeta "software"
- descomprimir el contenido
- correr los siguientes comandos en la linea de comandos de Windows, CMD: 

raxmlHPC-PTHREADS -p 123568 -m GTRCAT -s output_2.phy -T 10 -# 10 -n nwk ;
raxmlHPC-PTHREADS -m GTRCAT -p 123568 -b 123568 -# 1000 -s output_2.phy -T 10 -n nwk2 ;
raxmlHPC -m GTRCAT -p 12345 -fb -t RAxML_bestTree.nwk -z RAxML_bootstrap.nwk2 -n nwk3 ;

- el resultado se llamará "RAxML_bipartitions.nwk3"

#paso 4 : visualizar la filogenia en figtree
- descargar FIGTREE desde la carpeta "software"
- visualizar y enraizar el arbol "RAxML_bipartitions.nwk3", exportarlo en formato "newick"

#paso 5 : visualizar el árbol y la metadata en MICROREACT
- MICROREACT está disponible en https://microreact.org/upload
- cargar el árbol y la metadata
```
