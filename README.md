# dryncs
Very Fast!!! Copy serialized dirs and files to 1 or 2 o 3 target at the same time - Tested in Linux Mint 21.2, Debian 12\
Work in [bash](https://www.gnu.org/software/bash/) Linux and [cygwin](https://cygwin.com/) Windows.


English\
Script in bash with rsync and dialog for copy serialized files and directories that contain name spaces listed inside archive.txt

Español\
Script en bash con rsync y dialog para copiar carpetas con nombres con espacio que coincidan con los listados en un archivo de texto archivo.txt.

Only working the for music and movies. we are cooking yet.

![imagen](https://github.com/ekardian/dryncs/assets/6296036/06476fd4-ede7-4c2c-abee-23b1990565b0)

- For Movies files, example `my-movie-F1234.mkv`, wil conpy only the movie files with the reference `F1234.mkv`.
  For copy a list of movies, just write a movie list to copy to anywhere, example write line by line in a file name called mymovies.txt:\
  F1234\
  F12345\
  F123456\
- For Music files, example `(/dirs/my-album-M1234/allmusicfiles*.mp3)`, this will copy the dir and his contain with the reference `M1234`.
  For copy a list of albums,  just write a music list to copy to anywhere, example write line by line in a file name called mymusic.txt\
  M1234\
  M12345\
  M123456\

## Steps
Warning. This gonna rewrite all the files with the same name in the target.

in the firsth execution, update the location of movies and music with the option 9. If you change the location of your files, run again the update with the option 9.

1. Select the option for copy Movies or Music.
2. Select the target, USB drive, samba directories shared (if need authentication firsth do it from your explorar, then run again dryncs), others.
3. Select the text file that contain the list for copy. This file can be stored and called from anywahere if you have shared resources in your network with read access. If you need authenticate, do it from your explorar, thhen run again dryncs.
If something going wrong press CTRL+X
Check the log files `copiados.log` `fallidos.log` `dryncs.log` for more information about copied files and errors.

## Requirements:
  - [rsync](https://rsync.samba.org/) (linux/windows cygwin), [dialog](https://linux.die.net/man/1/dialog) (linux/windows cygwin), [lsblk](https://www.geeksforgeeks.org/lsblk-command-in-linux-with-examples/)(linux), [sed](https://www.gnu.org/software/sed/manual/sed.html) (linux/windows cygwin)
    ````
    $ sudo apt install rsync
    $ sudo apt install dialog
    ````
## Install
````
$ git clone https://github.com/ekardian/dryncs.git
$ cd dryncs.git
$ chmod a+rx dryncs.scr dryncs2way.scr dryncs3way.scr
$ ./dryncs.scr

# update database of Music, Movies, etc with the option 9
````
 - `dryncs.scr` for one target, need config variables in `mdialog_conf`. See inside `mdialog_conf`
 - `dryncs2way.scr` for two target, need config variables inside `dryncs2way.scr`
 - `dryncs3way.scr` for three target, need config variables inside `dryncs3way.scr`

Change the config file `mdialog_conf` for `dryncs.scr`

## Example
For test and practice you can populate dirs and files with `populate-dirs-files` and `populate-dirs-files-ns2`
Note. this script rewrite all the dirs and files with the same name.
````
$ chmod a+rx populate-dirs-files populate-dirs-files-ns2
$ ./populate-dirs-files
$ ./populate-dirs-files-ns2
````

### Scene
Copiaré solo las carpetas que contengan A123 y A12345, estas dos cadenas que buscaré estarán contenidas en un archivo.txt.
  Contenido del archivo.txt\
    folder-A123\
    folder-A12345\
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
      Target Folder
                   |--- folder-A123
                                   |--- file1
                                   |--- file....
                   |--- folder-A12345
                                   |--- file2
                                   |--- file....
````                 
What do these scripts [populate-dirs-files](populate-dirs-files) and [populate-dirs-files-ns2](populate-dirs-files-ns2) do

Serialized Folders

![imagen](https://github.com/ekardian/dryncs/assets/6296036/2057ba43-383c-409f-9930-c9bc9e7c2e7b)

Serialized Files

![imagen](https://github.com/ekardian/dryncs/assets/6296036/854cd0b7-5860-44f1-8ca3-44cdfd7b81ed)

