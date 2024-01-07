# Fullstack Application
Fullstack REST API using Node.js, Express, Prisma and PostgreSQL.
The application is mainly divided into three components - db, backend and frontend.

1. For db, postgresql is used for storing user information.

2. For backend, nodejs container providing REST APIs to interact with the db and frontend.
    - Run below commands to initialize backend component
        1. `npm init`  #initialising nodejs project
        2. `npm i express prisma @prisma/client`
        3. `npx prisma init`     #initialize prisma
            This command will create a `schema.prisma` file inside `prisma` folder.
            Add User model in `schema.prisma` file.
    - To test the application, without frontend, run below commands.
        1. Run `docker compose up`. This will build & run both containers db & backend.
        2. Exec into postgres db container, to check the tables etc. Run `docker exec -it db psql -U postgres`.
        Run `\dt` command to check the relations/tables present in the db.
        3. Exec into backend nodejs container to initialize db tables or migrating models, run `docker exec -it backend npx prisma migrate dev --name init`.
        4. The application is running on port `4000`. Use POSTMAN or any API client to access the APIs - POST, PUT, GET and DELETE the user/s.

3. For frontend, nextjs is used.
    - Run `npx create-next-app@latest --no-git`. This will bootstrap a nextjs project.
    - Enter the frontend directory created using above command.
    - `npm i axios`. To install axios dependency to interact with backend.
    - Refer `frontend` folder in the project to create required components, index file and the docker files.
    - Run `docker compose up -d` in the main directory of the project to run all three containers. Run `docker compose up -d frontend` if rest two containers `db` and `backend` are already running.
    - If required, to test the frontend locally, run `npm run dev` inside frontend folder. 