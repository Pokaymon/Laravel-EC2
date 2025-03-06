# Laravel-EC2
Como montar Laravel en EC2

## 🚀 **Actualizar**
```bash
sudo apt-get update -y
sudo apt-get upgrade -y
```

### 📂 **Apache**
```bash
sudo apt-get install apache2
sudo systemctl enable apache2
sudo systemctl start apache2
sudo systemctl status apache2
```

### 💻 **Php (Ultima Version)**
```bash
sudo apt-get install php php-cli php-common php-imap php-redis php-snmp php-xml php-zip php-mbstring php-curl
php -v
```

### 🎶 **Curl y Composer**
```bash
sudo apt install curl
sudo apt install composer
composer
```

### ⚙️ **Crear Proyecto**
```bash
cd /var/www/html
sudo composer create-project laravel/laravel "project"
cd project/
php artisan --version
```

#### 🔑 **Cambiar propietario de todos los archivos y directorios en el proyecto a www-data(usuario y grupo utizado por Apache)**
```bash
sudo chown -R www-data:www-data .
```

#### 🔗 **Ajusta los permisos del directorio storage para que el servidor web tenga los permisos adecuados de lectura, escritura y ejecución**
```bash
sudo chmod -R 775 storage/
```

### 🏛️ **Crear archivo de host virtual**
#### 🗄️ **Directorio de configuraciones de sitios de Apache**
```bash
cd /etc/apache2/sites-available/
```

#### 🌍 **Abre editor de texto gedit/nano para editar el archivo de configuración del host virtual de Laravel**
```bash
sudo gedit laravel.conf
```

#### 📄 **Pega el siguiente Código**
```bash
<VirtualHost *:80>
   ServerName @localhost
   DocumentRoot /var/www/html/project/public
   <Directory /var/www/html/project>
       AllowOverride All
   </Directory>
   ErrorLog ${APACHE_LOG_DIR}/error.log
   CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

#### 🔄 **Habilite la configuración de apache para laravel**
```bash
sudo a2ensite laravel.conf
```

#### 📦 **Verifique sintaxis (para asegurar que no haya errores)**
```bash
sudo apachectl -t
```

#### 📟 **Reinicie servidor Apache**
```bash
sudo systemctl reload apache2
```
