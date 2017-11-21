# PostgreSQL database

Image docker build on postgres:alpine

the database name is set on "main" and the username/password is indaym

# Installation

Windows :
- You must install [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_windows/)
- During installation download our [Dockerfile](/pg/Dockerfile)
- After installation, launch *Docker Quickstart*
- For all other action with docker stay in *Docker Quickstart terminal*
- See Build

Others OS:
- Install docker
- During installation,  download our [Dockerfile](/pg/Dockerfile)
- Launch the service *docker*
- See Build


Build and launch :
- Go in the directory where you downloaded the *Dockerfile* and build the project with the command

```bash
docker build -t indaym . # <= this dot is inside the command
```

- Create a volume to have persistant data for your database,

```bash
docker volume create indaym-volume
```

- Launch the docker,

```bash
docker run --rm -p 4001:5432 -v indaym-volume:/var/lib/postgresql/data --name indaym indaym
```


Now you can access to database with the url *localhost:4001*

NB :
You can launch back-indaym with docker database with command `yarn run dev` (livereload) or `yarn run start:dev` (without livereload)
