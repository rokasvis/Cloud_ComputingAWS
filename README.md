# What is cloud computing

Cloud computing is the delivery of on-demand computing services -- from applications to storage and processing power -- typically over the internet and on a pay-as-you-go basis.

## How does it work

Rather than owning their own computing infrastructure or data centres, companies can rent access to anything from applications to storage from a cloud service provider.

## What are the benefits

- Business don't to have invest into hardware
- Services can be accessed instantly 
- No maintenace costs
- Services are scalable 

## What is IaaS, PaaS and SaaS

Infrastructure-as-a-Service (IaaS) delivers fundamental compute, network, and storage resources to consumers on-demand, over the internet, and on a pay-as-you-go basis. Using an existing infrastructure on a pay-per-use scheme seems to be an obvious choice for companies saving on the cost of investing to acquire, manage, and maintain an IT infrastructure. 

Platform-as-a-Service (PaaS) provides customers a complete platform—hardware, software, and infrastructure—for developing, running, and managing applications without the cost, complexity, and inflexibility of building and maintaining that platform on-premises. Organizations may turn to PaaS for the same reasons they look to IaaS, while also seeking to increase the speed of development on a ready-to-use platform to deploy applications.

Software-as-a-service (SaaS) is a way of delivering applications over the Internet—as a service. Instead of installing and maintaining software, you simply access it via the Internet, freeing yourself from complex software and hardware management.

SaaS applications are sometimes called Web-based software, on-demand software, or hosted software. Whatever the name, SaaS applications run on a SaaS provider’s servers. The provider manages access to the application, including security, availability, and performance.

## What is AWS

Amazon Web Services (AWS) is the world’s most comprehensive and broadly adopted cloud platform, offering over 200 fully featured services from data centers globally. Millions of customers—including the fastest-growing startups, largest enterprises, and leading government agencies—are using AWS to lower costs, become more agile, and innovate faster.

## Benefits of using AWS

- Comprehensive
- Cost-Effective
- Adaptable
- Secure

# Setting up AWS

## Setting up EC2 instance

https://eu-west-1.console.aws.amazon.com/console/home?region=eu-west-1

Services > EC2 > Instances > Launch Instances 

For this particula app selected Ubuntu 18.04 machine > t2 family > devopsstudent default 1a subnet > enable auto assign public ip > 8GB storage general purpose SSD > create/ select security group openning SSH and HTTP ports


### Coppying APP into AWS

The app that I already had set up on my `localhost` and tested on a virtual vagrant machine needed to be transfered on my AWS instance. To do so I used `git clone` command to tranfer all my files from my github respiratory: https://github.com/rokasvis/vm_devops.git

### Installing dependancies

Once the respiratory is clonned the depenacies need to be set up. All of the dependacies can be found on provisioning file which needed to be executed using following commands:

`$ sudo chmod +x filename.sh` this is to make it executable

`sh filename.sh` to run the file and install all the dependencies

Once `nginx` and the right version of `nodejs` is installed run the following commands: 

`node /app/seeds/seeds.js` 

Change directory to app folder using `cd app`

`npm install`

`npm start`

Should get a following response:

`Your app is ready and listening on port 3000`

### Connect the app to the database

Create a second instance for a database creating security group and adding the ip address of the app server. Once the second instance is launched install all the dependencies that includes installing `mongodb`

`sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20`

`sudo systemctl restart mongod`

`sudo systemctl restart mongod`

ssh to an app machine and create a enviroment variable `DB_HOST`

`export DB_HOST="mongodb://0.0.0.0:27017/posts` (use the address for the database)

App should now be connected to the database

### Creating an AMI

Amazon Machine Image (AMI) provides the information required to launch an instance. You must specify an AMI when you launch an instance.

To create an AMI:

Select an instance > image and templates > create image 

### Cloud Watch, Alarms and SNS

### How to make your app Highly Available and Scalable







