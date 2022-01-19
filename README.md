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

### Container lifecycle

<img src="https://user-images.githubusercontent.com/63965898/148417361-c98efdca-bf44-42cb-87f4-c0ce61e4cf85.png" width="600" height="350"/>

#### `docker run = docker create + docker start`

- The `run` command is the combination of two other commands called `create` and `start`.
- the `create` comammnd is used to only create the container.
  - Like : ![image](https://user-images.githubusercontent.com/63965898/148419543-d8eb559d-b3e9-4059-8d9a-5005a9794359.png)
  - The long aplha numberic string is the id of the conatiner. The `create` command just created a container.
- the `start` command is used to start the container.
- but when we use `start` like `docker start container_id` it just prints the id of the container.
- for getting the output we will have to use the start command like `docker start -a cotainer_id`.
- so by default `run` command runs the container and prints the output.

### `system prune` command
- this commad is used to remove 
  - all the stopped container.
  - all networks not used by atleast one container.
  - all dangling images.
  - all build cache - all the images downloaded from docker hub.

- Example of - `docker system prune`
- ![image](https://user-images.githubusercontent.com/63965898/150167914-57b4ab30-9cd8-4950-8ccc-9fa4b087baca.png)

### `docker logs` command

- this command shows all the logs that have been printed by a container.
- it does not re run the container but just prints all the logs printed during the container execution.
- Example :
 ![image](https://user-images.githubusercontent.com/63965898/150169363-fd9fea04-2a48-4493-a325-741643b7059d.png)
- in the above picture we created a container
- then we started the container with `docker start`, without -a, this will execute / run the conatiner internally.
- now when we execute `docker logs conatiner_id`, we can see the logs or output that was emitted by the container during it's execution.
- the logs sommand go back to the conatiner and fetches all the logs that hve been emitted by the container.

### `stop` and `kill` command

- both _stop_ and _kill_ command are used to stop a a running continer.
- difference is just that, `stop` is like shutting down, it performs some cleaning operations and then gracefully shuts down the container.
- while the `kill` command is like power off, it doesn't do any operation and directly kills all the process of the container.
- also, if the _stop_ command takes more than 10 seconds to stop a container than docker internally calls the _kill_ command.

![image](https://user-images.githubusercontent.com/63965898/150172729-8ac42b2c-11b1-49e3-9bf4-954be5689a71.png)

- in the above image first we created a container.
- then we started the conatiner.
- the conatiner runs for forever.
- now first we gave the `stop` command but it takes more than 10 seconds and docker runs the `kill` command internally.
- after that we started the conatiner one more time.
- this time we give the `kill` command and the conatiner is stopped instantly.







