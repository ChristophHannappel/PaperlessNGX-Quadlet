# PaperlessNGX-Quadlet
systemd Quadlet files for running PaperlessNGX with podman rootless.  
Requires Podman v5  
Tested with Fedora Workstation 40  
[Podman Systemd Documentation](https://docs.podman.io/en/v5.0.3/markdown/podman-systemd.unit.5.html)

## Installation
1. Copy the files from `.config/container/systemd` to your `~/.config/containers/systemd/` folder
2. Create a Passwort file with `nano ~/paperless.pass` enter a Password for the Database User
3. Create a new Podman Secret `podman secret create paperless_dbpass ~/paperless.pass` and delete the password file `rm ~/paperless.pass`
4. Run `systemctl --user daemon-reload`
5. Run the container with `systemctl --user start paperlessNGX-pod.service`
6. Create a Superuser with `podman exec -it systemd-paperless-webserver python manage.py createsuperuser`
7. Open the PaperlessNGX Interface with your Browser http://127.0.0.1:8000 or http://serverip:8000
