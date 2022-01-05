# Docker

What is docker?

Docker is an open source containerization platform. It enables developers to package applications into containers—standardized 
executable components combining application source code with the operating system (OS) libraries and dependencies required to run 
that code in any environment.

for more follow this link : https://www.ibm.com/cloud/learn/docker - this link has answer to the questions like, what is docker, docker file, docker image, docker container, etc.

## Docker Commands

### `run` command
- Used to run the docker image
- first it searches the images locally, if it finds then it runs the image from local storage
- if it cannot find the image locally, then it searches it on the remote repository, if the image is found, it downloads the image and then run it, otherwise it shows the error
- Example : ![image](https://user-images.githubusercontent.com/63965898/148259235-e2916273-8386-4f3c-93a3-41b0d59bb50e.png)
- In the ablove picture I first excecuted the run command to use the busybox image, so the docker started searching it locally and after it cannot find it locally it searched it on remote repository and then downloaded it and then executed successfully.

### `ps` command
- It is used to list all the running containers
- It list all the containers which are running for some longer amount of time.
- For example : running the command `docker run busybox echo hello world`, docker ps will not list this image because it executes very quickly.
- So for running the busybox for longer amount of time we can use the command `docker run busybox ping google.com`, this will run busybox image for longer amount of time and actually it will keep running, so we can open an another window and try runnning `docker ps`, and now it will show the busybox in the table.![image](https://user-images.githubusercontent.com/63965898/148261448-03886243-b12f-4173-b644-05c6e084057f.png)
- So using `ps` command we can see all the imformation about the image, like the id, etc.
- For seeing all the images that have been created, we can use another ps command, `docker ps --all`. This will show all the containers which were created. ![image](https://user-images.githubusercontent.com/63965898/148262216-fdde8f83-9dc3-44f7-b796-5f960f237509.png)

