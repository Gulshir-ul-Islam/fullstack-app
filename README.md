# Fullstack Application
Fullstack REST API using Node.js, Express, Prisma and PostgreSQL.
The application is mainly divided into three components - db, backend and frontend.

1. For db, postgresql is used for storing user information.

2. For backend, nodejs container providing REST APIs to interact with the db and frontend.
    - Run below commands to initialize backend component
        1. npm init  #initialising nodejs project
        2. npm i express prisma @prisma/client
        3. npx prisma init     #initialize prisma
            This command will create a `schema.prisma` file inside `prisma` folder.
            Add User model in `schema.prisma` file.
    - To test the application, without frontend, run below commands.
        1. Run `docker compose up`. This will build & run both containers db & backend.
        2. Exec into postgres db container, to check the tables etc. Run `docker exec -it db psql -U postgres`.
        Run `\dt` command to check the relations/tables present in the db.
        3. Exec into backend nodejs container to initialize db tables or migrating models, run `docker exec -it backend npx prisma migrate dev --name init`.
        4. The application is running on port `4000`. Use POSTMAN or any API client to access the APIs - POST, PUT, GET and DELETE the user/s.