 # Acerca de la claves SSH  

## Generando tu clave pública SSH:

Para más detalles sobre cómo crear unas claves SSH en variados sistemas operativos,  
consultar la correspondiente guía en GitHub: (https://help.github.com/articles/generating-ssh-keys.)  

## pasos:

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
 2. *Comprueba la lista de directorio para ver si ya tiene una clave SSH pública (.pub)*
 ~~~
        id_rsa.pub
        id_ecdsa.pub
        id_ed25519.pub
 ~~~  

 3. *Generar una nueva clave SSH*  

       `ssh-keygen -t ed25519 -C "your_email@example.com"`  
       **Nota** No admite el algoritmo Ed25519, usa:  
       `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`  
       Cuando se le pida, escriba una frase de contraseña segura.  
       `Enter passphrase (empty for no passphrase): [Type a passphrase]`  
       `Enter same passphrase again: [Type passphrase again]`  

 4. *Agregar tu clave SSH al ssh-agent*  
 Asegúrate de que el agente ssh se esté ejecutando  
 Este comando ``` eval `ssh-agent -s`  ``` inicializará el agente en segundo plano y establecerá las variables de entorno apropiadas.  
~~~
       Agent pid 794
~~~  
 5. *Agregue la clave privada SSH al **agente** ssh.*
 
       ```ssh-add c:/Users/YOU/.ssh/id_ed25519``` ó mediante ` ssh-add ~/.ssh/id_ed25519`  

Si la contraseña fue enter si no ingresar password
~~~
       Identity added: /c/Users/User/.ssh/id_ed25519 (jrichip@hotmail.com)
~~~ 

   
 6. *Agregar una clave SSH nueva a tu cuenta de GitHub*  
 