# Git_cheatsheet

<https://git-scm.com/>

## Identity

    git config --global user.name "Victor"
    git config --global user.email victor@git.com

## Editor

    # <tool>: code, vim, notepad++ ...
    git config --global core.editor code

## Herramienta show diff

    git config --global merge.tool vimdiff

# BASIC COMMANDS

    # Clonar repo
    git clone

    # Recibir cambios del repo remoto
    git pull

    # Ver estado repo
    git status

    # Añadir modificaciones (stage fase)
    git add file
    git add . 

    # Confirmar los cambios
    git commit
    git commit -m "description"

    # Subir los cambios al repo
    git push
    git push -u origin master
    git push -u origin release-1.0

## Subir código local a repo

    git init
    git add .
    git commit -m "initial commit"

## Centralización de código compartido

    # En el server
    mkdir project.git
    cd project.git
    git init --bare

    # En nuestra carpeta
    git remote add origin user@server:/path/to/the/project.git
    git push -u origin master

## Mantener cambios sin hacer commit

    # Guardando cambios sin hacer commit (archivos en modified - stash)
    git stash
    # Mostrar los stash realizados
    git stash list
    # Aplicar stash (lo elimina y lo aplica al proyecto)
    git stash pop

# Branchs

    # ver las ramas
    git branch
    #elegir una rama
    git checkout master
    # crear
    git branch <new_brach>

    # crear rama remota
    git remote add origin https://github.com/victor/my-repo
    git push -u origin <new_branch>

    # Crear una rama remota sin estar enlazada con una rama local
    git push origin HEAD:only-emote-branch

## Branchs merge

    #Fusionar branchs (merge)
    git merge <branch_name>

    # Guardarlos en el stash
    git stash               # agregarlos al stash
    git merge new-features  # fusionarlos
    git stash pop           # obtén los cambios devuelta al árbol de trabajo (working tree)

    # Abandonar todos los cambios
    git reset --hard        # descarta todos los cambios pendientes

## Rebase (hacer solo en local)
