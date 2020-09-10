# Dockerized PERN stack 
Simple react todo app with backend on Express with db(Postgress)

## How to run 
### Docker installation
Follow the instructions from official installation guide and choose appropriate way to install docker for you OS
If you going to run docker on windows, make sure that virtualization and Hyper-V is enabled.
>https://docs.docker.com/engine/install/

Clone the repo and follow a guide below

```
https://github.com/rexvel/pern-stack.git
```

### Build docker-compose image 
All you need to do for this point is just to copy a command

```docker-compose up```

### Database setup

After building and launching app's image , you need to  create database and table. Use next command to setup them in another one terminal 

```docker exec -it postgres psql -U postgres```

The above command will connect you to the psql console of the container running Postgres.
The next set of commands will let us seed the database with some data

```CREATE ROLE <<rolename_set_in_backend>> WITH LOGIN PASSWORD 'your_admin_password';
CREATE DATABASE testdata WITH OWNER <<rolename_set_in_backend>>;
\c testdata  <<rolename_set_in_backend>>
CREATE TABLE todo(
  todo_id SERIAL PRIMARY KEY,
  description VARCHAR(255)
);
INSERT INTO todo (todo_id, description) VALUES ($1, 'test');```

```


If all went well , app should work properly.



```CREATE ROLE postgres WITH LOGIN PASSWORD '1994';
CREATE DATABASE testdb WITH OWNER postgres;
\c testdb  postgres
CREATE TABLE todo(
  todo_id SERIAL PRIMARY KEY,
  description VARCHAR(255)
);
INSERT INTO todo (todo_id, description) VALUES (99, 'test');```

```