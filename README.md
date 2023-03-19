# WorPpress behind Traefik 2

Hello everyone, I created this repository to show you how to run **WordPress** with **Traefik** as a **reverse-proxy**. This will let you have a **SSL certificate** on your **self-hosted** instance.

> If you want to host your **WordPress** instance but you don't have a Traefik container yet, you can use this repository that I have created and tested with **WordPress** and other services : https://github.com/MoryCorp/traefik2-minimalist-configuration

## Edit docker-compose.yml

This configuration assumes that you already have a Traefik instance configured with an **entrypoint** named **"websecure"** on port **443**.

If this is the case, the only thing you will have to edit is **line 37** of the docker-compose.yml file, to put your domain name or sub-domain instead of "yourdomain.com" AND the .env file to change passwords etc.

The networks are configured so that only the **Wordpress** instance is exposed via Traefik. **Databases are not exposed** thanks to the "internal" network which is set to "external: false".

## Optional phpMyAdmin

When deploying my **WordPress** instance I also needed to be able to easily view and edit my database.   
So I added a **phpMyAdmin** instance. The latter is optional and can be completely removed or commented out if you don't need it.
