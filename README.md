## Acerca de la BitLana

La BitLana es una criptomoneda enfocada en proveer un mecanismo descentralizado de intercambio y anonimidad por medio de transacciones no rastreables y no vinculables.

¡La BitLana es de todos! El código es completamente abierto y gratuito para usar sin restricción alguna, excepto las especificadas en la licencia.

Si quieres hacer algún cambio al código, por favor haz un pull request en la rama master.

Puedes conocer más de esta criptomoneda en [https://www.bitlana.com](https://www.bitlana.com)

## Acerca de bitlana-explorer

Explorador de bloques experimental para la BitLana [BLANA].

### Instalación en Ubuntu 16.04
1) Configura tu servidor web

```bash
sudo apt-get install apache2
sudo apt-get install php libapache2-mod-php php-mcrypt php-curl
sudo a2enmod headers
sudo vim /etc/apache2/sites-available/explorer.bitlana.com.conf

  <VirtualHost *:80>
      ServerAdmin webmaster@explorer.bitlana.com
      ServerName explorer.bitlana.com
      ServerAlias www.explorer.bitlana.com
      DocumentRoot /var/www/explorer.bitlana.com/public_html/
      ErrorLog /var/www/explorer.bitlana.com/logs/error.log
      CustomLog /var/www/explorer.bitlana.com/logs/access.log combined
      <Directory /var/www/explorer.bitlana.com/public_html/>
        Options FollowSymLinks
        AllowOverride All
        Require all granted
      </Directory>
  </VirtualHost>

sudo mkdir -p /var/www/explorer.bitlana.com/public_html
sudo mkdir -p /var/www/explorer.bitlana.com/logs
sudo touch /var/www/explorer.bitlana.com/logs/error.log
sudo touch /var/www/explorer.bitlana.com/logs/access.log
sudo a2ensite explorer.bitlana.com
sudo service apache2 reload
```

2) Ejecuta el demonio de BitLana de la siguiente manera:
```bash
./bitlanad --enable-cors=* --enable_blockexplorer --rpc-bind-ip=0.0.0.0 --rpc-bind-port=27175
```
3) Clona este repositorio a tu servidor web y configura la variable `api` en el archivo`config.js` para apuntar a tu demonio.

## Comunidad y soporte

Nos puedes encontrar en:

[Comunidad oficial de Telegram](https://t.me/bitlana)

## License

bitlana-explorer está licenciado bajo la GNU Lesser General Public License v3.0.

## Créditos

Basado en [https://github.com/Karbovanets/Karbowanec-Blockchain-Explorer](https://github.com/Karbovanets/Karbowanec-Blockchain-Explorer)

