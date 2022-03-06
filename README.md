INSTALL IMAGE
- sudo docker pull nama_iamge:tag 
  (docker pull mongo:5.0.6-focal)

MELIHAT SEMUA IMAGE
- sudo docker images

MELIHAT SEMUA CONTAINER
- sudo docker container ls --all

MEMBUAT CONTAINER DARI IMAGE YANG SUDAH ADA
- sudo docker container create --name nama_container nama_image:tag 
  (sudo docker container create --name mongoserver506 mongo:5.0.6-focal)
- untuk publish port ke luar container
  (sudo docker container create --name mongoserver506 -p portUntukLuar:portDefault mongo:5.0.6-focal)

MENJALANKAN CONTAINER
- sudo docker container start nama_container 
  (sudo docker container start mongoserver506)

MENGHAPUS CONTAINER
- sebelum hapus, harus stop container
  (docker container stop nama_container nama_container2)
- sudo docker container rm nama_container nama_container2
  (sudo docker container rm mongoserver506)

MENGHAPUS IMAGE
- jika ada kontainer yang memakai image(yang mau dihapus) harus stop dan hapus container dulu
- sudo docker image rm nama_container:tag
  (sudo docker image rm mongo:5.0.6-focal)


CREATE IMAGE
- Create docker file Dockerfile
- Insert image golang => FROM baseImage
- Copy the file you want to use as an image => COPY
- Command to run golang file => CMD [ "go", "run", "/app/main.go" ]
- Build image => sudo docker build --tag nama_image:tag destination_dockerFile or use "."
- Create a container from the image that has been build
- Run container that has been created

CREATE REGISTRY
- Create repository on docker hub
- Change tagname and reponame => docker tag local_image:tag reponame:tagname
- Login from docker cli => sudo docker login
- Push docker => sudo docker push faizdamar1/app-golang:1.0
