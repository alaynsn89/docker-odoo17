# Instalando Odoo v17

- Instala docker y docker compose
Desde las fuentes [docker](https://docs.docker.com/get-docker/) y [docker-compose](https://docs.docker.com/compose/install/) para tu sistema operativo

Clona este repositorio:

``` sh
git clone https://github.com/alaynsn89/docker-odoo17.git
```

Accede al repositorio descargado

``` sh
cd docker-odoo17/
```

# Descargue e inicie los contenedores

Escriba el comando:
``` sh
docker-compose up -d
```
Abre en el navegador `localhost:8069` y tendrá acceso a Odoo 17. (Master password por defecto: `master`)

# Permisos
Dependiendo de su sistema operativo puede ser que necesite permisos en los siguientes directoios de este repositorio:

``` sh
$ sudo chmod -R 777 addons
$ sudo chmod -R 777 etc
$ sudo chmod -R 777 postgresql
```

# Puertos 
- Si necesita un puerto diferente para su instancia, cambie **8069** por otro valor en el fichero **docker-compose.yml** ejemplo de la sigueinte manera:

```
ports:
 - "4001:8069"
```

## Complementos Perzonalizados

El directorio **addons/** contiene addons personalizados. Pon tus addons personalizados si tienes alguno.

## Configuración y Logs de Odoo

* Si necesita cambiar alguna configuración, edite el archivo: **etc/odoo.conf**.
* Archivo de Log **etc/odoo-server.log**
* Master Password (**admin_passwd**) por defecto `master`, puede cambiarlo en it @ [etc/odoo.conf#L60](/etc/odoo.conf#L60)
* Desarrollo **dev_mode** Aquí, `reload` significa que Odoo recargará automáticamente los módulos cuando haya cambios detectados en los archivos del código fuente o en los archivos de la vista. Puede cambiarlo en it @ [etc/odoo.conf#L342](/etc/odoo.conf#L342)

## Comandos Útiles

**Iniciar Odoo**:

``` bash
docker-compose up -d
```

**Reiniciar Odoo**:

``` bash
docker-compose restart
```

**Parar Odoo**:

``` bash
docker-compose down
```

## docker-compose.yml

* odoo:17
* postgres:16

