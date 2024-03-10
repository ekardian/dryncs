# dryncs
Copy serialized dirs and files - Tested in Linux Mint 21.2, Debian 12\
Work in [bash](https://www.gnu.org/software/bash/) Linux and [cygwin](https://cygwin.com/) Windows

English\
Script in bash with rsync and dialog for copy serialized files and directories with references.

Español\
Script en bash con rsync y dialog para copiar carpetas con nombres con espacio que coincidan con los listados en un archivo.txt.

## Requerimientos:
  - [rsync](https://rsync.samba.org/) (linux/windows cygwin), [dialog](https://linux.die.net/man/1/dialog) (linux/windows cygwin), [lsblk](https://www.geeksforgeeks.org/lsblk-command-in-linux-with-examples/)(linux), [sed](https://www.gnu.org/software/sed/manual/sed.html) (linux/windows cygwin)
    ````
    $ sudo apt install rsync
    $ sudo apt install dialog
    ````
## Install
````
$ git clone https://github.com/ekardian/dryncs.git
$ cd dryncs.git
$ chmod 
$ ./dryncs.git
````
## Ejemplo
For test and practice you can populate dirs and files with `populate-dirs-files` and `populate-dirs-files-ns2`

### Scene
Copiaré solo las carpetas que contengan A123 y A12345, estas dos cadenas que buscaré estarán contenidas en un archivo.txt.
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
Serialized Folders

![imagen](https://github.com/ekardian/dryncs/assets/6296036/2057ba43-383c-409f-9930-c9bc9e7c2e7b)

Serialized Files

![imagen](https://github.com/ekardian/dryncs/assets/6296036/854cd0b7-5860-44f1-8ca3-44cdfd7b81ed)

