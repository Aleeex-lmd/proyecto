# Diseño e Implementación de una Infraestructura de Despliegue Continuo con GitOps y ArgoCD en Kubernetes (K8s) sobre una Base No Convencional y un Kernel Optimizado de Baja Latencia

## Indice


---


## Introducción

### Introducción al sistema operativo

Primero comenzaremos por lo más básico, el sistema operativo, la base de la mayoría de proyectos y lo que los definen. Para este proyecto estaremos usando **[Ryoku arch](https://ryoku.dev)**, una distribución de Linux la cual usa como base Arch Linux, pero a diferencia de este es mucho más sencillo de instalar, al igual que otras alternativas como Omarchy, las cuales facilitan mucho la instalación, configuración y uso de estos sistemas operativos para la gente que no tiene un conocimiento tan elevado de la informática.

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
