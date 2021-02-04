# Práctica: HTTPS con Lets's Encrypt y Cerbot 

**HTTPS** (Hyptertext Transfer Protocol Secure) o protocolo seguro de transferencia de hipertexto, es un protocolo de la capa de aplicación basado en el protocolo HTTP, destinado a la transferencia segura de datos de hipertexto.

**Let’s Encrypt**​ es una autoridad de certificación que se puso en marcha el 12 de abril de 2016 y que proporciona certificados X.509 gratuitos para el cifrado de seguridad de nivel de transporte (TLS) a través de un proceso automatizado diseñado para eliminar el complejo proceso actual de creación manual, la validación, firma, instalación y renovación de los certificados de sitios web seguros.

## Requisitos: 

Necesitamos que estén los puertos habilitados:

- SSH: 22/TCP
- HTTP: 80/TCP
- HTTPS: 443/TCP

Dentro de nuestra máquina debemos deberemos instalar un sitio web, como por ejemplo un Wordpress. 

## Pasos a seguir: 

Registraremos nuestro nombre de dominio el algún proveedor de nombre de dominio, como en por ejemplo Freenom. En mi caso mi nombre de dominio lo he llamado: **practicaiaw.ml**

Dentro de nuestro dominio configuraremos los registros DNS. Añadiremos la IP pública de nuestra máquina, un registro estará en blanco y otro con las www. 

```
NOTA: Tendremos que esperar que los cambios en el DNS se propaguen, podemos comprobar su estado dentro de dnscheker.org.
```

## Paso Cerbot: 

Para poder obtener un certificado de Let’s Encrypt para un dominio de un sitio web es necesario demostrar que se tiene control sobre ese dominio. Para realizar esta tarea es necesario utilizar un cliente del protocolo ACME (Automated Certificate Management Environment)

Dentro de la página le asignaremos el tipo de software y sistema opertivo que estamos usando ya que así nos dará las directrices de como instalarlo: 

- En nuestro caso: Apache y Ubuntu 20.04
```
https://certbot.eff.org/lets-encrypt/ubuntufocal-apache
```

Y finalmente instalamos nuestro servidor web. 
