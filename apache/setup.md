* start VM

* add inbound rule for HTTP and HTTPS

* sudo apt-get update

* sudo apt-get install apache2

* check if http://vmp-ip is working

* at this point you can set domain A name record pointing to this IP

* sudo a2enmod proxy

* sudo a2enmod proxy_http

* sudo systemctl apache2 restart

* run webserver process (on non-80 port)


