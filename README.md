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
*Así deberia verse*




