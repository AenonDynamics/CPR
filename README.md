Corporate Package Repository [CPR]
====================================

To serve different packages typ (.deb, npm, archives) we are using a custom repository application called **Package-Monster**. It is a fully integrated component which acts as part of our **Continous Delivery Pipeline**.

## Debian Packages ##

To use Aenon-Dynamics APT Repository you have to download the related public key which signs the index files.

* GPG (dearmored) [pubkey.gpg](https://packages.aenon-dynamics.com/static/pubkey.gpg)
* ASC (ASCII armored [pubkey.asc](https://packages.aenon-dynamics.com/static/pubkey.asc)

**1 Install Repository PGP Key**

```bash
wget -O /usr/share/keyrings/aenon-dynamics.gpg https://packages.aenon-dynamics.com/static/pubkey.pgp
```

**1.2 Create /etc/apt/sources.list.d/aenon-dynamics.list**

```bash
echo "deb [signed-by=/usr/share/keyrings/aenon-dynamics.gpg] https://packages.aenon-dynamics.com/debian stable main" > /etc/apt/sources.list.d/aenon-dynamics.list
```

**1.3 Update your local indexes**

```bash
apt-get update
```

**1.4 Install the requested Packages**

```bash
apt-get install motd-sysinfo
```
