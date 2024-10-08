# Code Autograding Web Application

## Introduction
This is a full-stack web application for automated code grading.
It provide scalability, functionality and performance testing.

Provides an endpoint for grading programming assignments. Has the functionality
needed to create a grader image based on `grader-image` and to copy source code
and test code to the image.

When the grader API is run, the Docker daemon should be exposed to the grader
API to allow running the created Docker images.

## RUNNING

for dev environment run

```
sudo docker compose up --build
```

for production environment run

```
sudo docker compose -f docker-compose.prod.yml up --build
```

## TESTS:

run following in the root of the project when the application is running

```
sudo docker compose run --rm --entrypoint=npx e2e-playwright playwright test
```

### The application is run on localhost:7800

## API
programming-api
  GET /assignment/latest/:user_uuid
  GET /scores/:user_uuid
  GET /grading/status/:id
grader-api
  POST /api/grader/submit/answer

## Structure
```
├── .gitignore
├── PERFORMANCE_TEST_RESULTS.md
├── README.md
├── REFLECTION.md
├── docker-compose.prod.yml
├── docker-compose.yml
├── e2e-playwright
│   ├── Dockerfile
│   ├── README.md
│   ├── package.json
│   ├── playwright.config.js
│   ├── test-results
│   │   └── .last-run.json
│   └── tests
│       └── grader-api.spec.js
├── flyway
│   └── sql
│       ├── V1___initial_schema.sql
│       └── V2___first_assignments.sql
├── grader-api
│   ├── Dockerfile
│   ├── README.md
│   ├── app.js
│   ├── deps.js
│   └── services
│       ├── database.js
│       └── gradingService.js
├── grader-image
│   ├── Dockerfile
│   ├── README.md
│   ├── build.sh
│   ├── example-test-code
│   │   ├── code.py
│   │   └── test-code.py
│   └── grade.sh
├── k6
│   ├── README.md
│   ├── loading_assignment.js
│   └── submit_assignment.js
├── nginx
│   └── nginx.conf
├── programming-api
│   ├── Dockerfile
│   ├── Dockerfile.prod
│   ├── app.js
│   ├── database
│   │   └── database.js
│   ├── deps.js
│   └── services
│       └── programmingAssignmentService.js
├── programming-ui
│   ├── .gitignore
│   ├── Dockerfile
│   ├── Dockerfile.prod
│   ├── README.md
│   ├── astro.config.mjs
│   ├── node_modules
│   ├── package.json
│   ├── public
│   │   └── favicon.svg
│   ├── src
│   │   ├── components
│   │   │   ├── Assignment.svelte
│   │   │   ├── Header.svelte
│   │   │   └── Submission.svelte
│   │   ├── env.d.ts
│   │   ├── layout
│   │   │   ├── Header.svelte
│   │   │   └── Layout.astro
│   │   ├── pages
│   │   │   ├── assignment.astro
│   │   │   └── index.astro
│   │   └── stores
│   │       └── stores.js
│   ├── svelte.config.js
│   ├── tailwind.config.cjs
│   └── tsconfig.json
└── project.env
```
