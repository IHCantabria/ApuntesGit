# Configuración para Github

Antes de poder trabajar con los repositorios de GitHub que tiene el IH debemos realizar una serie de pasos:

## Registro en GitHub

GitHub funciona totalmente independiente a unican, por tanto debemos crearnos un nuevo usuario que no va a tener relación con el existente de unican.  
Al registrarnos podemos elegir un nombre de usuario que no tiene por qué coincidir con el de unican, lo mismo con el email y, por supuesto, la contraseña a utilizar.

Una vez tengamos la cuenta creada, nos deben dar de alta en la organización creada dentro de GitHub, para ello mandamos un email a felipe.maza@unican.es con el nombre de usuario que hayáis elegido, y al grupo de trabajo al que pertenecéis.

Una vez dados de alta, tendremos acceso de lectura a todos los repositorios existentes en el IH, y en los repositorios de vuestro grupo tendréis también para escritura.

## Vincular clave SSH

Para que nuestro programa de `git` pueda conectarse fácilmente con GitHub debemos configurar claves `SSH`. En caso de que no las tengamos, debemos generar unas nuevas:

```sh
ssh-keygen -t ed25519
```

```
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/mazaf/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/mazaf/.ssh/id_ed25519
Your public key has been saved in /home/mazaf/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:wXt4cQ/lP3EA+Pmn3g/Y4HCi8stuGM//kjZ1MaumAX4 mazaf@IHPC20
The key's randomart image is:
+--[ED25519 256]--+
|           ...o  |
|       .  .  o . |
|        o ..o....|
|         + oooo.o|
|        S = o..=.|
|      .. = =.++ o|
|      .=o Eooooo |
|      .++.=.o .o |
|       o=+o*... +|
+----[SHA256]-----+
```

Cuando nos pida la contraseña, podemos dejar el campo vacío, pues para utilizar las claves previamente hemos debido desbloquear nuestra cuenta unican.

Ahora tendremos dos ficheros dentro de la carpeta `~/.ssh`: `id_ed25519` y `id_ed25519.pub`.

El contenido del fichero público debemos copiarlo a nuestra cuenta

```sh
cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIF21VhCkpHPYM9v/QYDLj23xXuX2m7NpUZh283OHKMaJ mazaf@IHPC20
```

En la página de [configuración de nuestro usuario](https://github.com/settings/profile) en GitHub, tenemos una sección llamada [SSH and GPG Keys](https://github.com/settings/keys).  

Damos sobre New SSH Key y en la caja de texto `key` copiamos la clave (toda la línea, completa).
