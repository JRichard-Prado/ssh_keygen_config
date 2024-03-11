 # Acerca de la claves SSH  

## Generando tu clave pública SSH:

Para más detalles sobre cómo crear unas claves SSH en variados sistemas operativos,  
consultar la correspondiente guía en GitHub: *[Generación de una nueva clave SSH y adición al agente SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)* 

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

       ```  
       Generating public/private ed25519 key pair.
       Enter file in which to save the key (/c/Users/User/.ssh/id_ed25519):
       Created directory '/c/Users/User/.ssh'.
       Enter passphrase (empty for no passphrase):
       Enter same passphrase again:
       Your identification has been saved in /c/Users/User/.ssh/id_ed25519
       Your public key has been saved in /c/Users/User/.ssh/id_ed25519.pub
       The key fingerprint is:
       SHA256:EVMuA3Nob3KDeAJgjuv0EBpt2DipUOvsUKnzbI8VNwU jrichip@hotmail.com
       The key's randomart image is:
       +--[ED25519 256]--+
       |.o.   E.+..      |
       |+B.o  o= +       |
       |OoB. o o= .      |
       |+X. o +.=+       |
       |Boo .oo+S.       |
       |o*o  o .         |
       | .=..            |
       | . +             |
       |  . .            |
       +----[SHA256]-----+      
       ```  
4. *Agregar tu clave SSH al ssh-agent*  

 Asegúrate de que el agente ssh se esté ejecutando. Este comando ``` eval `ssh-agent -s`  ``` inicializará el agente en segundo plano y establecerá las variables de entorno apropiadas.  
~~~
       Agent pid 794
~~~  
5. *Agregue la clave privada SSH al **agente** ssh.*
 
```ssh-add c:/Users/YOU/.ssh/id_ed25519``` ó mediante ` ssh-add ~/.ssh/id_ed25519`  

Muestra agreagdo si la  contraseña fue enter si no ingresar password
~~~
       Identity added: /c/Users/User/.ssh/id_ed25519 (jrichip@hotmail.com)
~~~ 
Para cambiar contraseña `ssh-keygen -p -f ~/.ssh/id_ed25519
`
~~~
       Key has comment 'jrichip@hotmail.com'
       Enter new passphrase (empty for no passphrase):
~~~  
**Nota:** Para eleiminar utilice SSH KEY `rm -rf ~/.ssh/`
   
6. *[Agregar una clave SSH nueva a tu cuenta de GitHub](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)*  


 Copia la llave SSH pública a tu portapapeles. `clip < ~/.ssh/id_ed25519.pub `  

 * Haga clic en la foto del [perfil](https://github.com/settings/keys) y, luego, en Settings (Configuración).
 * Haga clic en [Nueva clave SSH](https://github.com/settings/ssh/new) o en Agregar clave SSH.  
 * En el campo "Clave" `nano ~/.ssh/id_ed25519.pub`, pega tu clave pública.
 * Si se te solicita, confirma tu contraseña en GitHub

