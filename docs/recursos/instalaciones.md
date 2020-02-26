# Instalaciones

## Mattermost

* [Instalación](https://docs.mattermost.com/install/prod-docker.html#production-docker-setup-on-ubuntu)
* [Configuración SSL](https://github.com/mattermost/mattermost-docker#start)

!!! note
    El cambio de permisos se ha de hacer con `sudo`
    
    ```
    chown -R 2000:2000 ./volumes/app/mattermost/
    ```
