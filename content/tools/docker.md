---
title: "Docker"
date: 2021-05-18T15:55:39+02:00
draft: false
---

**host IP from container**

```shell
sudo ip addr show docker0
```


**Shell in container**
```
docker exec -it <container name> /bin/bash
```

**Extract container id from name :**
```shell
$(docker ps -qlf "name=stack-dev_cherm")
```

**Copy file in container**

Prerequisite : create destination folder in container :

```shell
mkdir retourpatrimoine
```

```shell
cat /home/arnaudb/Bureau/DATA/PROJETS/BATCH/retourPatrimoine_creerCompteServeurAuth/adherent_lfm_888888_O.csv  | docker exec -i $(docker ps -qlf "name=stack-dev_cherm") /bin/bash -c 'cat > /data/retourpatrimoine/adherent_lfm_888888_O.csv'
```

**Show full error at service mount :** 
```
docker service ps --no-trunc mysql
```