# Local `pip` repository

- Install `python3-pip` and `pip2pi`. Become `root` first for `pip2pi`.
```shell
apt install python3-pip
sudo su -
pip3 install pip2pi
```
- Create a local `pip` directory `/opt/pip`. Download `pip` packages to this directory and run `dir2pi`. Finally, copy `/opt/pip` to `/var/www/html/` for web hosting.

```shell
mkdir /opt/pip
pip3 install --download /opt/pip django==2.0.6
dir2pi /opt/pip
cp -av /opt/pip /var/www/html/
```
