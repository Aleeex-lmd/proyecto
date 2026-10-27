# Diseño e Implementación de una Infraestructura de Despliegue Continuo con GitOps y ArgoCD en Kubernetes (K8s) sobre una Base No Convencional y un Kernel Optimizado de Baja Latencia

## Indice


---


## Introducción

### Introducción al sistema operativo

Primero comenzaremos por lo más básico, el sistema operativo, la base de la mayoría de proyectos y lo que los definen. Para este proyecto estaremos usando **[Ryoku](https://ryoku.dev)**, una distribución de Linux la cual usa como base Arch Linux, pero a diferencia de este es mucho más sencillo de instalar, al igual que otras alternativas como Omarchy, las cuales facilitan mucho la instalación, configuración y uso de estos sistemas operativos para la gente que no tiene un conocimiento tan elevado de la informática.

Las razones que me han hecho elegir esto frente a otras alternativas como pueden llegar a ser Omarchy, EndeavourOS o directamente, un Arch puro con dotfiles, son principalmente su estética brutalista japonesa, sumada a su perfecta sinergia con varias aplicaciones propias que permiten un excelente manejo del sistema. Entre ellas destacan una herramienta propia para cambiar los fondos de pantalla y adaptar el layout completo al fondo y al tema, un reproductor propio que se integra al tema que estemos usando, un agente integrado que permite que la IA ejecute comandos sobre nuestro sistema según lo que le pidamos, un gestor de máquinas virtuales propio y mucho más.

### Introducción al kernel

Ahora que hemos introducido nuestro sistema operativo, toca intrducir el kernel, el cual tambien es muy importante, sobre todo en nuestro proyecto en el cual no queremos solo usarlo sino también demostrar porque es mejor este kernel ultramodificado para tener mejor rendimiento que un kernel convencional.

El kerner que usaremos será el del sistema operativo **[Cachyos](https://cachyos.org/)**, lo que tiene de especial es que es un sistema operativo mayormente dedicado para exprimir al máximo los recursos de cualquier pc que sea decente, esto mayormente suele usarse para gaming pero para este proyecto le daremos otro uso.

Ya que vamos a estar hablando todo el rato de esto, antes de seguir vamos a explicar lo que es un kernel de baja latencia, la latencia es el tiempo de espera entre la orden y su respuesta, por lo que el kernel de baja latencia lo que tiene de novedoso es reduce el scheduler para que cuando llegue una tarea la ejecute de inmediato aunque haya otras en marcha, esto lo explicaremos con más detalle más adelante

### Introducción a kubernetes

Ahora toca el momento de introducir otra herrramienta muy importante en nuestro proyecto como es el caso de kubernete, tambien conocido como k86, kunernetes es la herramienta que se encarga de automatizar tanto el despliegue como la escalabilidad y la gestión de aplicaciones en contenedores.

Kubernetes tiene cosas muy buenas como pueden ser el reinicio de los nodos que fallen sustituyendolos por otros que funcionen bien y reprogramandolos (self reparing), la agrupacion de servidores, ya sean fisicos o virtuales en un solo gurpo organizado, la escalabilidad automatizable y el balanceo de carga asi como el gestor de secretos son una de las muchas cosas que tiene esta herramienta

### Introduccion a GitOps

Gitops una metodologia de trabajo que usa GitHub como fuente central, unas de sus ventajas son:

1. Historial y auditoría total: Si el sistema falla, puedes revisar el historial de Git para ver qué cambio causó el problema.
2. Recuperación ante desastres (Rollback inmediato): Si una actualización rompe el sistema, simplemente regresas a la versión anterior en Git (commit anterior) y la herramienta GitOps reparará el clúster en segundos.
3. Mayor seguridad: Los desarrolladores no necesitan accesos directos ni contraseñas de los servidores de producción; solo necesitan permiso para proponer cambios en Git.


### Introducción a ArgoCD

Y llegamos a la ultima pieza de nuestro proyecto, argocd, la cual se encarga de unir Github y Kubernetes haciendo una sinergia perfecta.

Su trabajo consiste en leer la estructura que tiene descrita en nuestro repositorio GitHub y compararlo con lo que realmente esta bcorriendo en kubernetes, así mismo realizando cambios si fuese necesario. Si un desarrollador sube una nueva versión a Github, ArgoCD lo detecta inmediatamente y actualiza el cluster. Y si alguien por error intenta modificar algo a mano en kubernetes argocd lo corrige al instante.

## Instalacion del sistema operativo

Para instalar ryoku tenemos varias bases entre las cuales se encuentran: arch y cachyos comos bases estables y en version aun experimentales podemos encontrar void linux, fedora y nixos. Nosotros usaremos cachyos como base ya que haremos uso del kernel de baja latencia que nos proporciona cachyos para buestro proyecto asi como algunas de sus mejoras frete a arch linux.

Lo primero que haremos sera intalar ryoku desde su pagina web seleccionando la opcion de cachyos **[Ryoku](https://ryoku.dev)**

![alt text](img/0.png)
![alt text](img/1.png)
![alt text](img/2.png)
![alt text](img/3.png)
![alt text](img/4.png)
![alt text](img/5.png)
![alt text](img/6.png)
![alt text](img/7.png)
![alt text](img/8.png)
![alt text](img/9.png)
![alt text](img/10.png)
![alt text](img/11.png)
![alt text](img/12.png)
![alt text](img/13.png)
![alt text](img/14.png)
![alt text](img/15.png)
![alt text](img/16.png)
![alt text](img/17.png)
![alt text](img/18.png)
![alt text](img/19.png)
![alt text](img/20.png)
![alt text](img/21.png)
![alt text](img/22.png)
![alt text](img/23.png)
![alt text](img/24.png)
![alt text](img/25.png)
![alt text](img/26.png)
![alt text](img/27.png)
![alt text](img/28.png)
![alt text](img/29.png)
![alt text](img/30.png)
![alt text](img/31.png)
![alt text](img/32.png)
![alt text](img/33.png)
![alt text](img/34.png)