zabbix3proxy
=============

Complete installation and configuration of Zabbix 3 Beta Proxy.

Requirements
------------

This role comes with MySQL for database.
If you would like to setup your database, be sure to setup the variables correctly.

Role Variables
--------------

### Database

`zabbix3proxy_db`    
Which database to use. For now, just accepts mysql.

`zabbix3proxy_db_install`    
If is False, make sure that info below connects to a working database loaded with the structure provided by Zabbix.
                                                                          
`zabbix3proxy_dbhost`    
Host address to the databse.

`zabbix3proxy_dbname`    
Database name to connect.

`zabbix3proxy_dbschema`    
Database schema, if needed.

`zabbix3proxy_dbsocket`    
Database socket, if needed.

`zabbix3proxy_dbport`    
Database server port to connect.
                                                                          
`zabbix3proxy_dbrootpassword`    
If installing a dabatase, sets the root password.

`zabbix3proxy_dbuser`    
If installing a dabatase, sets the user to use.

`zabbix3proxy_dbuserpassword`    
If installing a dabatase, sets the root password.


### Zabbix

`zabbix3proxy_betaversion`    
Which beta version will install.

`zabbix3proxy_downloadurl`    
The URL to download the beta version from SourceForge.

`zabbix3proxy_compile_options`    
Options to compile Zabbix.

`zabbix3proxy_install_path`    
Directory to install Zabbix.

`zabbix3proxy_server`    
Server address that proxy is poiting to.

**Note: In `defaults/main.yml` file there is a lot of variables, after 'misc'. These variables are discribed in the zabbix_proxy.conf.j2 file.**

Dependencies
------------

None.

Example Playbook
----------------

This role comes with a Vagrant file. Just fire a `vagrant up` for testing.     
Once the environemnt is up, just run `vagrant provision` or `ansible-playbook -i tests/inventory tests/test.yml`.     
As the date of this commit, the parameter `host_key_checking=False` it's not working. If some SSH connection error occurs, try to execute `export ANSIBLE_HOST_KEY_CHECKING=False`.    

If you want to test the full Zabbix stack (Server, Proxy and Agent), install the other modules with:     
`ansible-galaxy install jonatasbaldin.zabbix3server`     
`ansible-galaxy install jonatasbaldin.zabbix3agent`     
And uncomment the sections on the files: `Vagrantfile`, `tests/inventory` and `tests/test.yml`.     

License
-------

MIT

Author Information
------------------

Jonatas Baldin      
<mailto:jonatas.baldin@gmail.com>      
http://deployeveryday.com
