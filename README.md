# notes

GITHUB
git config --global user.name "ususario"
git config --global user.email "correo"
1.- ssh-keygen -t rsa -b4096 -C 'tucorreo@.com'
2.- eval "$(ssh-agent -s)"
3.- cat ~/.ssh/id_rsa.pub

PHPMYADMIN
sudo /opt/lampp/lampp start
cd /opt/lampp
sudo ./manager-linux-x64.run

FUNCIONES TERMINAL
tty-clock -C   reloj
ranger  explorador
tmux    dividir terminal
nano ~/.bashrc  crear atajos rerminal

ATAJOS TERMINAL

nano ~/.bashrc #abrir archivo atajos

alias update='sudo apt update && sudo apt upgrade'
alias add='git add'
alias commit='git commit'
alias gs='git status'
alias off='shutdown now'
alias init='git init'

source ~/.bashrc #cargar atajos


https://github.com/cronwell30

https://www.youtube.com/watch?v=5kWLE1Eu7LU

---------------------------------------------------------------------
INSTALACION

# Instalar PostgreSQL
sudo apt install postgresql postgresql-contrib

# Verificar estado del servicio
sudo systemctl status postgresql

# Vercion 
psql --version

# Cambiar al usuario postgres
sudo -i -u postgres

# Habilitar inicio automático
sudo systemctl enable postgresql

# Cambiar al usuario postgres
sudo -i -u postgres

# Cambiar al usuario postgres
sudo -i -u postgres

# Acceder a la consola de PostgreSQL
psql 
sudo -u postgres psql #estas opciones son a elegir

# usuario
-- Crear un nuevo usuario/rol
CREATE USER mi_usuario WITH PASSWORD 'tu_contraseña';

-- Otorgar privilegios
GRANT ALL PRIVILEGES ON DATABASE mi_base_datos TO mi_usuario;

-- Usuario con privilegios específicos
CREATE USER mi_usuario WITH 
    PASSWORD 'mi_pass123'
    CREATEDB    -- Puede crear bases de datos
    CREATEROLE  -- Puede crear roles
    LOGIN       -- Puede conectarse
    VALID UNTIL '2025-12-31';  -- Expiración opcional


MODIFICACION DE USUARIOS

-- Cambiar contraseña
ALTER USER nombre_usuario WITH PASSWORD 'nueva_contraseña';

-- Agregar privilegios
ALTER USER nombre_usuario CREATEDB CREATEROLE;

-- Quitar privilegios
ALTER USER nombre_usuario NOCREATEDB NOCREATEROLE;

-- Cambiar fecha de expiración
ALTER USER nombre_usuario VALID UNTIL 'infinity';

-- Renombrar usuario
ALTER USER nombre_usuario RENAME TO nuevo_nombre;

-- Eliminar usuario con todos sus objetos
DROP USER nombre_usuario CASCADE;

PRIVILEGIOS

-- Verificar tus propios privilegios
SELECT current_user, usesuper FROM pg_user WHERE usename = current_user;