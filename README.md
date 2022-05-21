# python-flask-docker-https

Sample for building a web application with Python3, Flask, Gunicorn, Nginx (HTTPS) and Docker.

Please note: This project is a playground and is intended for learning.

![overview](https://user-images.githubusercontent.com/105594559/169369472-879dcac5-fc81-4953-9a75-385061bf2210.png)


## Getting started

First install [Docker](https://docs.docker.com/engine/install/) on your system.

If you are on Linux, add your user to the UNIX group called `docker`. For more details, check out [Docker post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/). Reboot your system to apply changes:

```console
sudo usermod -aG docker $USER
sudo reboot
```

Now generate a self-signed SSL certificate (cert.pem, key.pem):

```console
openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365
```

By default, the Nginx in this project wants a SSL certificate stored in `/var/ssl` on your local machine. You can move your generated `cert.pem` and `key.pem` file there. 

If you prefer to use a different directory (for example, because you are on Windows), you can change it. Simply open the file `.env` and replace /var/ssl with your preferred directory.

Now open a terminal in your project directory and launch your web application:
```console
docker compose up
```

Open in web browser: https://127.0.0.1

