 # Acerca de la claves SSH  

## Generando tu clave pública SSH:

Para más detalles sobre cómo crear unas claves SSH en variados sistemas operativos,  
consultar la correspondiente guía en GitHub: (https://help.github.com/articles/generating-ssh-keys.)  

### pasos:  

===============================================================
1. *Comprobar tus claves SSH existentes*   

       `ls -al ~/.ssh/`  

 ~~~   
        drwxr-xr-x 1 User 197121   0 Mar  9 16:47 ./
        drwxr-xr-x 1 User 197121   0 Mar  9 11:01 ../
        -rw-r--r-- 1 User 197121 411 Mar  9 01:39 id_ed25519
        -rw-r--r-- 1 User 197121 101 Mar  9 01:39 id_ed25519.pub
        -rw-r--r-- 1 User 197121 828 Mar  9 01:52 known_hosts
        -rw-r--r-- 1 User 197121  92 Mar  9 01:52 known_hosts.old 
~~~
 **Comprueba la lista de directorio para ver si ya tiene una clave SSH pública (.pub)**
 ~~~
        id_rsa.pub
        id_ecdsa.pub
        id_ed25519.pub
~~~
===============================================================  

 2. *sdf*
        `cd ~/.ssh`
        `ls -al ~/.ssh/`
