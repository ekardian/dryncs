# dryncs
Copy serialized dirs and files

English
Script in bash with rsync and dialog for copy serialized files and directories with references.

Español
Script en bash con rsync y dialog para copiar carpetas con nombres con espacio que coincidan con los listados en un archivo.txt. Testeado con Linux Mint 21.2 y Debian 12. Corre en Linux y Windows con cygwin. Instalación, solo clonar el repositorio y dar permisos de ejecutable a los archivos: `chmod a+rx dryncs.src`. Ejecute en consola con `./dryncs.src`.

  Requerimientos:
  - [rsync](https://rsync.samba.org/)(linux/windows cygwin), [dialog](https://linux.die.net/man/1/dialog)(linux/windows cygwin), [lsblk](https://www.geeksforgeeks.org/lsblk-command-in-linux-with-examples/)(linux), [sed](https://www.gnu.org/software/sed/manual/sed.html)(linux/windows cygwin)
    ````
    $ sudo apt install rsync
    $ sudo apt install dialog
    ````
  - dryncs.scr
  Ejemplo: Copiaré solo las carpetas que contengan A123 y A12345, estas dos cadenas que buscaré estarán contenidas en un archivo.txt.
  Contenido del archivo.txt
    folder-A123
    folder-A12345
  El script copiará solo las carpetas que coinciden con estos dos cadenas de texto, como se vé abajo
  
````  
     source
           |-- folder1
                      |-- folder2  
                                 |--- folder-A123
                                                 |--- file1
                                                 |--- file....
                                 |--- folder-A12345
                                                   |--- file2
                                                   |--- file....
                                 |---- folder-Annnn
                                                   |--- file3
                                                   |--- file....
      Folder-Destino
                   |--- folder-A123
                                   |--- file1
                                   |--- file....
                   |--- folder-A12345
                                   |--- file2
                                   |--- file....
````                 
