# Linux Server Configuration

In this project, the server is configured for [Catalog app](https://github.com/suldev8/catalog) to be deployed on Amazon Lightsail using Ubuntu Server.

## Connecting via SSH

You can make SSH connection using grader as a user, IP address: [52.57.34.107](http://52.57.34.107), port is 2200 and the RSA private key.

```bash
ssh grader@52.57.34.107 -p 2200 -i /path/to/key
```
## Summary
After creating an Ubuntu Server instance on Amazon Lighsail. Followed these steps.
* The `ufw` is configured to only allow connections for `SSH` (port 2200), `HTTP` (port 80), and `NTP` (port 123). And changed the default port of SSH from `22` to `2200` 

* Installed Apache, mod_wsgi, and PostgreSQL. With Apache created a configuration file for WSGI file which is located on `/var/www/catalog/catalog.wsgi`. With PostgreSQL created a user named `suldev8` using this user created a database named `catalog`. 

* Using git cloned the [Catalog app](https://github.com/suldev8/catalog) repository to `/var/www/catalog`. 

* Created a user named `grader` and given the `sudo` access and generated SSH RSA keys and the public key is located on `/home/grader/.ssh/authorized_keys
`

## Resources
These links helped me a lot during the configuration and the deployment.
* [http://flask.pocoo.org/docs/1.0/deploying/mod_wsgi/](http://flask.pocoo.org/docs/1.0/deploying/mod_wsgi/) - Install mod_wsgi and configure Apache
* [https://link.medium.com/3Qsa9TT80S](https://link.medium.com/3Qsa9TT80S) - Deploying Flask Application Using mod_wsgi
* [https://youtu.be/-LwI4HMR_Eg](https://youtu.be/-LwI4HMR_Eg) - Installation and configuration PostgreSQL on Ubuntu Linu
