# Getting Started

To download the project and its submodules, run the command below:

git clone --recurse-submodules https://github.com/maikelsouza/ems-algaposts-meta.git

## # ems-algaposts-meta

This project is an exercise from the AlgaWorks microservices course.

The task is to develop a system composed of two microservices that communicate asynchronous via RabbitMQ using Spring amqp.
The system will be responsible for sending the posts, calculating the value of each post. This calculation will be performed in another microservice.

## Project Diagram

The diagram below shows how the Comment and Moderation microservices communicate asynchronous via RabbitMQ.

## Microservice: Post-service

This microservice is responsible for:

- Create a new post and submit it for calculation;
- View the details of an post;
- List posts with pagination;

### Endpoints

There are three endpoints:

- **POST** `/api/posts`  
  Creates a new post.

- **GET** `/api/posts/{id}`  
  Retrieves a post by its ID.

- **GET** `/api/posts`  
  Retrieves all posts with pagination.
- 
### Repository

- [**Post-service**](https://github.com/maikelsouza/ems-algaposts-post-service)

## Microservice: text-processor-service

This microservice is responsible for:

Consume the text-processor-service.post-processing.v1.q queue.
Process the body field of the received post.
Calculate:
- The number of words in the body of the text.
- The estimated value (words * $0.10).

### Repository

- [**Text-processor-service**](https://github.com/maikelsouza/ems-algaposts-text-processor-service)
