---
title: "OpenVpn Docker"
date: 2021-05-18T15:55:39+02:00
draft: false
---

[Image github](https://github.com/kylemanna/docker-openvpn)

[Tutorial](https://www.camillebaronnet.fr/blog/fr/serveur-openvpn-avec-docker)


## Requirement

- Open UDP port 1194 

- Install :
    - docker
    - docker compose
    - git

## Process

#### Create folder `openvpn` :
```shell
cd /srv
sudo mkdir openvpn
cd openvpn
```

#### Build image (fork of  kylemanna/docker-openvpn) :
```shell
git clone https://github.com/ArnaudBaley/fork-docker-openvpn.git
cd fork-docker-openvpn
docker build -t custom-openvpn .
```

#### Create folder `openvpn/data` :
```shell
cd ../../
sudo mkdir openvpn/data
```

#### Create configurations (fill your value for MY_IP_OR_MY_DOMAIN) : 
(-c allow clients to communicate between them)
```shell
sudo docker run -v /srv/openvpn/data:/etc/openvpn --rm custom-openvpn ovpn_genconfig -c -u udp://MY_IP_OR_MY_DOMAIN
```

#### Launch script ovpn_initpki :
```shell
sudo docker run -v /srv/openvpn/data:/etc/openvpn --rm -it custom-openvpn ovpn_initpki
```

#### Create file `docker-compose.yml` :
```shell
cd /srv/openvpn/
sudo nano docker-compose.yml
```

`docker-compose.yml` :
```yml
app:
  image: 'custom-openvpn'
  volumes:
    - './data:/etc/openvpn'
  ports:
    - "1194:1194/udp"
  cap_add:
    - NET_ADMIN
  restart: always
```

#### Start OpenVPN server :
```shell
sudo docker-compose up -d
```

#### Generate a client certificate without a passphrase (fill your value for CLIENT_NAME) :
```shell
sudo docker run -v /srv/openvpn/data:/etc/openvpn --rm -it custom-openvpn easyrsa build-client-full CLIENT_NAME nopass
```

#### Retrieve the client configuration with embedded certificates (fill your value for CLIENT_NAME) :

a - Normal case
```shell
sudo su
docker run -v /srv/openvpn/data:/etc/openvpn --rm custom-openvpn ovpn_getclient CLIENT_NAME > CLIENT_NAME.ovpn
```

b- IF OTP (2FA Google Authenticator) [SOURCE](https://github.com/kylemanna/docker-openvpn/blob/master/docs/otp.md#using-two-factor-authentication-for-users)

```shell
docker run -v /var/openvpn/data:/etc/openvpn --rm -t custom-openvpn ovpn_otp_user CLIENT_NAME
```


#### Get file with WinSCP