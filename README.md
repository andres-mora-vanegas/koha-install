# koha-install

## this is the link of the documentation
https://wiki.koha-community.org/wiki/Debian

![alt text](koha.jpg?raw=true)

### get the repo
```sh
sudo wget -q -O- https://debian.koha-community.org/koha/gpg.asc | sudo apt-key add -

echo 'deb http://debian.koha-community.org/koha stable main' | sudo tee /etc/apt/sources.list.d/koha.list
```
### update repos
```sh
sudo apt-get update
```
### select repo
```sh
echo 'deb http://debian.koha-community.org/koha 18.05 main' | sudo tee /etc/apt/sources.list.d/koha.list
```

### update repos
```sh
sudo apt-get update
```

### install koha
```sh
sudo apt-get install koha-common -y
```

### install mariadb
```
sudo apt-get install mariadb-server -y
```
### edit config of koha settings

```sh
sudo nano  /etc/koha/koha-sites.conf
```
### contents of file

```sh
#put 
INTRAPORT="8084"
INTRAPREFIX=""
INTRASUFFIX="-intra"
OPACPORT="8085"
#
```

### install apache configs
```sh
sudo a2enmod rewrite 
sudo a2enmod cgi 
sudo service apache2 restart
```
### create instance
```sh
sudo koha-create --create-db libraryname
```
### create admin password
```sh
sudo koha-passwd libraryname
```
#### copy the password result

#### user user koha_libraryname and password the copied

### instalación de idioma español
```sh
sudo koha-translate --install es-ES
```

### config the ports used in past config}
```sh
sudo nano /etc/apache2/ports.conf
```
#### content of file
```sh
Listen 8084
Listen 8085
```
### reload apache
```sh
sudo service apache2 restart
```

* enter to http://localhost:8084 and config koha, inside of config only need to select next, next, next, the language, super admin config account and password, next, next and finish.
