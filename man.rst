cdist-type__ungleich_nextcloud(7)
=======================================
This type installs Nextcloud.

ungleich GmbH <cdist--@--ungleich.ch>


DESCRIPTION
-----------
We suggest to use our type 
__ungleich_nginx_app_proxy for the nginx configuration.
Keep in mind, that you have to install the certificates with 
another type or nginx doesn't start.


REQUIRED PARAMETERS
-------------------
domain
    where Nextcloud runs


DEFAULT PARAMETERS
-------------------
admin-pass  
    Nextcloud default admin passwort: nextcloud

admin-user
    Nextcloud default admin user: nextcloud  

db-name
    Nextcloud default database name: nextcloud     

db-pass     
    Nextcloud default password: nextcloud

db-user 
    Nextcloud default database user: nextcloud    

uri
    Nextcloud default Uniform Resource Identifier (URI): https://download.nextcloud.com/server/releases/nextcloud
         
version
    Nextcloud default version: 11.0.1


OPTIONAL PARAMETERS
-------------------
admin-pass
    Nextcloud admin password

admin-user
    Nextcloud user password

db-name
    Nextcloud database name

db-pass
    Nextcloud password

db-user
     Nextcloud database user

ssl-cert
    Define the path where the ssl-cert is on the $host

ssl-key
    Define the path where the ssl-key is on the $host

uri
     Nextcloud Uniform Resource Identifier (URI)

version
    Nextcloud version

If not set the type uses the default parameters.   

BOOLEAN PARAMETERS
------------------
ssl
    Enable if you want to use SSL

ssl-no-redirect
    Enable if you don't want a redirect to https

custom-config-from-stdin
    Insert this configuration from stdin after the generic part


EXAMPLES
--------

.. code-block:: sh

    # only required
     __ungleich_nextcloud --domain test.example.org

    # set a different admin-user and db-user; ssl is needed
    __ungleich_nextcloud --ssl --admin-user ungleich --db-user ungleich --domain test.example.org 

    # custom config
    __ungleich_nextcloud --domain test.example.org --custom-config-from-stdin << eof

        # some aditional nginx config

    eof


SEE ALSO
--------
- `cdist-type(7) <cdist-type.html>`_


COPYING
-------
Copyright \(C) 2017 ungleich GmbH (www.ungleich.ch). 
Free use of this software is granted under the terms 
of the GNU General Public License version 3 (GPLv3).
