# FizzBuzz Rest server
This application is a backend rest server to get result of FizzBuzz game

# Endpoints

    /{number}

accepts integer value and produces json response with the following schema:

    {
      "type": "object",
      "properties": {
        "input": {
          "type": "integer",
          "title": "Interpreted value of the input supplied in the request",
          "examples": [
            789
          ]
        },
        "result": {
          "type": "string",
          "title": "Result of the game",
          "examples": [
            "Fizz"
          ]
        }
      }
    }
 

# Design decisions made
   1) Service created with Spring Boot 2.0
   2) MVC error handling is configured in `RestResponseEntityExceptionHandler` class to provide JSON error responses to the client.
   3) Two Spring configuration files are provided (`dev` and `default`).
   4) `FizzBuzzResource` uses `FizzBuzzService` interface to obtain response and is it's only implementation at the moment is 'FizzBuzzServiceImpl'. By using the interface an alternative implementation can be added without any changes to the web layer.
   