# P4: Servidores virtuales de Apache

## EJERCICIO

***Crea dos sitios web que compartirán IP y puerto, pero tendrán nombres DNS distintos 
para acceder a ellos. El nombre del primer dominio será daw.gimbernat.eug.es y el 
segundo tunombreyapellidos.gimbernat.eug.es, donde “tunombreyapellidos” contiene 
la inicial de tu nombre, el primer apellido, y la inicial de tu segundo apellido. De esta 
manera, si tu nombre es: Francisco Mesas Cervilla, el domino quedaría: 
fmesasc.gimbernat.eug.es.***

*• En el primer caso, daw.gimbernat.eug.es tendrá su directorio base en 
/var/www/daw/ conteniendo una página llamada index.html que ponga el 
nombre de la clase como título con un archivo css para aplicarle estilos al título.*

*• En el segundo caso, fmesasc.gimbernat.eug.es tendrá su directorio base en 
/var/www/fmesasc/ (el equivalente para vuestros nombres), conteniendo una 
página llamada index.html que contenga vuestro currículum aplicándole un 
estilo css para que se visualice correctamente.*

***Para ello, tendrás que crear un archivo de configuración (copiado de 000-default.conf) 
para cada uno de los dominios. Recuerda que con a2ensite puedes crear los enlaces 
simbólicos necesarios para añadir esta configuración a la ejecución de apache.***

## RESOLUCIÓN

Primero de todo comprobar que el apache esta bien instalado y funciona, para ello introduciremos la IP del servidor.

![image](https://user-images.githubusercontent.com/113515330/202173045-f3b6f64f-90b9-405b-8e34-909d1244b090.png)
*Podemos ver que tenemos la practica anterior por lo tanto Apache funciona correctamente.*


Ahora ya podemos empezar de forma segura este nuevo ejercicio, el primer paso es acceder al archivo de configuraciñon de Apache
y modificar/comprobar que tenemos el siguiente texto:

![image](https://user-images.githubusercontent.com/113515330/202173754-e7f69834-f468-4a8a-8da1-9a5402e14bca.png)

Haremos la configuración de los Virtual Hosts.

![image](https://user-images.githubusercontent.com/113515330/202183680-b8f0df28-2040-448d-a057-ac5a9f5c4bd4.png)

Crearemos un fichero de Virtual Host, que llamaremos mas adelante.

![image](https://user-images.githubusercontent.com/113515330/202184933-2b8badae-d706-4d98-8dab-14a4e0ea84f6.png)

Y comprobamos que este se haya creado correctamente, y este dispuesto.

![image](https://user-images.githubusercontent.com/113515330/202185041-76b1ad92-b6ae-4a22-b8cf-0401e47db0ed.png)

Luego nos pondremos en modo superuser, y a continuación creamos las dos carpetas (daw.gimbernat.eug.es y rperezma.gimbernat.eug.es)

![image](https://user-images.githubusercontent.com/113515330/202177221-deff15fb-4819-4cfc-a460-81d3d020bdf1.png)
![image](https://user-images.githubusercontent.com/113515330/202177289-4b8df79a-dc30-4c34-b927-99bb9e8a0abe.png)

Ahora veremos la estrcutura para ver que las carpteas se han creado correctamente (instalamos tree para mejor visualización):

![image](https://user-images.githubusercontent.com/113515330/202177456-6bc7e582-87f2-41b5-a32a-79ce3487b0ee.png)
![image](https://user-images.githubusercontent.com/113515330/202177503-d2df6d11-1f28-4dfa-8caa-8281170824b1.png)

Esta es la carpeta de html de *rperezma*.

![image](https://user-images.githubusercontent.com/113515330/202190599-0417f885-9c80-478d-99f5-e7f3b82503c2.png)

Volvemos a la carpeta de host *rperezma* y pondremos el archivo VH.

![image](https://user-images.githubusercontent.com/113515330/202190179-b927bef4-becd-4700-8209-e447d9bc4805.png)

Esta es la carpeta de html de *daw*.

![image](https://user-images.githubusercontent.com/113515330/202190684-ffd7e0d4-fc41-4d76-8f6b-4e84efac5d09.png)

Volvemos a la carpeta de host *daw* y pondremos el archivo en el VH.

![image](https://user-images.githubusercontent.com/113515330/202190979-868044b2-86b0-4a8f-8b3a-d5bddc7e8cbb.png)

**IMPORTANTE** Este paso permite que las peticiones web que se hagan desde el mismo servidor lleguen a la interfaz de Apache y este pueda responder como
el VirtualHost configurado.

*Introducimos el comando /etc/hosts y escribimos la IP y a continuación nuestros dominio*

![image](https://user-images.githubusercontent.com/113515330/202179830-1447df9e-8741-4df5-9509-93123b48d111.png)

Ahora configuraremos los parametros del virtual host, utilizando el siguiente comando que accedera a la carpeta:

![image](https://user-images.githubusercontent.com/113515330/202186625-712d91a5-d00e-43f6-badf-39adbcfdac80.png)

*Esta es la carpeta donde configuraremos nuesto nombre de servidor*

![image](https://user-images.githubusercontent.com/113515330/202187012-8fdfac7d-3de1-47ba-9d8b-a89ad520324c.png)

Crearemos carpeta de configuración de Virtual Host.

![image](https://user-images.githubusercontent.com/113515330/202187466-97722d2e-0a2d-40f0-bfb4-7e7f573c158f.png)

*Esta es la carpeta donde configuraremos nuesto nombre de servidor*

![image](https://user-images.githubusercontent.com/113515330/202187762-dd3b59dd-b61f-4ddf-a3a8-6d697b198726.png)


Ahora a continuació activaremos las dos paginas de Virtual Host:

![image](https://user-images.githubusercontent.com/113515330/202188203-1fa32ec4-6094-49e1-a721-d41d9e653388.png)

![image](https://user-images.githubusercontent.com/113515330/202188110-796502e3-488b-481f-a1e5-437d4c800bc3.png)

Reinicamos el apache2 para implementar los cambios.

![image](https://user-images.githubusercontent.com/113515330/202188459-e586c75c-49c5-4f6d-87d2-504adb0da7fa.png)

Luego de todo esto comprobamos que si accedemos a nuestras URL's podremos acceder al archivo que hemos creado.

*daw.gimbernat.eug.es*
![image](https://user-images.githubusercontent.com/113515330/202191428-861d9a85-d9fe-47b3-be39-4516f766963c.png)

*rperezma.gimbernat.eug.es*

![image](https://user-images.githubusercontent.com/113515330/202191635-311f903a-ce08-4597-a5fb-70d1b516cf5a.png)

Comenzamos con la edición de html y css de los archivos creados en los directorios.

![image](https://user-images.githubusercontent.com/113515330/202286234-1a347e26-c4e8-49b8-92a7-42d0ece1f971.png)
*el HTML se ve tal que así*

![image](https://user-images.githubusercontent.com/113515330/202286316-a280bb32-4d4c-4201-8403-6d74c6bbd148.png)
*Y esto es lo que se ve a traves del directorio*





