# Settingup Virtual Host

## Introduction
Fellow below steps for setting up to redirect one domain to other.

## Step 1: Create a Virtual Host Configuration:

Open a terminal and create a new virtual host configuration file:

```bash
sudo nano /etc/apache2/sites-available/dastak-irshad-service.conf
```

## Step 2: Configure the Virtual Host:

```bash
<VirtualHost *:80>
    ServerName www.dastak-irshad-service.punjab.gov.pk
    Redirect permanent / http://www.dastak-irshad.punjab.gov.pk/
</VirtualHost>

```

## Step 4: Virtual Host Enable Karein

- Virtual host ko enable karein:

```bash
sudo a2ensite dastak-irshad-service.conf

```

- Changes ko apply karne ke liye Apache ko restart karein:

```bash
sudo systemctl restart apache2


```