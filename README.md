# eKitchen APP Backend API

![check](https://github.com/obsismc/ekitchen/actions/workflows/check.yml/badge.svg)

# Recipe APP API

## Introduction

The **eKitchen APP Backend API** is a backend project designed to support a recipe management application. It is ready for deployment with Docker and includes GitHub Actions for continuous integration and automated deployment. The API enables users to perform essential operations such as creating accounts, managing recipes, adding tags, and managing ingredients. It also supports secure user authentication, image uploads, and seamless integration with production-ready tools.

## Features

- **User Authentication**: Secure user registration and login using token-based authentication.
- **Recipe Management**: Create, update, and delete recipes.
- **Ingredient Management**: Add and manage ingredients linked to recipes.
- **Tagging System**: Organize recipes with customizable tags.
- **Image Uploads**: Attach images to recipes for better visualization.

## Technologies Used

- **Programming Language**: Python
- **Framework**: Django, Django REST Framework (DRF)
- **Database**: PostgreSQL
- **Testing**: unittest library
- **Containerization & Deployment**: Docker, Docker Compose, Nignx
- **CI/CD**: GitHub Actions

## Quick Start
[Online Demo](http://ec2-18-117-102-134.us-east-2.compute.amazonaws.com:8000/api/docs/)

Follow these steps to set up and run the project locally.

### Prerequisites

- **Only** Docker & Docker Compose

### Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/ObsisMc/eKitchen.git
   cd eKitchen
   ```

2. **Build Docker Containers**

   ```bash
   docker-compose build
   ```

3. **Apply Migrations**

   ```bash
   docker-compose run --rm app sh -c "python manage.py migrate"
   ```

4. **Run the Application**

   ```bash
   # run
   docker-compose up

   # close
   docker-compose down
   ```
4. **Create a Superuser** (optional)

   ```bash
   docker-compose run --rm app sh -c "python manage.py createsuperuser"
   ```

The API will be available at `http://localhost:8000`.
- Swagger API Page: http://localhost:8000/api/docs
- Admin Page (optional): http://localhost:8000/admin

## Deployment

This project is deployment-ready with Docker and GitHub Actions configured for CI/CD.

### Deployment Steps


1.**Set .env**
  Create your own `.env` 
  ```shell
  cp .env.sample .env
  ```
2. **Build Docker Images**
   Ensure Docker is set up on your deployment server and build the images:

   ```bash
   docker-compose -f docker-compose-deploy.yml build
   ```

4. **Run Containers**
   Start the application in detached mode:

   ```bash
   docker-compose -f docker-compose-deploy.yml up -d
   ```

4. **Create a Superuser** (optional)

   ```bash
   docker-compose run --rm app sh -c "python manage.py createsuperuser"
   ```

The API will be available at `http://your_DJANGO_ALLOWED_HOSTS:8000`.
- Swagger API Page: http://your_DJANGO_ALLOWED_HOSTS:8000/api/docs
- Admin Page (optional): http://your_DJANGO_ALLOWED_HOSTS:8000/admin


