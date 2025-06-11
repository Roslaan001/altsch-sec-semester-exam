# Altschool Second Semester Examination Project

- NAME: Abdulwahab Abdulsomad Olayiwola
- SCHOOL ID: ALT/SOE/024/4646
- TRACK: Cloud Engineering
- SCHOOL: AltSchool Africa
- BATCH: Tinyuka '24

---

## Below is my submission/documentation for my Altschool Second Semester Examination Project

---

## PROJECT OVERVIEW

### The exam entails creating, deploying and configuring HTTPS for a dynamic web application as stated below

- Provisioning a server (Done with AWS Elastic Compute Cloud(EC2))
- Web Server Setup (Done with Nginx (A lightweight Webserver))
- Dynamic Landing Page (Beyond Static HTML) (Done with HTML, Tailwind css for styling and CSS for animations)
- Networking & Security (Production-Ready) (Done by allowing port 80 for HTTP and securing the Let's Encrypt (Certbot))

---

## PROJECT OBJECTIVES

The goal of this project is to provision/create a server, set up a web server, deploy a dynamic landing page and necessary networking settings to make the page publicly accessible. As a cloud engineer, I implored creative ways to do this examination by making use of automation which has tends to reduce manual and much work in tech ecosystem, so therefore using bash scripting makes the project faster for me and less cubersome documentation on the project.

![image description](path/to/your/image.png)

Here is a step by step guide on how I completed the project.

### Step 1: Creating my dynamic landing page

 1. I created my landing page and tested it in my local environment before pushing to Github and making it production ready.

I created four files

- __index.html__: To serve my webpage content, an embedded tailwind for styling the webpage and an inline javascript for changing the color of the webpage when it is being refreshed.

- __style.css__: My CSS codes that contains the styling and animations of the webpage.

- __app.js__:A Node.js application that serves web content and acts as the backend server that Nginx (configured as a reverse-proxy) forwards requests to.

- __automated-deployment.sh__ : A bash script code that automated the update and upgrade of the ec2 server, installation of nginx, cloning the code from GitHub, deploying and hosting of the web server and installation of certbot which is used for securing the web app with HTTPS.

---

### Step 2: Provisioning/Creating a server with AWS EC2

1. Choosing a cloud provider:

    - I chose AWS as my cloud provider

2. Having an account with AWS already, I logged in to my console, search for EC2 in the search bar in the console then click on "launch instances" then I followed these steps:

- Name and Tags
    - __Name__ : Altsch-sec-semester-exam

- Application and OS Images (Amazon Machine Image)
    - __AMI__: Ubuntu Server 24.04 LTS (HVM), SSD Volume Type

- Instance Type
    - __instance type__:t2.micro


- Key Pair (login)
    - I created a new key pair with the name (altschool)
        - __Key pair name__: altschool.pem

- Network Settings
    - __VPC__: Default VPC
    - __Subnet__: Default Subnet in any availability zone
    - __Auto-assign public IP__: Enable
    - Firewall (security groups)
        - I configured both the http and https to save time
        - I also allow ssh traffic from only my PC address for security wiseness
        -

- Under the advanced details section, there is a section called User Data, (picture shown below)