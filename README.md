# CI/CD_using_springboot_application

##in jenkins configure as follows:

// I am using windows batch to connect to docker demon the env setup should be made 
docker-machine env --shell cmd default
@FOR /f "tokens=*" %%i IN ('docker-machine env --shell cmd default') DO @%%i
//For deleting the existing containers and images ie shell it follows as: docker stop $(docker ps -a -q); docker rm $(docker ps -a -q); docker rmi $(docker ps -q)
FOR /f "tokens=*" %%i IN ('docker ps -a -q') DO docker stop %%i
FOR /f "tokens=*" %%i IN ('docker ps -a -q') DO docker rm %%i
FOR /f "tokens=*" %%i IN ('docker ps -q') DO docker rmi %%i

// cmd for stop, rm, rmi image using batch cmd
FOR /f "tokens=*" %%i IN ('docker ps -aq') DO docker stop %%i && docker rm %%i
FOR /f "tokens=*" %%i IN ('docker images --format "{{.ID}}"') DO docker rmi %%i

cd C:\Users\[System name]\.jenkins\workspace\[job name]
mvn clean package docker:build
docker run --name demo-mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=demo -e MYSQL_USER=demo_user -e MYSQL_PASSWORD=demo_pass -d mysql:5.6
docker run -p 8080:8080 --name demo-app --link demo-mysql:mysql -d [image name]


it should work good now.....!!!!!!!!

