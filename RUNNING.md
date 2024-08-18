RUNNING:

for dev environment run

`sudo docker compose up --build`

for production environment run

`sudo docker compose -f docker-compose.prod.yml up --build`

TESTS:

run following in the root of the project when the application is running

`sudo docker compose run --rm --entrypoint=npx e2e-playwright playwright test`

The application is run on localhost:7800