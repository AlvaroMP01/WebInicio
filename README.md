# Despliege de una Página Web

## Creación de un Proyecto Web con Git, Node.js y Vite

### 1. Crear una carpeta y configurar el repositorio local

```bash
mkdir RepositorioWeb
cd RepositorioWeb/
```

### Crear un nuevo directorio y configurarlo para Git

```bash
mkdir WebInicio
cd WebInicio/
git init
git branch -M main
```

### 2. Instalar Node.js y verificar versiones

```bash
node -v        # Verificar versión de Node.js
npm --version  # Verificar versión de npm
```

### 3. Crear un proyecto con Vite

```bash
cd WebInicio
npm create vite@latest
```

#### 3.1. Seleccionar la tecnología de desarrollo deseada

- Damos Enter, seleccionamos Vanilla y elegimos JavaScript.

### 4. Conectar el proyecto con GitHub y configurar el entorno

```bash
npm install     # Instala todas las dependencias
npm run dev     # Inicia el servidor de desarrollo de Vite
```

### Modificar el script en package.json

- Cambiar "dev" por "start" para facilitar el inicio del proyecto

___Crear estructura básica en index.html escribiendo '!' y presionando Enter___

#### La dirección del servidor local será: http://localhost/

### 5. Subir el proyecto a GitHub

```bash
git add . && git commit -m "Created Web Inicio"
git status -s   # Verificar que no haya cambios pendientes
```

### 6. Crear un repositorio en GitHub con el nombre 'WebInicio' (sin README, .gitignore ni licencia)

```bash
git remote add origin git@github.com:usuario/WebInicio.git
git push -u origin main
```

### 7. Haremos commit para subir el ejemplo de pagina web creado con Vite

```bash
git add . && git commit -am “Created example Vite”
git status -s
```

### 8. Haremos un pull antes de hacer un push a Github

```bash
git pull origin main
```

### 9. Haremos un push a Github

```bash
git push origin main
```

# Creación de una clave SSH

### 1. Nos situamos en la carpeta de usuario (c/users/usuario)

```bash
cd c/users/usuario
```

### 2. Comprobar si tenemos una clave SSH creada

```bash
cd .ssh
```

Si al ejecutar este comando **solo** nos aparece algo parecido a esto:

```bash
known_hosts
```

Entonces no tenemos ninguna clave SSH creada.

### 3. Crear una clave SSH

```bash
ssh-keygen -t ed25519 -C "email"
```

Damos _enter_ tres veces para confirmar la clave.

### 4. Copiar la clave SSH

En PowerShell:

```powershell
Get-Service -Name ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent
ssh-add c:/Users/usuario/.ssh/id_ed25519
```

### 5. Ahora añadir la clave SSH

En Bash:

```bash
cat id_ed25519.pub
```

Seleccionar la clave y copiarla.
En los ajustes de GitHub buscamos SSH and GPG keys, ponemos un título, _autenthication key_ y en _key_ pegamos lo copiado, le damos a _add_ para añadir la clave.

### 6. Comprobar la clave SSH

Para comprobar que la clave SSH se ha creado correctamente:

```bash
ssh -T git@github
```

### Comprobamos que estemos en el directorio SSH

```bash
pwd
```

### Salimos del directorio SSH

```bash
cd..
```

### Entramos en la carpeta del repositorio

```bash
cd /Documents/RepositorioWeb/WebInicio
```

Una vez tengamos todos estos pasos anteriores ya podremos hacer un _push_ a GitHub correctamente.

```bash
git pull origin main
git push origin main
```

# Modificar el archivo .html creado en Visual Studio Code

- Creamos un encabezado h2 y ponemos nuestro nombre.

 ```bash
 <h2>@AlvaroMP01</h2>
 ```

- Creamos un parrafo con el enlace a nuestro github.

```bash
<p>
    <a href="https://github.com/AlvaroMP01">Mi GitHub</a>
</p>
```

## En la terminal Bash de Visual Studio Code

Hacemos un _commit_ de los cambios que hemos hechco en el archivo index.html.

```bash
git add . && git commit -m "Modified index.html"
```

## En la terminal Bash fuera de Visual Studio Code

Hacemos un _push_ de los cambios que hemos hecho en el archivo index.html.

```bash
git push origin main
```
