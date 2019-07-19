## Instalar paquetes:

apt install nagios-nrpe-server nagios-plugins

## Modificar regla de acceso:

vim /etc/nagios/nrpe.cfg

### Buscamos la línea

allowed_hosts=127.0.0.1

### Y la cambiamos por:

allowed_hosts=127.0.0.1,[IP del NAGIOS]

## Añadimos definiciones de chequeos personalizados

vim /etc/nagios/nrpe_local.cfg

### Lista de chequeos personalizados:

Ojo, en el primer chequeo que viene ahora hay que modificar /dev/vda1 por el dispositivo de tu servidor.
Puedes ver la lista de dispositivos de disco con el comando lsblk 

```
command[check_root]=/usr/lib/nagios/plugins/check_disk -w 20% -c 10% -p /dev/vda1
command[check_peers]=/usr/lib/nagios/plugins/check_peers
command[check_load]=/usr/lib/nagios/plugins/check_load -r -w .70,.70,.70 -c .90,.80,.70
```

## Subimos nuestros scripts de checkeos

```
scp check_root [user]@[ip]:/tmp
scp check_peers [user]@[ip]:/tmp
scp check_mem [user]@[ip]:/tmp
```

Y luego desde dentro de la máquina los copiamos a su destino

cp /tmp/check_* /usr/lib/nagios/plugins/

## Paramos y arrancamos el servicio nagios-nrpe-server

```
/etc/init.d/nagios-nrpe-server stop
/etc/init.d/nagios-nrpe-server start
```

