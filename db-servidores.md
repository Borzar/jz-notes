# Servidores 

Son maquinas computudadores (fisicas o virtuales) que son capaces de realizar(proveer) algun tipo de servicio como por ejemplo:
  Servidor web.
  Servidor de correo electronico
  Servidor de base de datos.
  Servidor de archivos
  Servidor de aplicaciones
  Servidor proxy
  Servidor DNS
  Servidor de impresion
  Servidor de juegos 
  Servidor de almacenamiento de red 
  Servidor de chat

# Base de datos y despliegue

Las bases de datos pueden estar en local, en un servidor de produccion/test o un la nube.
Para desplegar una base de datos local a la nube(o servidor destino) se deben generar
scrips para generar la misma structura (la misma estructura que se encuentra en local)
y los datos que se quieran migran desde la db local a la base de datos que se usara en produccion o test.
(en palabras simples se realizar una migración).
Luego, asegurarce de actualizar la cadena de conexion que apunte al servidor destino o la
base de datos desplegada.
