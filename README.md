![Logo](https://camo.githubusercontent.com/f950a0dd055fe96a89dbeabdb2a39f941b85db5d/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6361726c6f736d6172742e636f2f6772617068656e652d6c6f676f2e706e67)

# Django/GraphQL tutorial

Graphene Django has a number of additional features that are designed to make working with Django easy. Our primary focus in this tutorial is to give a good understanding of how to connect models from Django ORM to graphene object types.

## Table of Contents

- [Setting up the project](#setting-up-the-project)
- [Setting up the project with Docker](#setting-up-the-project-with-docker)
- [Cleaning up the Container and Image](#cleaning-up-the-container-and-image)
- [Setup](#setup)
- [Inspiration](#inspiration)
- [Contact](#contact)


## Setting up the project

  Start by cloning the project with the command:
  ```
  $ git clone https://github.com/rmiyazaki6499/graphql_django_tutorial.git
  ```
  
  ## Setting up the project with Docker

  For those that are not interested in setting up the project manually or would simply not have to worry about downloading node.js and its dependencies, I have created a Dockerfile and docker-compose.yml file to help create a container with everything you would need to run the **project**.

  ### Install Docker

  To make this as easy as possible, we will be using *Docker Compose* to creat our container.

  - If you do not have Docker yet, start by downloading it here if you are on a Mac or Windows:
  https://www.docker.com/products/docker-desktop

  - Or if you are on a Linux Distribution follow the directions here:
  https://docs.docker.com/compose/install/

  - To confirm you have Docker Compose, open up your terminal and run the command below:

  ```
  $ docker-compose --version
  docker-compose version 1.26.2, build eefe0d31
  ```
  
  - Go into the project directory to build and run the container with:

  ```
  $ cd dja_vue_gql/
  $ docker-compose up -d --build
  ```

  **This may take a few moments**
  
  Navigate to http://localhost:8000/graphql to view the site on the local server.
  
  This will show you the GraphiQL interface that should look like this:
  
  

An example Query which returns all names and ids for ingredients might look like this:
```
query {
  allIngredients {
    edges {
      node {
        id,
        name
      }
    }
  }
}
```
  
  ### Cleaning up the Container and Image

  - To stop the container from running, use `<Ctrl-C>` twice.
  - To close down the container use the command:

  ```
  $ docker-compose down
  ```
  - Then to clean up the container and image which we are no longer using use the command:

  ```
  $ docker system prune -fa
  ```

  - Confirm that the container and image is no longer there with:

  ```
  $ docker system df -v
  ```

## Setting up the project manually

After cloning the project:
```
# Creating the virtual environment
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt

# Running the server
python3 manage.py runserver
```
Once the server is running, go to:
localhost:8000/graphql/

This will show you the GraphiQL interface. 

An example Query which returns all names and ids for ingredients might look like this:
```
query {
  allIngredients {
    edges {
      node {
        id,
        name
      }
    }
  }
}
```


## Inspiration

Graphene-Python
https://docs.graphene-python.org/projects/django/en/latest/tutorial-plain/

## Contact

[Ryuichi Miyazaki](https://github.com/rmiyazaki6499)
