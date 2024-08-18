# Code Autograding Web Application

This is a full-stack web application for automated code grading.
It provide scalability, functionality and performance testing.

Provides an endpoint for grading programming assignments. Has the functionality
needed to create a grader image based on `grader-image` and to copy source code
and test code to the image.

When the grader API is run, the Docker daemon should be exposed to the grader
API to allow running the created Docker images.

## API
programming-api
  GET /assignment/latest/:user_uuid
  GET /scores/:user_uuid
  GET /grading/status/:id
grader-api
  POST /api/grader/submit/answer
