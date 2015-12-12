.. title: Migrando a python 3(.5)
.. slug: migrando-a-python-35
.. date: 2015-12-12 11:26:15 UTC-03:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text

Hoy me levanté con ganas de migrar "todos" mis scripts a Python 3.5.

.. TEASER_END: Seguir leyendo

La idea es hacerlo como siempre, prueba y error hasta que el script funcione, leyendo y aprendiendo sobre los errores que vayan sucediendo.

Primero lo primero, instalar Python 3.5 (en mi ubuntu 14.04) y luego crear un virtualenv usando esta versión

Instalar Python 3.5
-------------------

.. code-block:: bash

	$ sudo add-apt-repository ppa:fkrull/deadsnakes
	$ sudo apt-get update
	$ sudo apt-get install python3.5 python3.5-dev

Python 3.5-dev nos permitirá instalar paquetes con setuptools además de otras cosas.

Luego de esto, podemos ejecutar el intérprete de python 3.5 con los comandos:

.. code-block:: bash

    $ python3.5
    Python 3.5.0 (default, Sep 17 2015, 00:00:00) 
    [GCC 4.8.4] on linux
    Type "help", "copyright", "credits" or "license" for more information.
    >>>

Tener en cuenta que (al menos en ubuntu 14.04) ya tenemos los ejecutables: python y python3, que están apuntando a python2.7 y python3.4, respectivamente. No es conveniente cambiar estos links ya que de ellos dependen muchas funciones del sistema.

Crear virtualenv
****************

Lo último que falta es poder crear una environment con python 3.5. En mi caso, uso virtualenwrapper para organizar mis environments.

.. code-block:: bash

    $ mkvirtualenv --python=`which python3.5` python3.5_env

Con el argumento --python le indicamos la ruta absoluta al interprete de python que queremos usar en el environment.

Y eso es todo, ya podemos trabajar con python 3.5 dentro de este environment. En los siguientes posts iré comentando pormenores de esta migración.


PD: Nikola_ la herramienta que uso para armar este blog está migrando a Python 3 dejando de dar soporte a Python 2 en su próximo major release [#]_ , otro gran motivo para hacer esta migración.

.. _Nikola: https://getnikola.com/
.. [#] https://getnikola.com/blog/env-survey-results-and-the-future-of-python-27.html
