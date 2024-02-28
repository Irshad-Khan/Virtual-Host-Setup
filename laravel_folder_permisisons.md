# Settingup Virtual Host

## Introduction
Fellow below steps for setting up to set permissions.

## Step 1: Set permissions to storage folder:

Open a terminal and create a new virtual host configuration file:

```bash
sudo chown -R $USER:www-data storage
sudo chown -R $USER:www-data bootstrap/cache

chmod -R 775 storage
chmod -R 775 bootstrap/cache
```