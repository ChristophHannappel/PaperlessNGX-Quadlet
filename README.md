# PaperlessNGX-Quadlet
systemd Quadlet files for running PaperlessNGX with podman rootless.  
Requires Podman v5  
Tested with Fedora Workstation 40  
[Podman Systemd Documentation](https://docs.podman.io/en/v5.0.3/markdown/podman-systemd.unit.5.html)

## Installation
1. Copy the files from `.config/container/systemd` to your `~/.config/containers/systemd/` folder
2. Change the Password at `paperless-postgres.container`
3. Run `systemctl --user daemon-reload`
4. Run the container with `systemctl --user start paperless-pod.service`
5. Create a Superuser with `podman exec -it systemd-paperless-webserver python manage.py createsuperuser`
6. Open the PaperlessNGX Interface with your Browser http://127.0.0.1:8000 or http://serverip:8000
