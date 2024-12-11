# Flask-mysql-docker-app

1. git clone the project

2. make sure docker is installed in your system

3. Build the docker image of the flask-app

4. Create a network with the command docker "network create -d bridge two-tier-app-nw"

5. Create a mysql docker container with " docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=test@123 -e MYSQL_DATABASE=testdb -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin --name mysql --network two-tier-app-nw mysql:latest"

6. Create a flask container with " docker run -d -p 5000:5000 -e MYSQL_HOST=mysql -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -e MYSQL_DB=testdb --name flask-app --network two-tier-app-nw flask-app:latest"

7. Now the testdb has been created but to messages table inside mysql container , run "docker exec -it <your_mysql_container-id> bash"

8. Then, run "mysql -u root -p"
         "use testdb"
         " run the cmd to create the messages table"

   


     
   
         
