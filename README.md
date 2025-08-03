Deploys minecraft java server using k3s

Install k3s:
  curl -sfL https://get.k3s.io | sh -

Create following directories:
  mkdir -p /app/minecraft/data/world
  mkdir /app/minecraft/data/mods
  mkdir /app/minecraft/data/modpacks
  chmod -R 777 /app/minecraft/data

Place minecraft-java.yml in /app/minecraft

Use the image with the required java version: 
  itzg/minecraft-server:<tag>
https://docker-minecraft-server.readthedocs.io/en/latest/versions/java/

Change external IP to be the host running k3s

Change OPS and Whitelist value to be your UUID

Change minecraft version to desired version eg:
 - name: VERSION
   value: "1.16.5"

Place any server mods in /app/data/mods

Deploy:
  kubectl apply -f minecraft-java.yml
