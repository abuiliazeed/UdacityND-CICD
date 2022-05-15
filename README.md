[![CircleCI](https://circleci.com/gh/abuiliazeed/UdacityND-CICD/tree/main.svg?style=svg)](https://circleci.com/gh/abuiliazeed/UdacityND-CICD/tree/main)

# Deployment

## Backend API Endpoint
[Backend API Endpoint Link](http://udagram-api.us-east-1.elasticbeanstalk.com/api/v0)
## Front End
[Front End Deployment Link](http://udacityndbucket.s3-website-us-east-1.amazonaws.com/)

## Infrastructure
### Front End
The front end static files build is hosted on AWS S3 bucket with permissions to read and write in order for the user to upload photos for the posts created.

### Backend
#### Server
The server is hosted on AWS Elastic Beanstalk with node environment.

#### Database
The database is hosted on AWS RDS with PostgreSQL.

#### Architecture Diagram
![AWS Archticture](https://i.imgur.com/ZTrur2t.png "AWS Archticture Diagram")

# CircleCI for CICD
We use CircleCI for Continuous Integration and Continuous Delivery

# Trigger pipeline
Once the developer has pushed the code to the githup repository, we can trigger the pipeline.

## Pipeline Steps
- Installing Backend Environment and Dependencies
- Building Backend
- Deploying Backend to AWS Elastic Beanstalk
- Installing Front End Environment and Dependencies
- building Front End
- Deploying Front End to AWS S3

## Pipeline Diagram
![CICD Pipeline](https://i.imgur.com/Youy4QB.png "CICD Pipeline")


# Udagram App Developer Guide

This application is provided by udacity team in order to run it locally follow this guide

## Getting Started

1. The application consists of two code bases the udagram-api which handle the server and the database connections and the udagram-frontend which handles the front end.
2. Clone this repo locally into the location of your choice.
3. Move the content of the udagram folder at the root of the repository as this will become the main content of the project.
4. Open a terminal and navigate to the root of the repo
5. follow the instructions in the installation step

The project can run but is missing some information to connect to the database and storage service. These will be setup during the course of the project

### Dependencies

```
- Node v14.15.1 (LTS) or more recent. While older versions can work it is advisable to keep node to latest LTS version

- npm 6.14.8 (LTS) or more recent, Yarn can work but was not tested for this project

- AWS CLI v2, v1 can work but was not tested for this project

- A RDS database running Postgres.

- A S3 bucket for hosting uploaded pictures.

```

### Installation

Provision the necessary AWS services needed for running the application:

1. In AWS, provision a publicly available RDS database running Postgres. <Place holder for link to classroom article>
1. In AWS, provision a s3 bucket for hosting the uploaded files. <Place holder for tlink to classroom article>
1. Export the ENV variables needed or use a package like [dotnev](https://www.npmjs.com/package/dotenv)/.
1. From the root of the repo, navigate udagram-api folder `cd starter/udagram-api` to install the node_modules `npm install`. After installation is done start the api in dev mode with `npm run dev`.
1. Without closing the terminal in step 1, navigate to the udagram-frontend `cd starter/udagram-frontend` to intall the node_modules `npm install`. After installation is done start the api in dev mode with `npm run start`.

## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1. `cd starter/udagram-frontend`
1. `npm run test`
1. `npm run e2e`

There are no Unit test on the back-end

### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

