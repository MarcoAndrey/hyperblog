# Curso Profesional de Git y GitHub

- **¿Por qué usar un sistema de control de versiones como Git?**
    
    Un [sistema de control de versiones como Git](https://platzi.com/clases/1557-git-github/20215-que-es-git/) nos ayuda a guardar el historial de cambios y crecimiento de los archivos de nuestro proyecto.
    
    En realidad, los cambios y diferencias entre las versiones de nuestros proyectos pueden tener similitudes, algunas veces los cambios pueden ser solo una palabra o una parte específica de un archivo específico. Git está optimizado para guardar todos estos cambios de forma atómica e incremental, o sea, aplicando cambios sobre los últimos cambios, estos sobre los cambios anteriores y así hasta el inicio de nuestro proyecto.
    
    - El comando para iniciar nuestro repositorio, o sea, indicarle a Git que queremos usar su sistema de control de versiones en nuestro proyecto, es `git init`.
    - El comando para que nuestro repositorio sepa de la existencia de un archivo o sus últimos cambios es `git add`. Este comando no almacena las actualizaciones de forma definitiva, únicamente las guarda en algo que conocemos como “Staging Area” (área de montaje o ensayo).
    - El comando para almacenar definitivamente todos los cambios que por ahora viven en el staging area es `git commit`. También podemos guardar un mensaje para recordar muy bien qué cambios hicimos en este commit con el argumento `m "Mensaje del commit"`
    - `git status`  El comando nos sirve para ver el estatus de los cambios realizados,
    - El comando  `git show`  es muy importante por que nos muestra todos los cambios históricos hechos, incluyendo las lineas de código, las lineas de texto o las lineas de cualquier archivo que se hayan añadido o cambiado, cuando se ha hecho cambios y quien los hizo
    - El comando nos sirve para ver la historia entera del proyecto o un archivo `git log archivo.txt` y el nombre del archivo
    - Por último, si queremos mandar nuestros commits a un servidor remoto, un lugar donde todos podamos conectar nuestros proyectos, usamos el comando `git push`.
    
    ## Comandos básicos de git
    
    - **git init:** inicializa un repositorio de GIT en la carpeta donde se ejecute el comando.
    - **git add**: añade los archivos especificados al área de preparación (staging).
    - **git commit -m “commit description”**: confirma los archivos que se encuentran en el área de preparación y los agrega al repositorio.
    - **git commit -am “commit description”**: añade al staging area y hace un commit mediante un solo comando. (No funciona con archivos nuevos)
    - git status: ofrece una descripción del estado de los archivos (untracked, ready to commit, nothing to commit).
    - git rm (. -r, filename) (–cached): remueve los archivos del index.
    - git config --global user.email [tu@email.com](mailto:tu@email.com): configura un email.
    - git config --global [user.name](http://user.name/) : configura un nombre.
    - git config --list: lista las configuraciones.
    
    ## Analizar cambios en los archivos de un proyecto Git
    
    - git log: lista de manera descendente los commits realizados.
    - git log --stat: además de listar los commits, muestra la cantidad de bytes añadidos y eliminados en cada uno de los archivos modificados.
    - git log --all --graph --decorate --oneline: muestra de manera comprimida toda la historia del repositorio de manera gráfica y embellecida.
    - git show filename: permite ver la historia de los cambios en un archivo.
    - git diff : compara diferencias entre en cambios confirmados.
    
    ## Volver en el tiempo con branches y checkout
    
    - git reset --soft/hard: regresa al commit especificado, eliminando todos los cambios que se hicieron después de ese commit.
    - git checkout : permite regresar al estado en el cual se realizó un commit o branch especificado, pero no elimina lo que está en el staging area.
    - git checkout – : deshacer cambios en un archivo en estado modified (que ni fue agregado a staging)
    
    ## git rm y git reset
    
    ### **git rm**:
    
    Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.
    
    git rm no puede usarse por sí solo, así nomás. Se debe utilizar uno de los flags para indicar a Git cómo eliminar los archivos que ya no se necesitan en la última versión del proyecto:
    
    - git rm --cached : elimina los archivos del área de Staging y del próximo commit, pero los mantiene en nuestro disco duro.
    - git rm --force : elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos aplicar comandos más avanzados).
    
    ### **git reset**
    
    Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir.
    
    - git reset --soft: Vuelve el branch al estado del commit especificado, manteniendo los archivos en el directorio de trabajo y lo que haya en staging considerando todo como nuevos cambios. Así podemos aplicar las últimas actualizaciones a un nuevo commit.
    - git reset --hard: Borra absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
    - git reset HEAD: No borra los archivos ni sus modificaciones, solo los saca del área de staging, de forma que los últimos cambios de estos archivos no se envíen al último commit. Si se cambia de opinión se los puede incluir nuevamente con git add.
    
    ## Ramas o Branches en git
    
    Al crear una nueva rama se copia el último commit en esta nueva rama. Todos los cambios hechos en esta rama no se reflejarán en la rama master hasta que hagamos un merge.
    
    - git branch : crea una nueva rama.
    - git checkout : se mueve a la rama especificada.
    - git merge : fusiona la rama actual con la rama especificada y produce un nuevo commit de esta fusión.
    - git branch: lista las ramas generadas.
- **¿Qué es Git?**
    
    **Git es un sistema de control de versiones distribuido** que te permite registrar los cambios que haces en tus archivos y volver a versiones anteriores si algo sale mal. Fue diseñado por Linus Torvalds para garantizar la eficiencia y confiabilidad del mantenimiento de versiones de aplicaciones que tienen un gran número de archivos de código fuente.
    
    - Git está optimizado para guardar cambios de forma incremental.
    - Permite contar con un historial, regresar a una versión anterior y agregar funcionalidades.
    - Lleva un registro de los cambios que otras personas realicen en los archivos.
    
    Git fue diseñado para operar en un entorno Linux. Actualmente, es multiplataforma, es decir, es compatible con Linux, MacOS y Windows. En la máquina local se encuentra Git, se utiliza bajo la terminal o línea de comandos y tiene comandos como *merge, pull, add, commit* y *rebase*, entre otros.
    
    ## Para qué proyectos sirve Git
    
    Con Git se obtiene una mayor eficiencia usando archivos de texto plano, ya que con archivos binarios no puede guardar solo los cambios, sino que debe volver a grabar el archivo completo ante cada modificación, por mínima que sea, lo que hace que incremente demasiado el tamaño del repositorio.
    
    “Guardar archivos binarios en el repositorio de Git no es una buena práctica, únicamente deberían guardarse archivos pequeños (como logos) que no sufran casi modificaciones durante la vida del proyecto. Los binarios deben guardarse en un CDN”.
    
    ## Características de Git
    
    Git te ayuda a trabajar de manera más organizada y colaborativa en proyectos de desarrollo de software. Estas son algunas de sus principales características:
    
    ### Control de versiones
    
    Git almacena la información como un conjunto de archivos. Te permite llevar un registro de los cambios que haces en tus archivos, lo que significa que siempre puedes volver a versiones anteriores si algo sale mal.
    
    ### Ramificación
    
    Puedes crear ramas en tu proyecto, lo que te permite trabajar en diferentes características o aspectos del mismo sin afectar el trabajo de los demás.
    
    ### Colaboración
    
    En Git, varias personas pueden trabajar en diferentes aspectos del proyecto al mismo tiempo.
    
    ### Seguridad
    
    No existen cambios, corrupción en archivos o cualquier alteración sin que Git lo sepa. Git cuenta con 3 estados en los que es posible localizar archivos: Staged, Modified y Committed.
    
    ### Flexibilidad
    
    Casi todo en Git es local. Es difícil que se necesiten recursos o información externos, basta con los recursos locales con los que cuenta.
    
    ### Comandos
    
    Git tiene una sintaxis de comandos bastante sencilla y fácil de aprender, lo que lo hace accesible incluso para principiantes en programación.
    
    ## ¿Qué es un sistema de control de versiones?
    
    El SCV o VCS (por sus siglas en inglés) es un sistema que registra los cambios realizados sobre un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas llevar el historial del ciclo de vida de un proyecto, comparar cambios a lo largo del tiempo, ver quién los realizó o revertir el proyecto entero a un estado anterior.
    
    Cualquier tipo de archivo que se encuentre en un ordenador puede ponerse bajo control de versiones.
    
    ![https://static.platzi.com/media/user_upload/Que_es_Git-8f5b6780-47b4-4ff7-9a8a-6fdec5a0f1af.jpg](https://static.platzi.com/media/user_upload/Que_es_Git-8f5b6780-47b4-4ff7-9a8a-6fdec5a0f1af.jpg)
    
    ## ¿En qué se diferencia de Github?
    
    Github es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. Se emplea principalmente para la creación de código fuente de programas de computadora.
    
    Puede considerarse a Github como la red social de código para los programadores y en muchos casos es visto como un *curriculum vitae*, pues aquí se guarda el portafolio de proyectos de programación.
    
    ## Características de Github
    
    - GitHub permite alojar proyectos en repositorios de forma gratuita y pública, pero tiene una forma de pago para privados.
    - Puedes compartir fácilmente tus proyectos.
    - Permite colaborar para mejorar los proyectos de otros y a otros mejorar o aportar a los tuyos.
    - Ayuda a reducir significativamente los errores humanos, a tener un mejor mantenimiento de distintos entornos y a detectar fallos de una forma más rápida y eficiente.
    - Es la opción perfecta para poder trabajar en equipo en un mismo proyecto.
    - Ofrece todas las ventajas del sistema de control de versiones Git, pero también tiene otras herramientas que ayudan a tener un mejor control de los proyectos.
- **Tipos de archivos y sus diferencias**
    - **Archivos de Texto (.txt)**: Texto plano normal y sin nada especial. Lo vemos igual sin importar dónde lo abramos, ya sea con el bloc de notas o con editores de texto avanzados.
    - **Archivos RTF (.rtf)**: Podemos guardar texto con diferentes tamaños, estilos y colores. Pero si lo abrimos desde un editor de código, vamos a ver que es mucho más complejo que solo el texto plano. Esto es porque debe guardar todos los estilos del texto y, para esto, usa un código especial un poco difícil de entender y muy diferente a los textos con estilos especiales al que estamos acostumbrados.
    - **Archivos de Word (.docx)**: Podemos guardar imágenes y texto con diferentes tamaños, estilos o colores. Al abrirlo desde un editor de código podemos ver que es código binario, muy difícil de entender y muy diferente al texto al que estamos acostumbrados. Esto es porque Word está optimizado para entender este código especial y representarlo gráficamente.
    
    Recuerda que debes habilitar la opción de ver la extensión de los archivos, de lo contrario, solo podrás ver su nombre. La forma de hacerlo en Windows es `Vista > Mostrar u ocultar > Extensiones de nombre de archivo`.
    
    ## Conceptos importantes de Git
    
    - Bug: Error en el código
    - Repository: Donde se almacena todo el proyecto, el cual puede vivir tanto en local como en remoto. El repositorio guarda un historial de versiones y, más importante, de la relación de cada versión con la anterior para que pueda hacerse el árbol de versiones con las diferentes ramas.
    - Fork: Si en algún momento queremos contribuir al proyecto de otra persona, o si queremos utilizar el proyecto de otro como el punto de partida del nuestro. Esto se conoce como “fork”.
    - Clone: Una vez se decide hacer un fork , hasta ese momento sólo existe en GitHub. Para poder trabajar en el proyecto, toca clonar el repositorio elegido al computador personal.
    - Branch: Es una bifurcación del proyecto que se está realizando para anexar una nueva funcionalidad o corregir un bug.
    - Master: Rama donde se almacena la última versión estable del proyecto que se está realizando. La rama master es la que está en producción en cada momento (o casi) y debería estar libre de bugs. Así, si esta rama está en producción, sirve como referente para hacer nuevas funcionalidades y/o arreglar bugs de última hora.
    - Commit: consiste en subir cosas a la versión local del repositorio. De esta manera se puede trabajar en la rama de forma local sin tener que modificar ninguna versión en remoto ni tener que tener la última versión remota, cosa muy útil en grandes desarrollos trabajados por varias personas.
    - Push: Consiste en enviar todo lo que se ha confirmado con un commit al repositorio remoto. Aquí es donde se une nuestro trabajo con el de los demás.
    - Checkout: Acción de descargarse una rama del repositorio GIT local (sí, GIT tiene su propio repositorio en local para poder ir haciendo commits) o remoto.
    - Fetch: Actualiza el repositorio local bajando datos del repositorio remoto al repositorio local sin actualizarlo, es decir, se guarda una copia del repositorio remoto en el local.
    - Merge: La acción de merge es la continuación natural del fetch. El merge permite unir la copia del repositorio remoto con tu repositorio local, mezclando los diferentes códigos.
    - Pull: Consiste en la unión del fetch y del merge, esto es, recoge la información del repositorio remoto y luego mezcla el trabajo en local con esta.
    - Diff: Se utiliza para mostrar los cambios entre dos versiones del mismo archivo.
- **Introducción a la terminal y línea de comandos**
    
    La línea de comandos nos permite interactuar con nuestro computador sin necesidad de utilizar una interfaz gráfica. Sin embargo, los computadores emplean distintos sistemas de archivos y manejan diferentes comandos, dependiendo del sistema operativo que utilicen.
    
    > Aprende más sobre: qué es un comando.
    > 
    
    ## **Diferencias** entre la estructura de archivos de Windows, Mac o Linux
    
    - La ruta principal en Windows es `C:\`, en UNIX es solo `/`.
    - Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.
    
    Recuerda que GitBash usa la ruta `/c` para dirigirse a `C:\` (o `/d` para dirigirse a `D:\`) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es `/c/Users/Nombre de tu usuario`
    
    ## **Comandos básicos en la terminal**
    
    - **pwd**: Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
    - **mkdir**: Nos permite crear carpetas (por ejemplo, `mkdir Carpeta-Importante`).
    - **touch**: Nos permite crear archivos (por ejemplo, `touch archivo.txt`).
    - **rm**: Nos permite borrar un archivo o carpeta (por ejemplo, `rm archivo.txt`). Mucho cuidado con este comando, puedes borrar todo tu disco duro.
    - **cat**: Ver el contenido de un archivo (por ejemplo, `cat nombre-archivo.txt`).
    - **ls**: Nos permite cambiar ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser `-` + el nombre del argumento o `` + una sola letra o shortcut por cada argumento).`ls -a`: Mostrar todos los archivos, incluso los ocultos.`ls -l`: Ver todos los archivos como una lista.
    - **cd**: Nos permite navegar entre carpetas.`cd /`: Ir a la ruta principal:`cd` o `cd ~`: Ir a la ruta de tu usuario`cd carpeta/subcarpeta`: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.`cd ..` (`cd` + dos puntos): Regresar una carpeta hacia atrás.Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar `cd .` (`cd` + un punto).
    - **history**: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
    - **! + número**: Ejecutar algún comando con el número que nos muestra el comando `history` (por ejemplo, `!72`).
    - **clear**: Para limpiar la terminal. También podemos usar los atajos de teclado `Ctrl + L` o `Command + L`.
    
    Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla `Tab` para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla `Arriba` puedes ver el último comando que ejecutamos.
    
    Recuerda que podemos descubrir todos los argumentos de un comando con el argumento `--help` (por ejemplo, `cat --help`).
    
- **Comandos de la terminal de MAC**
    
    Empezaremos con los siguientes comandos, serán muy sencillos, eso sí, recuerda que hay que practicar!!
    
    Comandos vim [https://youtu.be/TmNa4y-K5Z8?si=FtEKTb79BBLN7fxK](https://youtu.be/TmNa4y-K5Z8?si=FtEKTb79BBLN7fxK)
    
    [VIM - Tutorial para principiantes - El MEJOR editor de texto](https://youtu.be/TmNa4y-K5Z8?si=FtEKTb79BBLN7fxK)
    
    # man
    
    El primer comando que tenemos que aprender es man, dicho comando nos muestra la ayuda de otros comandos.
    
    ```
    man comando
    ```
    
    Ejemplo, mostrar ayuda del comando pwd:
    
    ```
    man pwd
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/man-pwd.png](https://labsmac.es/wp-content/uploads/2022/07/man-pwd.png)
    
    Guardar una copia en pdf de la ayuda del comando:
    
    ```
    man -t ls | open -fa preview.app
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/pdf-terminal.png](https://labsmac.es/wp-content/uploads/2022/07/pdf-terminal.png)
    
    # pwd
    
    **p**rint **w**orking **d**irectory, este comando nos muestra el directorio actual en el que estamos situados:
    
    ```
    pwd
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/pwd.png](https://labsmac.es/wp-content/uploads/2022/07/pwd.png)
    
    En este caso pwd, nos indica que estamos situados en la carpeta **labsmac**, y labsmac cuelga de la carpeta **/Users**
    
    # clear
    
    Este comando sirve básicamente para limpiar la pantalla de la terminal y no ver todo lo anterior que hemos ido ejecutando.
    
    ```
    clear
    ```
    
    # mkdir
    
    Este comando sirve para crear carpetas. Si el nombre de la carpeta que queremos crear tiene espacios, tenemos que usar comillas.
    
    ```
    mkdir "Nombre de la carpeta"
    ```
    
    Crear una carpeta
    
    Por ejemplo, crear una carpeta llamada labsmac.es:
    
    ```
    mkdir labsmac.es
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/mkdir-nueva-carpeta.png](https://labsmac.es/wp-content/uploads/2022/07/mkdir-nueva-carpeta.png)
    
    Crear varias carpetas y subcarpetas de forma instantánea
    
    Si añadimos la opción -p, podemos crear varias carpetas y subcarpetas de un instante.
    
    ```
    mkdir -p Bisabuelo/Abuelo/Padre/Hijo
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/mkdir-crear-carpetas-subcarpetas.png](https://labsmac.es/wp-content/uploads/2022/07/mkdir-crear-carpetas-subcarpetas.png)
    
    # cd
    
    cd que viene de **c**hange **d**irectory, es el comando que nos ayuda a movernos entre los directorios
    
    Antes de emprender a moverte entre las carpetas, debes saber que en la terminal:
    
    - Un punto ( . ) significa la carpeta actual.
    - Dos puntos ( .. ) significa la carpeta superior o carpeta padre. Esto nos sirve para retroceder hacia atrás dentro de las carpetas.
    
    Sabiendo esto al ejecutar el comando cd . nos quedamos en el mismo sitio:
    
    ```
    cd .
    ```
    
    En cambio si ejecutamos cd .. retrocederemos a la carpeta padre o superior:
    
    ```
    cd ..
    ```
    
    Podemos retroceder dos o más carpetas a la vez, de la siguiente manera:
    
    ```
    cd ../../  < Retrocedemos dos carpetas y cd ../../../  < Retrocederemos tres carpetas y así sucesivamente.
    ```
    
    Ayúdate con el comando pwd para saber donde estas y se te haga más fácil entender esto..
    
    Para seguir con el ejemplo del mdkir, tenemos la siguiente estructura de carpetas:
    
    ```
    Escritorio/Bisabuelo/Abuelo/Padre/Hijo
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/estructura-carpetas.png](https://labsmac.es/wp-content/uploads/2022/07/estructura-carpetas.png)
    
    Actualmente estamos dentro del Escritorio, observa como me voy moviendo y retrocediendo.
    
    ![https://labsmac.es/wp-content/uploads/2022/07/movimiento-carpetas-1024x467.png](https://labsmac.es/wp-content/uploads/2022/07/movimiento-carpetas-1024x467.png)
    
    # ls
    
    **list**, sirve para listar el contenido (archivos y carpetas) de un directorio/carpeta. Recomiendo usarlo con la opción -l para mostrarlo en forma de listado e información adicional:
    
    ```
    ls -l
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/ls-l.png](https://labsmac.es/wp-content/uploads/2022/07/ls-l.png)
    
    # cp
    
    Comando que sirve para **copiar** archivos y carpetas. Estructura del comando:
    
    ```
    cp origen destino
    ```
    
    Copiar fichero
    
    En este ejemplo, copiamos el documento.pdf dentro de la carpeta Subdirectorio a su vez cambiamos el nombre del fichero a archivo.pdf
    
    ```
    cp documento.pdf Subdirectorio/archivo.pdf
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/copiado-documentoPDF.png](https://labsmac.es/wp-content/uploads/2022/07/copiado-documentoPDF.png)
    
    Copiar carpetas y archivos
    
    En este otro ejemplo copiamos la carpeta Subdirectorio y todo su contenido en la misma ubicación pero con otro nombre, CopiaSubdirectorio
    
    ```
    cp -R Subdirectorio CopiaSubdirectorio
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/copiar-carpeta-entera.png](https://labsmac.es/wp-content/uploads/2022/07/copiar-carpeta-entera.png)
    
    # mv
    
    Comando que se utiliza para **mover carpetas y archivos**, también sirve para cambiar sus nombres o **renombrarlas**. Estructura del comando:
    
    ```
    mv origen destino
    ```
    
    En este ejemplo, movemos la carpeta MiCarpeta dentro de la carpeta DestinoFinal
    
    ```
    mv MiCarpeta DestinoFinal/
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/mover-carpeta.png](https://labsmac.es/wp-content/uploads/2022/07/mover-carpeta.png)
    
    # rm
    
    Comando para **borrar archivos y carpetas**, por defecto rm solo borrar archivos, pero si le añadimos la opción -r, borrará también carpetas y subcarpetas.
    
    **CUIDADO:** Lo que eliminas a través de la terminal no se va a la papelera, así que mucho cuidado!!!
    
    Eliminar fichero
    
    Para borrar un fichero:
    
    ```
    rm fichero_a_borrar
    ```
    
    Borrar carpetas y todo su contenido
    
    Para borrar una carpeta y todo su contenido (esto incluye archivos y subcarpetas), tenemos que añadir la opción -r:
    
    ```
    rm -r carpeta_a_borrar
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/eliminar-carpetas.png](https://labsmac.es/wp-content/uploads/2022/07/eliminar-carpetas.png)
    
    # history
    
    Muestra el histórico de los comandos, por defecto, si solo escribimos el comando nos arroja los últimos 16 comandos que hemos ejecutado:
    
    ```
    history
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/history.png](https://labsmac.es/wp-content/uploads/2022/07/history.png)
    
    Si ejecutamos history + número, nos muestra el histórico desde ese número hasta el último:
    
    ```
    history 280
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/history-280.png](https://labsmac.es/wp-content/uploads/2022/07/history-280.png)
    
    # open
    
    El comando open sirve para **abrir carpetas, archivos y aplicaciones**. Incluso podemos abrir **múltiples instancias de una aplicación.**
    
    ```
    open carpeta_o_archivo_aplicación
    ```
    
    ![https://labsmac.es/wp-content/uploads/2022/07/open-carpeta.png](https://labsmac.es/wp-content/uploads/2022/07/open-carpeta.png)
    
- **Crea un repositorio de Git y haz tu primer commit**
    
    Le indicaremos a [Git](https://platzi.com/clases/1557-git-github/20215-que-es-git/) que queremos crear un nuevo repositorio para utilizar su sistema de control de versiones. Solo debemos posicionarnos en la carpeta raíz de nuestro proyecto y ejecutar el comando:
    
    ```
    git init
    
    ```
    
    Recuerda que al ejecutar este comando (y de aquí en adelante) vamos a tener una nueva carpeta oculta llamada `.git` con toda la base de datos con cambios atómicos en nuestro proyecto.
    
    Recuerda que Git está optimizado para trabajar en equipo, por lo tanto, debemos darle un poco de información sobre nosotros. No debemos hacerlo todas las veces que ejecutamos un comando, basta con ejecutar solo una sola vez los siguientes comandos con tu información:
    
    ```
    git config --global user.email "tu@email.com"
    git config --global user.name "Tu Nombre"
    
    ```
    
    Existen muchas otras configuraciones de Git que puedes encontrar ejecutando el comando `git config --list` (o solo `git config` para ver una explicación más detallada).
    
    Si quieres ver los archivos ocultos de una carpeta puedes habilitar la opción de `Vista > Mostrar u ocultar > Elementos ocultos` (en Windows) o ejecutar el comando `ls -a`.
    
    ## Comandos para iniciar tu repositorio con Git
    
    - git init: para inicializar el repositorio git y el staged
    - git add nombre_del_archivo.txt: enviar el archivo al staged
    - git status: ver el estado, si se requiere agregar al starget o si se requiere commit
    - git conf: para ver las posibles configuraciones
    - git conf --list: para ver la lista de configuraciones hechas
    - git conf --list --show-origin: para mostrar las configuraciones y sus rutas
    - git rm --cached nombre_del_archivo.txt: para eliminar el archivo del staged(ram)
    - git rm nombre_del_archivo.txt: para eliminar del repositorio
    
    Si por algún motivo te equivocaste en el nombre o email que configuraste al principio, lo puedes modificar de la siguiente manera:
    
    `git config --global --replace-all user.name “Aquí va tu nombre modificado”`
    
    O si lo deseas eliminar y añadir uno nuevo
    
    `git config --global --unset-all user.name :Elimina el nombre del usuario`
    
    `git config --global --add user.name “Aquí va tu nombre”`
    
- **Analizar cambios en los archivos de tu proyecto con Git**
    
    El comando **`git show`** nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuándo se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser más detallados.
    
    Si queremos ver la diferencia entre una versión y otra, no necesariamente todos los cambios desde la creación del archivo, podemos usar el comando **`git diff commitA commitB`**.
    
    Recuerda que puedes obtener el ID de tus commits con el comando **`git log`**.
    
    ## Comandos para analizar cambios en GIT
    
    - **git init**: inicializar el repositorio
    - **git add nombre_de_archivo.extensión**: agregar el archivo al repositorio
    - **git commit -m “Mensaje”**: Agregamos los cambios para el repositorio
    - **git add**: Agregar los cambios de la carpeta en la que nos encontramos agregar todo
    - **git status**: visualizar cambios
    - **git log nombre_de_archivos.extensión**: histórico de cambios con detalles
    - **git push**: envía a otro repositorio remoto lo que estamos haciendo
    - **git pull**: traer repositorio remoto
    - **ls**: listado de carpetas en donde me encuentro. Es decir, como emplear dir en windows.
    - **pwd**: ubicación actual
    - **mkdir**: make directory nueva carpeta
    - **touch archivo.extensión**: crear archivo vacío
    - **cat archivo.extensión**: muestra el contenido del archivo
    - **history**: historial de comandos utilizados durante esa sesión
    - **rm archivo.extensión**: Eliminación de archivo
    - **comando --help**: ayuda sobre el comando
    - **git checkout**: traer cambios realizados
    - **git rm --cached archivo.extensión**: se utiliza para devolver el archivo que se tiene en ram. Cuando escribimos `git add`, lo devuelve a estado natural mientras está en *staging*.
    - **git config --list**: muestra la lista de configuración de git
    - **git config --list --show-origin**: rutas de acceso a la configuración de git
    - **git log archivo.extensión**: muestra la historia del archivo
- **¿Qué es el staging?**
    
    El staging es el lugar donde se guardan temporalmente los cambios, para luego ser llevados definitivamente al repositorio. El repositorio es el lugar donde se guardan todos los registros de los cambios realizados a los archivos.
    
    Para iniciar un repositorio, o sea, activar el sistema de control de versiones de [Git](https://platzi.com/clases/1557-git-github/20215-que-es-git/) en tu proyecto, solo debes ejecutar el comando `git init`.
    
    ## ¿Qué es el área de staging?
    
    El área de staging se puede ver como un limbo donde nuestros archivos están por ser enviados al repositorio o ser regresados a la carpeta del proyecto.
    
    ## ¿Qué es git init?
    
    `git init`es el comando que activa git en nuestro proyecto creando un espacio en memoria RAM llamado staging y una carpeta .git.
    
    Este comando se encargará de dos cosas: primero, crear una carpeta `.git`, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; segundo, crear un área que conocemos como **staging**, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).
    
    ![https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202022-08-12%20a%20la%28s%29%205.16.50%20p.m.-a7159754-9fcd-4a76-83fa-095ee65bda01.jpg](https://static.platzi.com/media/user_upload/Captura%20de%20Pantalla%202022-08-12%20a%20la%28s%29%205.16.50%20p.m.-a7159754-9fcd-4a76-83fa-095ee65bda01.jpg)
    
    ## Cómo funciona el staging y el repositorio: ciclo básico de trabajo en git:
    
    El flujo de trabajo básico en git es algo así:
    
    1. Modificas una serie de archivos en tu directorio de trabajo.
    2. Preparas los archivos, añadiéndolos a tu área de preparación (staging).
    3. Confirmas los cambios (commit), lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de git.
    
    Veamos a detalle las 3 secciones principales que tiene un proyecto en git.
    
    ### Working directory
    
    El *working directory* es una copia de una versión del proyecto. Estos archivos se sacan de la base de datos comprimida en el directorio de git y se colocan en el disco para que los puedas usar o modificar.
    
    ### Staging area
    
    Es un área que almacena información acerca de lo que va a ir en tu próxima confirmación. A veces se le denomina índice (*index*).
    
    ### .git directory (repository)
    
    En el *repository* se almacenan los metadatos y la base de datos de los objetos para tu proyecto. Es la parte más importante de git (carpeta .git) y es lo que se copia cuando clonas un repositorio desde otra computadora.
    
    ![https://static.platzi.com/media/user_upload/estados-git-0acb84f7-5080-4098-99d9-59012a3b8e86-e5b46dbb-9bab-4d7c-aa74-c055ffcde639.jpg](https://static.platzi.com/media/user_upload/estados-git-0acb84f7-5080-4098-99d9-59012a3b8e86-e5b46dbb-9bab-4d7c-aa74-c055ffcde639.jpg)
    
    ## **Ciclo de vida o estados de los archivos en git**
    
    Cuando trabajamos con git, nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):
    
    ### **Archivos tracked**
    
    Son los archivos que viven dentro de git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos `git add` y `git commit`.
    
    ### **Archivos staged**
    
    Son archivos en staging. Viven dentro de git y hay registro de ellos porque han sido afectados por el comando `git add`, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando `git commit`.
    
    > Git stash: guarda cambios temporalmente
    > 
    
    ### **Archivos unstaged**
    
    Entiéndelos como archivos *“tracked* pero *unstaged”*. Son archivos que viven dentro de git pero no han sido afectados por el comando `git add` ni mucho menos por `git commit`. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.
    
    ### **Archivos untracked**
    
    Son archivos que NO viven dentro de git, solo en el disco duro. Nunca han sido afectados por `git add`, así que git no tiene registros de su existencia.
    
    Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de staging (con el comando `git add`), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de staging.
    
    ## **Comandos para mover archivos entre los estados de Git**
    
    Estos son los comandos más importantes que debes conocer:
    
    ### Git status
    
    **`git status`** nos permite ver el estado de todos nuestros archivos y carpetas.
    
    ### Git add
    
    **`git add`** nos ayuda a mover archivos del untracked o unstaged al estado staged. Podemos usar `git nombre-del-archivo-o-carpeta` para añadir archivos y carpetas individuales o `git add -A` para mover todos los archivos de nuestro proyecto (tanto untrackeds como unstageds).
    
    ### G**it reset HEAD**
    
    Nos ayuda a sacar archivos del estado staged para devolverlos a su estado anterior. Si los archivos venían de unstaged, vuelven allí. Y lo mismo se venían de untracked.
    
    ### G**it commit**
    
    Nos ayuda a mover archivos de unstaged a tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento `m` para escribirlo (`git commit -m "mensaje"`).
    
    ### G**it rm**
    
    Este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente:
    
    - `git rm --cached`: mueve los archivos que le indiquemos al estado untracked.
    - `git rm --force`: elimina los archivos de git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
- **¿Qué es branch (rama) y cómo funciona un Merge en Git?**
    
    Una **rama o branch** es una versión del código del proyecto sobre el que estás trabajando. Estas ramas ayudan a mantener el orden en el control de versiones y manipular el código de forma segura.
    
    En otras palabras, un branch o rama en [Git](https://platzi.com/clases/1557-git-github/20215-que-es-git/) es una rama que proviene de otra. Imagina un árbol, que tiene una rama gruesa, y otra más fina, en la rama más gruesa tenemos los commits principales y en la rama fina tenemos otros commits que pueden ser de `hotfix`, `devlopment` entre otros.ㅤ
    
    ![https://static.platzi.com/media/user_upload/ramas-branch-en-git-7e72b407-90cc-4b90-8de1-738b155764eb.jpg](https://static.platzi.com/media/user_upload/ramas-branch-en-git-7e72b407-90cc-4b90-8de1-738b155764eb.jpg)
    
    ## Clases de branches o ramas en Git
    
    Estas son las ramas base de un proyecto en Git:
    
    ### 1. Rama main (Master)
    
    Por defecto, el proyecto se crea en una rama llamada Main (anteriormente conocida como Master). Cada vez que añades código y guardas los cambios, estás haciendo un commit, que es añadir el nuevo código a una rama. Esto genera nuevas versiones de esta rama o branch, hasta llegar a la versión actual de la rama Main.
    
    ### 2. Rama development
    
    Cuando decides hacer experimentos, puedes generar ramas experimentales (usualmente llamadas development), que están basadas en alguna rama main, pero sobre las cuales puedes hacer cambios a tu gusto sin necesidad de afectar directamente al código principal.
    
    ### 3. Rama hotfix
    
    En otros casos, si encuentras un bug o error de código en la rama Main (que afecta al proyecto en producción), tendrás que crear una nueva rama (que usualmente se llaman bug fixing o hot fix) para hacer los arreglos necesarios. Cuando los cambios estén listos, los tendrás que fusionar con la rama Main para que los cambios sean aplicados. Para esto, se usa un comando llamado *Merge*, que mezcla los cambios de la rama que originaste a la rama Main.
    
    **Todos los commits se aplican sobre una rama**. Por defecto, siempre empezamos en la rama Main (pero puedes cambiarle el nombre si no te gusta) y generamos nuevas ramas, a partir de esta, para crear flujos de trabajo independientes.
    
    ## Cómo crear un branch o rama en Git
    
    El comando git branch permite crear una rama nueva. Si quieres empezar a trabajar en una nueva función, puedes crear una rama nueva a partir de la rama master con git branch new_branch. Una vez creada, puedes usar git checkout new_branch para cambiar a esa rama.
    
    Recuerda que todas tus versiones salen de la rama principal o Master y de allí puedes tomar una versión específica para crear otra rama de versiones.
    
    ## Cómo hacer merge
    
    Producir una nueva rama se conoce como **Checkout**. Unir dos ramas lo conocemos como **Merge**.
    
    Cuando haces merge de estas ramas con el código principal, su código se fusiona originando una nueva versión de la rama master (o main) que ya tiene todos los cambios que aplicaste en tus experimentos o arreglos de errores.
    
    Podemos generar todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para producir ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.
    
    > Descubre qué son los git tags
    > 
    
    Solo ten en cuenta que combinar estas ramas ([hacer “merge”](https://platzi.com/clases/1557-git-github/19939-funcion-de-ramas-con-git-mer-7/)) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos *a mano*.
    
- **Volver en el tiempo en nuestro repositorio utilizando reset y checkout**
    
    El comando **`git checkout`** + `ID del commit` nos permite viajar en el tiempo. Podemos volver a cualquier versión anterior de un archivo específico o incluso del proyecto entero. Esta también es la forma de crear ramas y movernos entre ellas.
    
    También hay una forma de hacerlo un poco más “ruda”: usando el comando `git reset`. En este caso, no solo “volvemos en el tiempo”, sino que borramos los cambios que hicimos después de este commit.
    
    Hay dos formas de usar `git reset`: con el argumento `--hard`, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento `--soft`, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.
    
    > Repasa qué es branch
    > 
    
    ## Cómo usar Git Reset
    
    Para volver a commits previos, borrando los cambios realizados desde ese commit, podemos utilizar:
    
    - git reset --soft [SHA 1]: elimina los cambios hasta el staging area
    - git reset --mixed [SHA 1]: elimina los cambios hasta el working area
    - git reset --hard [SHA 1]: regresa hasta el commit del [SHA-1]Donde el SHA-1 es el identificador del commit
- **Git reset vs. Git rm**
    
    Los comandos git reset y git rm tienen utilidades muy diferentes, pero pueden confundirse fácilmente.
    
    ## Git reset
    
    El comando `git reset` es una herramienta poderosa que te permite deshacer o revertir cambios en tu repositorio de Git. Lo puedes ejecutar de tres maneras diferentes, con las líneas de comando `--soft, --mixed y --hard`.
    
    Pero no como `git checkout` que nos deja ir, mirar, pasear y volver. Con `git reset` volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.
    
    ## Tres árboles en Git
    
    Para entender lo anterior, recordemos que los “tres árboles” de Git son estructuras de datos basadas en nodos y punteros que Git utiliza para hacer seguimiento a un cronograma de ediciones, aunque no sean estructuras en forma de árbol en el sentido tradicional.
    
    La mejor forma de entender estos mecanismos es creando un conjunto de cambios en un repositorio y siguiéndolos a través de los tres árboles. Averigüémoslo.
    
    ```
    $ mkdir git_reset_test
    $ cd git_reset_test/
    $ git init .
    Initialized empty Git repository in /git_reset_test/.git/
    $ touch reset_lifecycle_file
    $ git add reset_lifecycle_file
    $ git commit -m"initial commit"
    [main (root-commit) d386d86] initial commit
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 reset_lifecycle_file
    
    ```
    
    ![https://static.platzi.com/media/user_upload/arboles-git-3092a895-4d68-4d40-b397-033e2d5f0767.jpg](https://static.platzi.com/media/user_upload/arboles-git-3092a895-4d68-4d40-b397-033e2d5f0767.jpg)
    
    ## ¿Cómo funciona Git Reset en tu flujo de trabajo?
    
    `git reset` permite moverte entre diferentes commits para deshacer o rehacer cambios. Git guarda todos lo nuevo del repositorio como commits, que son instantáneas del estado del código en un momento dado y existen variaciones de este comando.
    
    ### Variaciones de Git Reset
    
    - `git reset --soft`: Borra el historial y los registros de Git de commits anteriores, pero guarda los cambios en Staging para aplicar las últimas actualizaciones a un nuevo commit.
    - `git reset --hard`: Deshace todo, absolutamente todo. Toda la información de los commits y del área de staging se elimina del historial.
    - `git reset --mixed`: Borra todo, exactamente todo. Toda la información de los commits y del área de staging se elimina del historial.
    - `git reset HEAD`: El comando `git reset` saca archivos del área de staging sin borrarlos ni realizar otras acciones. Esto impide que los últimos cambios en estos archivos se envíen al último commit. Podemos incluirlos de nuevo en staging con `git add` si cambiamos de opinión.
    
    Ten en cuenta que, si deshaces commits en un repositorio compartido en GitHub, estarás cambiando su historia y esto puede causar problemas de sincronización con otros colaboradores.
    
    ## ¿Qué es git reset HEAD?
    
    `git reset HEAD` es un comando que te permite revertir los cambios que ya habías preparado para subir, y moverlos de vuelta a tu proyecto. Con este comando puedes cancelar los cambios que ya habías agregado, para que puedas revisarlos, modificarlos o deshacerlos antes de confirmarlos con un commit.
    
    ## Git rm
    
    Por otro lado, `git rm` es un comando que nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Para recuperar el archivo eliminado, necesitamos retroceder en la historia del proyecto, recuperar el último commit y obtener la última confirmación antes de la eliminación del archivo.
    
    Es importante tener en cuenta que `git rm` no puede usarse sin evaluarlo antes. Debemos usar uno de los flags siguientes para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto.
    
    ### Variaciones de Git rm
    
    - `git rm --cached`: Elimina archivos del repositorio local y del área de staging, pero los mantiene en el disco duro. Deja de trackear el historial de cambios de estos archivos, por lo que quedan en estado `untracked`.
    - `git rm --force`: Elimina los archivos de Git y del disco duro. Git guarda todo, por lo que podemos recuperar archivos eliminados si es necesario (empleando comandos avanzados).
    
    ¡Al usar git rm lo que haremos será eliminar este archivo completamente de git!
    
    ## ¿Cuál es la diferencia entre git rm y git reset Head?
    
    La diferencia principal entre `git rm` y `git reset HEAD` radica en que `git rm` elimina archivos del repositorio y de la historia del proyecto, mientras que `git reset` saca los cambios del área de preparación y los mueve del espacio de trabajo, sin afectar la historia del repositorio.
    
    ![https://static.platzi.com/media/user_upload/git-reset%20%281%29-77a1294a-fb8b-43d0-aace-a517c1a05c2e.jpg](https://static.platzi.com/media/user_upload/git-reset%20%281%29-77a1294a-fb8b-43d0-aace-a517c1a05c2e.jpg)
    
    Es importante tener en cuenta el efecto que cada comando tiene en el proyecto y usarlos según tus necesidades y objetivos específicos.
    
    ## ¿Cuándo utilizar git reset en lugar de git revert?
    
    Para reescribir la historia del repositorio y eliminar confirmaciones anteriores, se utiliza `git reset`. Para deshacer cambios de confirmaciones anteriores de forma segura sin modificar la historia del repositorio, se emplea `git revert`.
    
    ![https://static.platzi.com/media/user_upload/lifecycle-674998bf-5510-4dc9-9840-edcbe86bf1e8.jpg](https://static.platzi.com/media/user_upload/lifecycle-674998bf-5510-4dc9-9840-edcbe86bf1e8.jpg)
    
    ## Resumen
    
    Para evitar problemas en el trabajo, es valioso entender las implicaciones y riesgos de cada comando y elegir el enfoque adecuado según las necesidades y el flujo de trabajo del proyecto.
    
    Con `git rm` eliminamos un archivo de Git, pero mantenemos su historial de cambios. Si no queremos borrar un archivo, sino dejarlo como está y actualizarlo después, no debemos usar este comando en este commit.
    
    Empleando `git reset HEAD`, movemos los cambios de Staging a Unstaged, pero mantenemos el archivo en el repositorio con los últimos cambios en los que hicimos commit. Así, no perdemos nada relevante.
    
    ## Siguientes pasos
    
    Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.
    
- **Flujo de trabajo básico con un repositorio remoto**
    
    Cuando empiezas a trabajar en un entorno local, el proyecto vive únicamente en tu computadora. Esto significa que no hay forma de que otros miembros del equipo trabajen en él.
    
    Para solucionar esto, utilizamos los **servidores remotos**: un nuevo estado que deben seguir nuestros archivos para conectarse y trabajar con equipos de cualquier parte del mundo.
    
    Estos servidores remotos pueden estar alojados en GitHub, GitLab, BitBucket, entre otros. Lo que van a hacer es guardar el mismo repositorio que tienes en tu computadora y darnos una URL con la que todos podremos acceder a los archivos del proyecto. Así, el equipo podrá descargarlos, hacer cambios y volverlos a enviar al servidor remoto para que otras personas vean los cambios, comparen sus versiones y creen nuevas propuestas para el proyecto.
    
    Esto significa que debes aprender algunos nuevos comandos
    
    ## Comandos para trabajo remoto con GIT
    
    - **`git clone url_del_servidor_remoto`**: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta `.git`.
    - **`git push`**: Luego de hacer `git add` y `git commit` debemos ejecutar este comando para mandar los cambios al servidor remoto.
    - **`git fetch`**: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
    - **`git merge`**: También usamos el comando `git merge` con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
    - **`git pull`**: Básicamente, `git fetch` y `git merge` al mismo tiempo.
    
    Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:
    
    - **git log --oneline**:Te muestra el id commit y el título del commit.
    - **git log --decorate**: Te muestra donde se encuentra el head point en el log.
    - **git log --stat**: Explica el número de líneas que se cambiaron brevemente.
    - **git log -p**: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
    - **git shortlog**: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
    - **git log --graph --oneline --decorate** y
    - **git log --pretty=format:"%cn hizo un commit %h el dia %cd"**: Muestra mensajes personalizados de los commits.
    - **git log -3**: Limitamos el número de commits.
    - **git log --after=“2018-1-2”**
    - **git log --after=“today”** y
    - **git log --after=“2018-1-2” --before=“today”**: Commits para localizar por fechas.
    - **git log --author=“Name Author”**: Commits hechos por autor que cumplan exactamente con el nombre.
    - **git log --grep=“INVIE”**: Busca los commits que cumplan tal cual está escrito entre las comillas.
    - **git log --grep=“INVIE” –i**: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
    - **git log – index.html**: Busca los commits en un archivo en específico.
    - **git log -S “Por contenido”**: Buscar los commits con el contenido dentro del archivo.
    - **git log > log.txt**: guardar los logs en un archivo txt
- **Introducción a las ramas o branches de Git**
    
    Las ramas [(branches)](https://platzi.com/clases/1557-git-github/19947-que-es-un-branch-rama-y-como-funciona-un-merge-en-/) son la forma de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.
    
    La cabecera o `HEAD` representan la rama y el commit de esa rama donde estamos trabajando. Por defecto, esta cabecera aparecerá en el último commit de nuestra rama principal. Pero podemos cambiarlo al crear una rama (`git branch rama`, `git checkout -b rama`) o movernos en el tiempo a cualquier otro commit de cualquier otra rama con los comandos (`git reset id-commit`, `git checkout rama-o-id-commit`).
    
    > Repasa: ¿Qué es Git?
    > 
    
    ## Cómo funcionan las ramas en GIT
    
    Las ramas son la manera de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.
    
    - **git branch -nombre de la rama-**: Con este comando se genera una nueva rama.
    - **git checkout -nombre de la rama-**: Con este comando puedes saltar de una rama a otra.
    - **git checkout -b rama**: Genera una rama y nos mueve a ella automáticamente, Es decir, es la combinación de git branch y git checkout al mismo tiempo.
    - **git reset id-commit**: Nos lleva a cualquier commit no importa la rama, ya que identificamos el id del tag., eliminando el historial de los commit posteriores al tag seleccionado.
    - **git checkout rama-o-id-commit**: Nos lleva a cualquier commit sin borrar los commit posteriores al tag seleccionado.
- **Fusión de ramas con Git merge**
    
    La **fusión en Git** es la forma en que este sistema une un historial bifurcado. El comando `git merge` permite integrar líneas de desarrollo independientes generadas por `git branch` en una sola rama. Con este comando, podemos crear un nuevo *commit* que combina dos ramas o [branches](https://platzi.com/clases/1557-git-github/19947-que-es-un-branch-rama-y-como-funciona-un-merge-en-/): la rama actual y la rama que se indica después del comando.
    
    Estos comandos de fusión del merge afectan solo a la rama actual y no a la rama de destino. Por lo tanto, te recomendamos utilizar `git checkout` para seleccionar la rama actual y `git branch -d` para eliminar la rama de destino obsoleta.
    
    ## Funcionamiento de Git merge
    
    Git merge fusiona secuencias de confirmaciones en un solo historial, generalmente para combinar dos ramas. Busca una confirmación de base común y genera una confirmación de fusión que representa la combinación de las dos ramas hasta el resultado final.
    
    ![https://static.platzi.com/media/user_upload/git-merge-final-7422eace-18ce-4fb2-8eb2-11275fde2f41.jpg](https://static.platzi.com/media/user_upload/git-merge-final-7422eace-18ce-4fb2-8eb2-11275fde2f41.jpg)
    
    ## ¿Cómo unir dos ramas en git?
    
    Ahora bien, para combinar ramas en tu repositorio local, usa git checkout para cambiar a la rama donde deseas fusionar. Por lo general, esta es la rama principal. Luego, emplea git merge y especifica el nombre de la otra rama que deseas traer a esta rama. Ten en cuenta que esto es una combinación de avance rápido.
    
    ## ¿Cómo realizar un merge en git?
    
    Para hacer un merge en Git, primero asegúrate de estar en la rama correcta. Después, usa el comando git merge seguido del nombre de la rama que quieres combinar. Por ejemplo, si quieres crear un nuevo commit en la rama master con los cambios de la rama cabecera, usa este comando:
    
    ```
    git checkout master
    git merge cabecera
    
    ```
    
    Es importante tener en cuenta que en caso de haber conflictos, debes guardar tus cambios antes de hacer `git checkout` para evitar perder tu trabajo. También es recomendable emplear los comandos básicos de GitHub, como `git fetch`, `git push` y `git pull`, para mantener actualizado tu repositorio.
    
    En este ejemplo, vamos a crear un nuevo *commit* en la rama *master* combinando los cambios de una rama llamada *cabecera*: Otra opción es crear un nuevo *commit* en la rama *cabecera* combinando los cambios de cualquier otra rama:
    
    Git es asombroso porque puede saber cuáles cambios deben conservarse en una rama y cuáles no. En casos de conflictos, asegúrate de guardar tus cambios antes de hacer `git checkout` para evitar perder tu trabajo.
    
    ## Comandos básicos de GitHub
    
    - `git init`: crear un repositorio.
    - `git add`: agregar un archivo a staging.
    - `git commit -m “mensaje”`: guardar el archivo en git con un mensaje.
    - `git branch`: crear una nueva rama.
    - `git checkout`: moverse entre ramas.
    - `git push`: mandar cambios a un servidor remoto.
    - `git fetch`: traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local.
    - `git merge`: tiene dos usos. Uno es la fusión de ramas, funcionando como un *commit* en la rama actual, trayendo la rama indicada. Su otro uso es guardar los cambios de un servidor remoto en nuestro directorio.
    - `git pull`: fetch y merge al mismo tiempo.
    - `git checkout “codigo de version” “nombre del archivo”`: volver a la última versión de la que se ha hecho *commit*.
    - `git reset`: vuelve al pasado sin posibilidad de volver al futuro, se debe usar con especificaciones.
    - `git reset --soft`: vuelve a la versión en el repositorio, pero guarda los cambios en staging. Así, podemos aplicar actualizaciones a un nuevo *commit*.
    - `git reset --hard`: todo vuelve a su versión anterior
    - `git reset HEAD`: saca los cambios de staging, pero no los borra. Es lo opuesto a git add.
    - `git rm`: elimina los archivos, pero no su historial. Si queremos recuperar algo, solo hay que regresar. se utiliza así:`git rm --cached` elimina los archivos en staging pero los mantiene en el disco duro.`git rm --force` elimina los archivos de git y del disco duro.
    - `git status`: estado de archivos en el repositorio.
    - `git log`: historia entera del archivo.
    - `git log --stat`: cambios específicos en el archivo a partir de un commit.
    - `git show`: cambios históricos y específicos hechos en un archivo.
    - `git diff “codigo de version 1” “codigo de version 2”`: comparar cambios entre versiones.
    - `git diff`: comparar directorio con *staging*.
- **Resolución de conflictos al hacer un merge**
    
    **Git nunca borra nada**, a menos que nosotros se lo indiquemos. Cuando usamos los comandos `git merge` o `git checkout` estamos cambiando de rama o creando un nuevo *commit*, no borrando ramas ni *commits* (recuerda que puedes borrar commits con `git reset` y ramas con `git branch -d`).
    
    Git es muy inteligente y puede resolver algunos conflictos automáticamente: cambios, nuevas líneas, entre otros. Pero algunas veces no sabe cómo resolver estas diferencias, por ejemplo, cuando dos ramas diferentes hacen cambios distintos a una misma línea.
    
    Esto lo conocemos como **conflicto** y lo podemos resolver manualmente. Solo debemos hacer el *merge*, ir a nuestro editor de código y elegir si queremos quedarnos con alguna de estas dos versiones o algo diferente. Algunos editores de código como Visual Studio Code nos ayudan a resolver estos conflictos sin necesidad de borrar o escribir líneas de texto, basta con hacer clic en un botón y guardar el archivo.
    
    Recuerda que siempre debemos crear un nuevo commit para aplicar los cambios del merge. Si Git puede resolver el conflicto, hará commit automáticamente. Pero, en caso de no pueda resolverlo, debemos solucionarlo y hacer el commit.
    
    Los archivos con conflictos por el comando `git merge` entran en un nuevo estado que conocemos como ***Unmerged***. Funcionan muy parecido a los archivos en estado *Unstaged*, algo así como un estado intermedio entre Untracked y Unstaged. Solo debemos ejecutar `git add` para pasarlos al área de staging y `git commit` para aplicar los cambios en el repositorio.
    
    ## Cómo revertir un merge
    
    Si nos hemos equivocado y queremos cancelar el merge, debemos usar el siguiente comando:
    
    ```
    git merge --abort
    
    ```
    
    ## Conflictos en repositorios remotos
    
    Al trabajar con otras personas, es necesario utilizar un repositorio remoto.
    
    ­
    
    - Para copiar el repositorio remoto al directorio de trabajo local, se utiliza el comando `git clone <url>`, y para enviar cambios al repositorio remoto se utiliza `git push`.
    - Para actualizar el repositorio local se hace uso del comando `git fetch`, luego se debe fusionar los datos traídos con los locales usando `git merge`.
    - Para traer los datos y fusionarlos a la vez, en un solo comando, se usa `git pull`.­- Para crear commits rápidamente, fusionando `git add` y `git commit -m ""`, usamos `git commit -am ""`.­- Para generar nuevas ramas, hay que posicionarse sobre la rama que se desea copiar y utilizar el comando `git branch <nombre>`.
    - Para saltar entre ramas, se usa el comando `git checkout <branch>`­- Una vez realizado los cambios en la rama, estas deben fusionarse con `git merge`.
    - El merge ocurre en la rama en la que se está posicionado. Por lo tanto, la rama a fusionar se transforma en la principal.
    - Los merges también son commits.
    - Los merges pueden generar conflictos, esto aborta la acción y pide que soluciones el problema manualmente, aceptando o rechazando los cambios que vienen.
- **Cómo funcionan las llaves públicas y privadas**
    
    Las **llaves públicas y privadas**, conocidas también como cifrado asimétrico de un solo camino, sirven para mandar mensajes privados entre varios nodos con la lógica de que firmas tu mensaje con una llave pública vinculada con una llave privada que puede leer el mensaje.
    
    Las llaves públicas y privadas nos ayudan a cifrar y descifrar nuestros archivos de forma que los podamos compartir sin correr el riesgo de que sean interceptados por personas con malas intenciones.
    
    ## Cómo funciona un mensaje cifrado con llaves públicas y privadas
    
    - Ambas personas deben crear su llave pública y privada.
    - Ambas personas pueden compartir su llave pública a las otras partes (recuerda que esta llave es pública, no hay problema si la “interceptan”).
    - La persona que quiere compartir un mensaje puede usar la llave pública de la otra persona para cifrar los archivos y asegurarse que solo puedan ser descifrados con la llave privada de la persona con la que queremos compartir el mensaje.
    - El mensaje está cifrado y puede ser enviado a la otra persona sin problemas en caso de que los archivos sean interceptados.
    - La persona a la que enviamos el mensaje cifrado puede emplear su llave privada para descifrar el mensaje y ver los archivos.
    
    Nota: puedes compartir tu llave pública, pero nunca tu llave privada.
    
- **Configura tus llaves SSH en local**
    
    En este ejemplo, aprenderemos **cómo configurar nuestras llaves SSH en local**.
    
    ## Cómo generar tus llaves SSH
    
    ### 1. Generar tus llaves SSH**
    
    Recuerda que es muy buena idea proteger tu llave privada con una contraseña.
    
    ```
    ssh-keygen -t rsa -b 4096 -C "tu@email.com"
    
    ```
    
    ### 2. Terminar de configurar nuestro sistema.
    
    **En Mac**:
    
    - Encender el “servidor” de llaves SSH de tu computadora:
    
    ```
    eval "$(ssh-agent -s)"
    
    ```
    
    Crea un archivo config…
    
    Con Vim `vim config`
    
    Con VSCode `code config`
    
    Si usas una versión de OSX superior a Mac Sierra (v10.12), debes crear o modificar un archivo “config” en la carpeta de tu usuario con el siguiente contenido (ten cuidado con las mayúsculas):
    
    Host *
    
    ```
    Host *
    
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ruta-donde-guardaste-tu-llave-privada
    
    ```
    
    - Añadir tu llave SSH al “servidor” de llaves SSH de tu computadora (en caso de error puedes ejecutar este mismo comando pero sin el argumento -K):
    
    ```
    ssh-add -K ruta-donde-guardaste-tu-llave-privada
    ```
    
- **Uso de GitHub**
    
    **GitHub** es una plataforma que nos permite guardar repositorios de Git que podemos usar como servidores remotos y ejecutar algunos comandos de forma visual e interactiva (sin necesidad de la consola de comandos).
    
    Luego de crear nuestra cuenta, podemos crear o importar repositorios, crear organizaciones y proyectos de trabajo, descubrir repositorios de otras personas, contribuir a esos proyectos, dar estrellas y muchas otras cosas.
    
    El `README.md` es el archivo que veremos por defecto al entrar a un repositorio. Es una muy buena práctica configurarlo para describir el proyecto, los requerimientos y las instrucciones que debemos seguir para contribuir correctamente.
    
    Para clonar un repositorio desde GitHub (o cualquier otro servidor remoto) debemos copiar la URL (por ahora, usando `HTTPS`) y ejecutar el comando `git clone` + la URL que acabamos de copiar. Esto descargará la versión de nuestro proyecto que se encuentra en GitHub.
    
    Sin embargo, esto solo funciona para las personas que quieren empezar a contribuir en el proyecto.
    
    ## Cómo conectar un repositorio de GitHub a nuestro documento local
    
    Si queremos conectar el repositorio de GitHub con nuestro repositorio local, que creamos usando el comando `git init`, debemos ejecutar las siguientes instrucciones:
    
    - Guardar la URL del repositorio de GitHub con el nombre de origin
    
    ```
    git remote add origin URL
    
    ```
    
    - Verificar que la URL se haya guardado correctamente:
    
    ```
    git remote
    git remote -v
    
    ```
    
    - Traer la versión del repositorio remoto y hacer *merge* para crear un *commit* con los archivos de ambas partes. Podemos usar `git fetch` y `git merge` o solo `git pull` con el *flag* `-allow-unrelated-histories`:
    
    ```
    git pull origin master --allow-unrelated-histories
    
    ```
    
    - Por último, ahora sí podemos hacer `git push` para guardar los cambios de nuestro repositorio local en GitHub:
    
    ```
    git push origin master
    
    ```
    
    ## Cómo autenticarte en GitHub 2022
    
    Antes de empezar debemos renombrar la rama ‘máster’ a ‘main’, este es el nuevo estándar en GitHub, para esto:
    
    1. Primero nos posicionamos en la rama a la que queremos cambiarle el nombre.
    2. Ejecutamos el siguiente comando: `git branch -M main`
    
    **Pasos para crear un token de acceso personal.**
    
    **Desde el 2022 GitHub** ya no deja hacer el push con la contraseña del propio GitHub, para esto tenemos que crear un token, y este token es la contraseña que vamos a colocar cuando nos pida clave.
    
    > Descubre el uso de tags en Github
    > 
    
    Seguir la secuencia: Ingresamos a nuestra cuenta de GitHub.
    
    1. Buscamos `Settings`
    2. Click en `Developer settings`
    3. Click en `Personal access tokens`
    4. Click en `Generate new token` aquí se puede colocar un nombre, la fecha de expiración.
    5. Tildar en repo y luego click en el botón verde `Generate token`
- **Manejo de ramas en GitHub**
    
    Las ramas nos permiten hacer cambios a nuestros archivos sin modificar la versión principal (master). Puedes trabajar con ramas que nunca envías a GitHub, así como pueden haber ramas importantes en GitHub que nunca usas en el repositorio local. Lo crucial es que aprendas a manejarlas para trabajar profesionalmente.
    
    Si, estando en otra rama, modificamos los archivos y hacemos *commit*, tanto el historial(`git log`) como los archivos serán afectados. La ventaja que tiene usar ramas es que las modificaciones solo afectarán a esa rama en particular. Si luego de “guardar” los archivos(usando `commit`) nos movemos a otra rama (`git checkout otraRama`) veremos como las modificaciones de la rama pasada **no aparecen** en la `otraRama`.
    
    ## Comandos para manejo de ramas en GitHub
    
    - Crear una rama:`git branch branchName`
    - Movernos a otra rama:`git checkout branchName`
    - Crear una rama en el repositorio local:`git branch nombre-de-la-rama` o `git checkout -b nombre-de-la-rama`.
    - Publicar una rama local al repositorio remoto:`git push origin nombre-de-la-rama`.
    
    Recuerda que podemos ver gráficamente nuestro entorno y flujo de trabajo local con Git utilizando el comando `gitk`. Gitk fue el primer visor gráfico que se desarrolló para ver de manera gráfica el historial de un repositorio de Git.
    
    > 
    > 
- **Configurar múltiples colaboradores en un repositorio de GitHub**
- **Flujo de trabajo profesional: Haciendo merge de ramas de desarrollo a master**
    
    Para poder desarrollar software de manera óptima y ordenada, necesitamos tener un flujo de trabajo profesional, que nos permita trabajar en conjunto sin interrumpir el trabajo de otros desarrolladores. Una buena práctica de flujo de trabajo sería la siguiente:
    
    - Crear ramas
    - Asignar una rama a cada programador
    - El programador baja el repositorio con `git pull origin master`
    - El programador cambia de rama
    - El programador trabaja en esa rama y hace *commits*
    - El programador sube su trabajo con `git push origin #nombre_rama`
    - El encargado de organizar el proyecto baja, revisa y unifica todos los cambios
- **COMANDOS MAS UTIIZADOS PARA UTILIZARLOS SE RECOMIENDA ESTE EN MINUSCULA**
    
    CD:  lo utilizamos en mac para elegir la carpeta donde esta nuestro proyecto 
    
    PWD: nos indica la ruta o la carpeta donde estamos situados
    
    LS: nos muestra las carpetas donde estamos situados en el terminal 
    
    LS -A: nos muestra las carpetas en lista de las carpetas donde estamos situados incluso nos muestra las carpetas ocultas
    
    CLEAR: elimina todo lo escrito en el terminal 
    
    GIT INIT el comando para iniciar nuestro repositorio, o sea, indicarle a Git que queremos usar su sistema de control de versiones en nuestro proyecto
    
    GIT COMMIT -AM “ el mensaje “ el comando nos sirve para agregar los cambios y el mensaje del commit  Importante utilizarlo optimiza el trabajo
    
    GIT STATUS. el comando nos sirve para ver el estatus de los cambios realizados
    
    GIT LOG: lista de manera descendente los commits realizados.
    
    GIT LOG  - -STAT:  además de listar los commits, muestra la cantidad de bytes añadidos y eliminados en cada uno de los archivos modificados.
    
    GIT SHOW: es muy importante por que nos muestra todos los cambios históricos hechos, incluyendo las lineas de código, las lineas de texto o las lineas de cualquier archivo que se hayan añadido o cambiado, cuando se ha hecho cambios y quien los hizo. por otro lado nos muestra en que RAMA estamos situados IMPORTANTE para salir le damos (Q)
    
    GIT BRANCH **-nombre de la rama-**: Con este comando se genera una nueva rama.
    
    GIT CHECKOUT **-nombre de la rama-**: Con este comando puedes saltar de una rama a otra. importante en MAC para poder ver en donde estamos situado en la rama podríamos verlo en git status y ver en que rama estamos 
    
    GIT MERGE **nombre de la rama para combinar** debe estar siempre la principal y fusionar las ramas secundarias 
    
    GIT MERGE: tiene dos usos. Uno es la fusión de ramas, funcionando como un *commit* en la rama actual, trayendo la rama indicada. Su otro uso es guardar los cambios de un servidor remoto en nuestro directorio.
    
    GIT DIFF sirve para saber que cambios hemos realizado importante utilizarlo
    
    ## 1. SUBIR A GITHUB
    
    GIT INIT  para indicar que queremos subir un repositorio 
    
    GIT REMOTE ADD ORIGIN y el URL del repositorio 
    
    GIT REMOTE el comando nos sirve para evidencia el repositorio llamado ORIGIN
    
    GIT REMOTE -V el comando nos muestra el origin con las dos opciones FETCH para traer los archivos y PUSH para enviar los archivos 
    
    GIT ADD . para agregar todos los archivos en los que se van a trabajar
    
    GIT COMMIT -AM “Mensaje” Agregar mensaje 
    
    GIT PUSH ORIGIN MAIN esta es para subir el repositorio 
    
    ## 2. Cambios ajustes del proyecto subido
    
    Orden
    
    1. git pull origin nombre de la rama - traer el origen de la rama que se este trabajando o haciendo el cambio 
    2. git commit -am “” se agrega el mensaje del cambio 
    3. git pull origin Nombre de la rama - se hace nuevamente por seguridad y para que no tenga errores 
    4. git push origin nombre de la rama - esto es para enviar los cambios al repositorio 
    
    cuando se hace un cambio antes de hacer un commit llamamos la ultima versión que tenemos en el proyecto 
    
    GIT PULL  Sirve para traer la ultima versión del servidor 
    
    GIT PULL ORIGIN NOMBRE DE LA RAMA acá debemos hacer pull a la rama en la que estamos trabajando, importante despues del commit volver a utilizar en comando para que no tenga errores 
    
    GIT PUSH ORIGIN NOMBRE DE LA RAMA se utiliza para enviar los cambios al repositorio
    
    ## Manejo de ramas
    
    GIT SHOW-BRANCH Nos muestra las ramas que existen y su historial igual como GIT SHOW-BRANCH - -ALL
    
    ## SUBIR UN REPOSITORIO EXISTENTE O CLONADO EN GITHUB PASO A PASO
    
    1. Iniciar y buscar la carpeta desde el terminal
    2. git status : para saber el estado del repositorio si esta ok o tiene cambios
    3. Si tiene cambios, se agrega el commit -am “mensaje”
    4. hacemos un git pull origin main o según la rama en la que este solo para estar seguros que no halla errores, y poder traer lo que hay en internet  
    5. luego hacemos git push origin main 

## **Flujo de trabajo profesional: Haciendo merge de ramas de desarrollo a master**

una buena practica es dejar la rama MAIN como principal y trabajar en las otras ramas Header, Footer etc 

- asi git checkout header  segun el nombre que tengas en la rama
- para trabajar en las otras ramas sea ya creado en local o clonando un repositorio se llama de la siguiente forma git pull origin footer según sea la rama que necesite  o haya creado luego cambiamos de rama git checkout footer
- ya realizado los cambio o ajustes podremos hacer la subida de los cambios
- git commit -am “mensaje”
git pull origin footer
git push origin footer
- Si estoy en el proyecto raíz tengo que traer los cambios que se hayan echo tanto en el proyecto raíz como en los proyectos clonados con git pull origin y el nombre de la rama utilizada

COMBINAR LAS RAMAS DE LOS TRABAJOS FINALES 

Nos posicionamos en la rama principal “main” con git checkout main 

Fusionamos la ramas con git merge header según sea el nombre utilizado