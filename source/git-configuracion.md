# Configuración de git

## Configuración mínima

La configuración general de git la encontramos en el fichero `~/.gitconfig`.

Los datos mínimos que tenemos que tener configurados son:

- Datos de usuario, para saber quién es el autor del commit y su email.
- Rama por defecto, el nombre por defecto cuando trabajamos con un repositorio (usaremos `main`).
- Editor a utilizar por defecto, podemos configurar `vim`, `nano`, `notepad` o cualquiera con el que estemos cómodos trabajando.
  
```ini
[user]
        email = felipe.maza@unican.es
        name = Felipe Maza
[init]
        defaultBranch = main
[core]
        editor = vim
```

## Otras configuraciones

- Coloreado de código

```ini
[color]
    ui = auto
```

- Alias. Crea abreviaturas para comandos más extensos y complejos

```ini
[alias]
    co = checkout
    st = status

    lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
    lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
    lg = !"git lg1"

    undo = reset --soft HEAD^ 
    # ¡Cuidado! Si ya has hecho un push, habrá problemas al reescribir el historial
    # https://git-scm.com/docs/git-reset#git-reset-emgitresetemltmodegtltcommitgt

    stash-all = stash save --include-untracked
    # https://git-scm.com/docs/git-stash
      
```
