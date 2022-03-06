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
