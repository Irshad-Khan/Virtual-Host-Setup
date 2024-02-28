# Settingup Virtual Host

## Introduction
Fellow below steps for setting up a virtual host.

## Step 1: Apache Install Karein (Agar nahi hai)

Ubuntu mein Apache ko install karne ke liye terminal kholen aur ye command type karein:

```bash
sudo apt update
sudo apt install apache2
```

## Step 2: Virtual Host File Banayein

- Terminal kholen.
- Naye virtual host file banane ke liye ye command likhein:

```bash
sudo nano /etc/apache2/sites-available/dastak-irshad.conf
```

- Ab is file mein neeche diye gaye code ko paste karein aur save karein (Ctrl + X, phir Y, phir Enter):

```bash
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName www.dastak-irshad.punjab.gov.pk
    DocumentRoot /var/www/dastak-irshad
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

## Step 3: Website Directory Banayein

- Terminal mein ye command type karein taaki nayi directory ban sake:

```bash
sudo mkdir /var/www/dastak-irshad
```

- Is directory mein jaane ke liye ye command type karein:

```bash
cd /var/www/dastak-irshad
```

- Sample HTML file banane ke liye ye command type karein:

```bash
sudo nano index.html
```

- Ab kuch basic HTML code paste karein aur save karein (Ctrl + X, phir Y, phir Enter):

```bash
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Dastak Irshad</title>
</head>
<body>
    <h1>Welcome to Dastak Irshad!</h1>
    <p>This is a sample webpage for testing virtual hosting.</p>
</body>
</html>

```

- Website directory ke liye permission set karein:

```bash
sudo chown -R $USER:$USER /var/www/dastak-irshad
sudo chmod -R 755 /var/www/dastak-irshad

```

## Step 4: Virtual Host Enable Karein

- Virtual host ko enable karein:

```bash
sudo a2ensite dastak-irshad.conf

```

- Changes ko apply karne ke liye Apache ko restart karein:

```bash
sudo systemctl restart apache2


```