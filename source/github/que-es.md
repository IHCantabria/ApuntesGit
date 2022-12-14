# GitHub

## Qué es

GitHub es una plataforma para alojar repositorios git, con diferentes características que facilitan el desarrollo de los mismos a la comunidad.

GitHub es, primeramente, un servidor donde alojar repositorios git y es el más importante, es utilizado por los principales proyectos de software.  
Pertenece a Microsoft y su uso a diferencia de teams, es independiente de unican, por lo que el registro de usuarios y su gestión es independiente de la universidad.  
Tenemos creado una organización donde alojamos todos los repositorios con los que trabajamos, tanto los públicos como privados.  
Realizamos un backup periódicamente.

## Gestión y permisos de repositorios

Los repositorios pueden ser de dos tipos:

- Públicos: Cualquier persona puede leer el repositorio completo. No requiere registro en plataforma.
- Privados: Solo el propietario y a las cuentas que este asigne tendrán acceso al repositorio.

Existen diferentes niveles de acceso a un repositio, los principales son:

- Read, puede consultar todo el repositorio pero no puede subir sus cambios.
- Write, además de leer, puede subir nuevos cambios, gestionar incidencias y pull request.
- Admin, además de los permisos de escribir, puede añadir nuevos modificar la configuración del repositorio y añadir colaboradores.

## Cambiando propietario o nombre de proyecto

Cuando cambiamos el propietario o el nombre del proyecto, la URL del repositorio remoto también cambia, por ello debemos quitar el vínculo existente y añadir el nuevo.

Retirar el vínculo obsoleto:

```sh
git remote remove origin
```

Y añadimos el nuevo:

```sh
git remote add origin git@github.com:IHCantabria/NombreDelRepositorio.git
```

La palabra `origin` que se utiliza en ambos casos es el alias por defecto que se le asigna al repositorio remoto principal. Un repositorio git puede estar vinculado con diferentes repositorios remotos.
