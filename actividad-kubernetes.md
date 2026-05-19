# Actividad Kubernetes: Despliegue de `store-app` en Minikube


**Descripción:** Inspecciono el estado general del clúster con `kubectl get all` para ver pods, deployments y servicios.
Esto muestra qué recursos están desplegados y si hay pods con problemas o servicios en espera.

![alt text](img/image-1.png)

**Descripción:** Compruebo el endpoint de `store-app` con `kubectl get endpoints store-app` para ver IP y puerto.
Esto confirma si el servicio está enlazado correctamente a sus pods y es accesible internamente.


![alt text](img/image-2.png)

**Descripción:** Observo la advertencia deprecada `Endpoints` en Kubernetes y verifico el estado del servicio.
Sirve para entender si la versión de `kubectl` o del clúster necesita actualización o ajuste.


![alt text](img/image-22.png)

**Descripción:** Elimino el clúster `multinodo` usando `minikube delete -p multinodo` para liberar recursos.
Esto borra los nodos, contenedores y configuración del clúster anterior antes de crear uno nuevo.


![alt text](img/image-23.png)

**Descripción:** Inicio Minikube con el perfil `store-app` y construyo la imagen Docker para la app.
Aquí se prepara el entorno y se carga la imagen en Minikube para poder desplegarla en el cluster.


![alt text](img/image-24.png)

**Descripción:** Aplico el manifiesto `store-app-k8s.yaml` con `kubectl apply -f` para crear recursos Kubernetes.
Esto crea secret, configmap, PVC, deployments y servicios necesarios para la app y la base de datos.


![alt text](img/image-25.png)

**Descripción:** Expongo el servicio `store-app` con `minikube service store-app` para obtener la URL de acceso.
Así puedo abrir la aplicación en el navegador usando la IP y el puerto que Minikube asigna.


![alt text](img/image-26.png)

**Descripción:** Verifico los pods con `kubectl get pods` y reviso qué contenedores están en error o arrancando.
Esto me permite detectar pods con estado `CrashLoopBackOff` o reinicios antes de seguir depurando.


![alt text](img/image-3.png)

**Descripción:** Muestro cómo navego a la ruta correcta del proyecto antes de lanzar Minikube.
Esto es útil para tener claro el directorio de trabajo donde están los archivos de Kubernetes.


![alt text](img/image-4.png)

**Descripción:** Inicio Minikube con Docker y reviso mensajes de compatibilidad con `kubectl` y Kubernetes.
Fíjate en el aviso sobre la versión de `kubectl` frente a la versión de Kubernetes del cluster.


![alt text](img/image-5.png)

**Descripción:** Compruebo otra vez el estado de los pods después de iniciar el cluster y aplicar los manifiestos.
Aquí se ve si los pods del despliegue ya están `Running` o si todavía hay fallos que resolver.


![alt text](img/image-6.png)

**Descripción:** Reviso los logs detallados de arranque de Minikube y del proceso de creación del cluster.
Sirve para detectar errores en la inicialización del nodo o problemas con la imagen Docker.



![alt text](img/image-7.png)

**Descripción:** Registro el comando `minikube start` en la ruta `Actividad-kubernetes/peladonerd/kubernetes/35`.
Muestra el proceso de arranque desde esa carpeta y la configuración del perfil del cluster.


![alt text](img/image-8.png)

**Descripción:** Veo los mensajes de configuración del clúster, como detección de driver Docker y addons habilitados.
Esto confirma que Minikube está validando correctamente los componentes del cluster antes de iniciar.


![alt text](img/image-9.png)

**Descripción:** Ejecuto `kubectl get pods` para ver el estado final de los pods del despliegue `store-app`.
Se observa un pod con estado de error y reinicios, lo que indica que hay que depurar el contenedor.


![alt text](img/image-10.png)

**Descripción:** Reviso el estado completo del clúster y la disponibilidad de los pods tras el despliegue.
Esta última captura muestra si el despliegue y los servicios quedaron correctamente creados.