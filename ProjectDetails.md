# CICD Project Details

## **Project Summary**

In this project, you will take a newly developed full stack application and deploy it to a cloud service provider so that it is available to customers. This application contains the main components of a 3-tier full stack application (**UI**, **API**, and **Database**).

You will have to do the following:

- Configure the services and infrastructure on AWS
- Create scripts to deploy each component of the application
- Create and document an automated pipeline using CircleCI

You will have the choice of using either a starter project (**[GitHub link](https://github.com/udacity/nd0067-c4-deployment-process-project-starter)**) or the application created during the course of the Fullstack JavaScript Nanodegree.

# Hosting a Full-Stack Application

### **You can use you own project completed in previous courses or use the provided Udagram app for completing this final project.**

---

In this project you will learn how to take a newly developed Full-Stack application built for a retailer and deploy it to a cloud service provider so that it is available to customers. You will use the aws console to start and configure the services the application needs such as a database to store product information and a web server allowing the site to be discovered by potential customers. You will modify your package.json scripts and replace hard coded secrets with environment variables in your code.

After the initial setup, you will learn to interact with the services you started on aws and will deploy manually the application a first time to it. As you get more familiar with the services and interact with them through a CLI, you will gradually understand all the moving parts.

You will then register for a free account on CircleCi and connect your Github account to it. Based on the manual steps used to deploy the app, you will write a config.yml file that will make the process reproducible in CircleCi. You will set up the process to be executed automatically based when code is pushed on the main Github branch.

The project will also include writing documentation and runbooks covering the operations of the deployment process. Those runbooks will serve as a way to communicate with future developers and anybody involved in diagnosing outages of the Full-Stack application.

# **Project Environment**

## **Local Machine Instructions**

Ensure you have the following installed:

- **Node** v14.15.1 (LTS), or more recent. While older versions can work, it is advisable to keep Node to the latest LTS version
- **npm** 6.14.8 (LTS), or more recent. Yarn can work but was not tested for this project
- **AWS** CLI v2, v1 can work but was not tested for this project

## **Workspace Instructions**

### **Using the Udagram starter code**

A workspace has been set up for you with the necessary tools and the Udagram starter application. If you plan to use Udagram, make sure to connect this folder to a GitHub repository.

**Be sure to confirm that your project runs locally before you try to deploy the app.**

### **Uploading your own code**

You can also host your own application to complete this project. If you choose to do so, do the following:

- Host your code on a GitHub Repository.
- Connect your GitHub account to the workspace.
- Clone locally the GitHub repo on the workspace.

Alternatively, follow these steps to upload your code into the workspace:

- Zip any folder you want to use as you cannot upload a complete folder into the workspace
- Upload your Zip file and unzip it. You can use the `unzip <archivenamehere>` command.
- Modify your `package.json` start command to reflect the one you see in the starter code. This will be necessary in order to connect to the preview.
- Once you start your app from a CLI, click this open app button.

**NB: You will need to list** `@angular/cli` **as a devDependency in your project if it's not already done. The angular will be needed in your pipeline eventually.**

**Be sure to confirm that your project runs locally before you try to deploy the app.**

# **Project Instructions**

## **Submission Instructions**

- Provide the link to your hosted working Front-End Application in the README
- Include a screenshot of your last build in CircleCi (either include screenshots in the GitHub repo or upload into the Workspace)
- Include screenshots of the configuration page of your AWS services (either include screenshots in the GitHub repo or upload them into the Workspace)

## **Instructions Summary**

In order to complete the project you will need to do the following:

- Provision the necessary AWS services your app needs
- Deploy your application to those services
- Connect your GitHub repo to CircleCI
- Configure a CircleCI pipeline to automate your deployments
- Document the infrastructure needs (RDS, S3 Elastic Beanstalk, etc) and explain the different steps in the pipeline
- Create architecture diagrams for an overview of the infrastructure and the pipeline

Your project final project should include the following files and folders:

- .circleci/config.yml
- a root level package.json
- a Readme with some basic documentation
- a docs folder to include architecture diagram and more detailed documentation files (MD format) on infrastructure description, app dependencies, and pipeline process

### **Suggestions to Make Your Project Stand Out!**

- Make your pipeline run the front-end unit tests! You will need to figure out how to run mocha in a CI env
- Make Pull Requests builds so that each time you open a pull request against the main branch, your tests and build are executed.
- Make separate environments for staging and production in elastic beanstalk and s3. Deploy PR code to the staging and Main to Production.

To review the detailed requirements for the project, look at the **[project rubric](https://review.udacity.com/#!/rubrics/3070/view)**.

## **Ensure you have a working production environment if using Udagram.**

- Check if the API can connect to the Database
- Check if the Front-end can connect to the API
- Check if you can create a user from the production Front-end

## **Udagram is not working locally or in the workspace.**

- Ensure you installed dependencies in all folders.
- Did you add the connection strings of the database?
- Are both applications started in different windows?
- Double-check your Node version.

## **I can't build Udagram.**

- Can the build work locally?
- Are you using the proper Node version?

## **The app can't connect to the database.**

- Are you using the proper SQL version (Postgres if using Udagram)?
- Is your port open in the VPC on AWS?
- Did you make the RDS database public?
- Did you set the right password in your application?

## **I can't access the deployed Udagram Front-End.**

- Did you configure your S3 bucket for web hosting?
- Are you setting the proper index and error files in the S3 web hosting configuration?
- Are the static files well uploaded to S3?

## **I can't access the API in Elastic Beanstalk (EB).**

- Have you set the `env` variables in your environment?
- Try checking the logs of the environment to diagnose the issues. Add more logging to your application if the logs don't help you.
- Ensure your database is accessible.

## **I can't use the AWS or EB CLI from the CircleCi Pipeline.**

- Are you using the available CircleCi Orbs to install Node, AWS, and EB?
- Are your credentials well added to CircleCi?

## **CircleCI won't run my Pipeline file.**

- Is the yml indentation respected?
- Try editing the file directly in CircleCi to see if you are following all the proper syntax.

## **I can't connect my Github account to the workspace.**

- This **[documentation](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh)** should help.

Let's learn how to create a bucket in **[Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html)**, and view a few properties of an existing bucket.

## **Create a Bucket**

1. Navigate to the **[S3 dashboard](https://classroom.udacity.com/nanodegrees/nd0067-fwd-t3/parts/cd0295/modules/d74dd3e2-01b4-4bab-a4da-7e9a3843221b/lessons/4e482900-3dba-4ba3-8e45-31e29494eacc/concepts/console.aws.amazon.com/s3/home)**, and click on the **Create bucket** button. It will launch a new wizard.

![https://video.udacity-data.com/topher/2020/November/5fbe37ba_screenshot-2020-11-25-at-4.06.17-pm/screenshot-2020-11-25-at-4.06.17-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe37ba_screenshot-2020-11-25-at-4.06.17-pm/screenshot-2020-11-25-at-4.06.17-pm.png)

S3 service → Buckets dashboard.View all of the S3 buckets in your account*(S3 is a global service, not a region-specific).*

We create a bucket first, and later we upload files and folders to it.

1. **General configuration**Provide the bucket-name and the region where you want to locate the bucket. The bucket name must be unique worldwide, and must not contain spaces or uppercase letters.

![https://video.udacity-data.com/topher/2020/November/5fbe3a31_screenshot-2020-11-25-at-4.07.11-pm/screenshot-2020-11-25-at-4.07.11-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3a31_screenshot-2020-11-25-at-4.07.11-pm/screenshot-2020-11-25-at-4.07.11-pm.png)

Create a bucket - Provide general details

1. **Public Access settings**You can choose public visibility. Let's uncheck the *Block all public access* option.

![https://video.udacity-data.com/topher/2020/November/5fbe3a6e_screenshot-2020-11-25-at-4.07.33-pm/screenshot-2020-11-25-at-4.07.33-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3a6e_screenshot-2020-11-25-at-4.07.33-pm/screenshot-2020-11-25-at-4.07.33-pm.png)

Create a bucket - Make it public

1. **Bucket Versioning and Encryption**
    ◦ Bucket Versioning - Keep it disabled.
    ◦ Encryption - If enabled, it will encrypt the files being stored in the bucket.
    ◦ Object Lock - If enables, it will prevent the files in the bucket from being deleted or modified.

![https://video.udacity-data.com/topher/2020/November/5fbe3aab_screenshot-2020-11-25-at-4.07.54-pm/screenshot-2020-11-25-at-4.07.54-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3aab_screenshot-2020-11-25-at-4.07.54-pm/screenshot-2020-11-25-at-4.07.54-pm.png)

Create a bucket - Provide additional details

In the snapshots above, we have created a public bucket. Let's see **how to upload files and folders to the bucket**, and configure additional settings.

## **Upload File/Folders to the Bucket**

From the **[S3 dashboard](https://classroom.udacity.com/nanodegrees/nd0067-fwd-t3/parts/cd0295/modules/d74dd3e2-01b4-4bab-a4da-7e9a3843221b/lessons/4e482900-3dba-4ba3-8e45-31e29494eacc/concepts/console.aws.amazon.com/s3/home)**, click on the name of the bucket you have created in the step above.

![https://video.udacity-data.com/topher/2020/November/5fbe3ad2_screenshot-2020-11-25-at-4.12.35-pm/screenshot-2020-11-25-at-4.12.35-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3ad2_screenshot-2020-11-25-at-4.12.35-pm/screenshot-2020-11-25-at-4.12.35-pm.png)

Details of an existing bucket. Upload files/folders to this bucket.

In the snapshot above, it shows that the bucket is in the Region: `US East (Ohio) us-east-2`, and it has a unique Amazon resource name (ARN): `arn:aws:s3:::mtvbucket`. You can view more details of the bucket, in the tabs next to the bucket overview: **Objects, Properties, Permissions, Metrics, Management,** and **Access points**. Leet's upload a sample file to the bucket:

1. Click on the **Upload** button to upload files and folders into the current bucket. In the snapshot below, we have uploaded a **Sample.txt** file.

![https://video.udacity-data.com/topher/2020/November/5fbe3e6d_screenshot-2020-11-25-at-4.52.03-pm/screenshot-2020-11-25-at-4.52.03-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3e6d_screenshot-2020-11-25-at-4.52.03-pm/screenshot-2020-11-25-at-4.52.03-pm.png)

A sample file in the bucket

1. Click on the file name to view the file-specific details, as shown below.

![https://video.udacity-data.com/topher/2020/November/5fbe3ec1_screenshot-2020-11-25-at-4.53.35-pm/screenshot-2020-11-25-at-4.53.35-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe3ec1_screenshot-2020-11-25-at-4.53.35-pm/screenshot-2020-11-25-at-4.53.35-pm.png)

Details of an individual file (object)

## **Details of an Existing Bucket**

### **1. Properties**

There are several properties that you can set for S3 buckets, such as:

- Bucket Versioning - Allows you to keep multiple versions of an object in the same bucket.
- Static website hosting - Mark if the bucket is used to host a website. S3 is a very cost-effective and cheap solution for serving up static web content.
- Requester pays - Make the requester pays for requests and data transfer costs.
- Server access logging - Log requests for access to your bucket.
- **Permissions**

It shows who has access to the S3 bucket, and who has access to the data within the bucket. In the example snapshots above, the bucket is public, meaning anyone can access it. Here, we can write an access policy (in JSON format) to provides access to the objects stored in the bucket.

### **2. Metrics**

View the metrics for usage, request, and data transfer activity within your bucket, such as, total bucket size, total number of objects, and storage class analysis.

### **3. Management**

It allows you to create life cycle rules to help manage your objects. It includes rules such as transitioning objects to another storage class, archiving them, or deleting them after a specified period of time.

### **4. Access points**

Here, you can create access endpoints for sharing the bucket at scale. Using an endpoint, you can perform all regular operations on the bucket.

According to AWS:

> Amazon RDS is a relational database service that manages common database administration tasks, resizes automatically, and is cost-friendly.
> 

Let's see how to create a PostgresSQL database, and view the details of an existing database.

## **A. RDS Dashboard**

Navigate to the **[RDS dashboard](https://console.aws.amazon.com/rds/home)**. It shows the database-resources summary, such as the count of database instances, the health of the database service, reserved instances, snapshots. You can also view the portion of the allocated storage. You can launch the **Create database** wizard from here.

![https://video.udacity-data.com/topher/2020/November/5fbe80f9_screenshot-2020-11-25-at-8.43.57-pm/screenshot-2020-11-25-at-8.43.57-pm.png](https://video.udacity-data.com/topher/2020/November/5fbe80f9_screenshot-2020-11-25-at-8.43.57-pm/screenshot-2020-11-25-at-8.43.57-pm.png)

Snapshot: RDS dashboard

## **B. Create a Database**

AWS provides two options to choose from:

1. **Standard create** - You have set all of the configuration options, including ones for availability, security, backups, and maintenance.
2. **Easy create** - You use the industry best-practice configurations. All configuration options, except the Encryption and VPC details, can be changed after the database is created.

The snapshot below shows the fields you choose while creating a PostgreSQL database using the **Standard create** option.

![https://video.udacity-data.com/topher/2021/December/61adb3d0_create-rds-1/create-rds-1.png](https://video.udacity-data.com/topher/2021/December/61adb3d0_create-rds-1/create-rds-1.png)

Snapshot: Create a database - Choose the *Standard create* option and *Dev/Test* template

![https://video.udacity-data.com/topher/2021/December/61adb40a_create-rds-2/create-rds-2.png](https://video.udacity-data.com/topher/2021/December/61adb40a_create-rds-2/create-rds-2.png)

Snapshot: Choose a Single DB Instance and Credentials Settings

Use either the **RDS Free Tier** or **Dev/Test** template. On free-tier resources, you can develop and test applications to gain hands-on experience with Amazon RDS.
The password can either be auto-generated or manually created. Take note of this password, as it is useful for future steps. You will be able to find this password and change it later in the console.

![https://video.udacity-data.com/topher/2021/December/61adb457_create-rds-3/create-rds-3.png](https://video.udacity-data.com/topher/2021/December/61adb457_create-rds-3/create-rds-3.png)

Select *db.t3.micro*

![Untitled](CICD%20Project%20Details%206028885fc9874db7938484e602764143/Untitled.png)

Snapshot: Create a database - View default settings

Notice that all configuration settings, except the Encryption and VPC details, can be changed after the database is created.

## **C. Details of an Existing Database**

We have created a sample `database-1` to explain the information you can view at the Databases dashboard.

![https://video.udacity-data.com/topher/2021/January/5ff8d0f8_list-of-dbs/list-of-dbs.png](https://video.udacity-data.com/topher/2021/January/5ff8d0f8_list-of-dbs/list-of-dbs.png)

Snapshot: A sample `database-1`.

For each database in the list above, you can see the Region and availability zone it's running in, the size, and the status that it's up and running. You can also see the percentage utilization of the underlying CPU.

![https://video.udacity-data.com/topher/2021/January/5ff8d195_connectivity-and-security/connectivity-and-security.png](https://video.udacity-data.com/topher/2021/January/5ff8d195_connectivity-and-security/connectivity-and-security.png)

Snapshot: *Connectivity & security* details of the selected database

1. *Connectivity & security* - View the *endpoint URL* in the snapshot above. In order to see the data stored in this database, because it's PostgresSQL, you can use a tool like **[Postbird](https://github.com/Paxa/postbird)**. You will need to know the endpoint URL in order to connect directly to this database. In addition, you can view information about networking, the security groups that it's a part of, and replication information.
1. *Monitoring* - It shows several useful metrics about the status of your database, such as CPU utilization percentage, the number of connections, the free storage space, etc.
1. *Logs & events* - It shows useful events. For example, it shows the timestamp when the database was created, when the last backup occurred, etc.
1. *Configuration* - It shows more high-level information, like the ARN number, DB instance configurations, engine version, creation time, the master username, and other similar details.
1. *Maintenance & backups* - It shows any snapshots recently created. Note that the snapshots are taken automatically but you do have the option to configure it.

## Project Submission

After completing the hosting and pipeline for your project, be sure to include the following in your workspace:

- Provide the link to your hosted working Front-End Application in the README.
- Include a screenshot of your last build in CircleCi (either include screenshots in the GitHub repo or upload into the workspace).
- Include screenshots of the configuration page of your AWS services (either include screenshots in the GitHub repo or upload them into the workspace).
- Store screenshots inside a screenshot folder at the root folder of the workspace.

To review the detailed requirements for the project, look at the **[project rubric](https://review.udacity.com/#!/rubrics/3070/view)**.