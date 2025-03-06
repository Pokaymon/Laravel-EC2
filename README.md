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
php artisa --version
```

### ⚙️ **Crear Proyecto**

