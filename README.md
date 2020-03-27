![Logo](https://camo.githubusercontent.com/f950a0dd055fe96a89dbeabdb2a39f941b85db5d/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6361726c6f736d6172742e636f2f6772617068656e652d6c6f676f2e706e67)

# Django/GraphQL tutorial

Graphene Django has a number of additional features that are designed to make working with Django easy. Our primary focus in this tutorial is to give a good understanding of how to connect models from Django ORM to graphene object types.

## Table of Contents

- [Motivations](#motivations)
- [General info](#general-info)
- [Setup](#setup)
- [Features](#features)
- [Contact](#contact)


## General info

This project is an intro on integrating GraphQL with Django

## Setup

After cloning the project:
```
# Creating the virtual environment
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt

# Running the server
python3 cookbook/manage.py runserver
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

## Status

Project is: _Under development_

## Inspiration

Graphene-Python
https://docs.graphene-python.org/projects/django/en/latest/tutorial-plain/

## Contact

[Ryuichi Miyazaki](https://github.com/rmiyazaki6499)
