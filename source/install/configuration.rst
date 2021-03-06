===============================================================
Configuration of Lizmap
===============================================================

In some server, additionnal settings should be done into Lizmap.
Settings should be set into the ``lizmap/var/config/`` directory.

Configuration files
===================

There are several configuration files for Lizmap. There are into lizmap/var/config/.

Framework configuration files:

* ``mainconfig.ini.php`` contains many configuration parameters, mainly for
  the framework used by Lizmap. You may want to modify some of them, like
  the available languages etc. **DON'T MODIFY mainconfig.ini.php**. Put
  parameters with their new values into ``localconfig.ini.pp`` instead!
* ``localconfig.ini.php`` contains configuration parameters that are specific to
  your installation. So you put into it any parameters you can find into
  ``mainconfig.ini.php`` and you want to change.
* ``liveconfig.ini.php`` is containing parameters from ``mainconfig.ini.php``
  that are changed during the life of the application.

During the execution of Lizmap, ``mainconfig.ini.php``, ``localconfig.ini.pp``,
and ``liveconfig.ini.php`` are merged in this order. So parameters into ``liveconfig.ini.pp``
have higher priority that those into ``localconfig.ini.pp``, which in turn,
have parameters having higher priority over parameters of ``mainconfig.ini.php``.

.. note:: ``liveconfig.ini.php`` and ``localconfig.ini.pp`` may not exists
          on old releases.

Other framework configuration files:

* ``profiles.ini.php`` contains all credentials to access to databases, smtp
  servers, ldap etc. You should modify it to set these access parameters.
* ``installer.ini.php`` contains informations about Lizmap modules and their
  state. Don't touch it, and don't erase it between upgrades. You can delete it
  only if you want to reinstall Lizmap.

Lizmap configuration files:

* ``lizmapConfig.ini.php`` contains configuration parameters specific to
  Lizmap.
* ``lizmapLogConfig.ini.php`` contains configuration for the Lizmap logger

For backups and upgrades, you should keep ``localconfig.ini.pp``,  ``liveconfig.ini.php``,
``lizmapConfig.ini.php``, ``profiles.ini.php``, ``lizmapLogConfig.ini.php`` and  ``installer.ini.php``.
They are all modified during the life or the installation of the application.


Setting language
=================

Lizmap detects automatically the language of the user (given by his browser),
and it supports many languages.

Available language into Lizmap are: fr_FR, en_US, it_IT, es_ES, eu_ES, pt_PT,
el_GR, de_DE, pl_PL, ru_RU, fi_FI, gl_ES, sv_SE, nl_NL, ro_RO, hu_HU.

If the browser of the user indicates an unsupported language code, the default
language of Lizmap is used, and is en_US.

You can change the default language of Lizmap by setting the parameter ``locale``
Into localconfig.ini.php, with your prefered language code.

You can also limit available language by changing the ``availableLocales`` option.

In this example, only 3 languages are available and the default language is italian:

.. code-block:: ini

    locale = it_IT
    availableLocales = en_US,fr_FR,it_IT

There is also a ``fallbackLocale`` option but it is not recommended to change it.

