# JENKINSonDOCKER
5/10/2023
THIS PROJECT I USE Vagrantfile TO CREATE AN ubuntu/focal64, INSTALL DOCKER AND USE DOCKER TO CREAT AND RUN JENKINS ON LOCALHOST:8080
************************************************************************************************************************************
Automate Your Deployment: Learn CICD using Jenkins, Github Webhooks & Deploy on Nginx/Apache


create a ubuntu/focal64 vagrantfile .
create a folder "Jenkins" enter folder  "cd Jenkins" 
 craete a folder file "vagrant init"
 Edit the Vagrantfile copy and paste the shell on your Vagrantfile
-------------------------------------------------------------------------------
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2024"
	vb.cpus = 2
  end
  config.ssh.insert_key = false
end
-----------------------------------------------------------------------
"vagrant up" > to start up your ubuntu/focal64 & OS
-----------------------------------------------------
"vagrant ssh" >to ssh to your ubuntu/focal64 & OS
---------------------------------------------------
" sudo apt-get update -y" > to update your ubuntu/focal64 & OS
---------------------------------------------------------------
"sudo apt install docker.io" > install docker 
----------------------------------------------
"sudo docker pull jenkins/jenkins:lts-jdk11" > pull jenkins image
------------------------------------------------------------------
"sudo docker image" to check your jenkins image 
------------------------------------------------
run this command below to run your docker image on port 8080
-------------------------------------------------------------
"docker run -d -v jenkins_home:/var/jenkins_home -p 8080:8080 -p 50000:50000 --restart=on-failure jenkins/jenkins:lts-jdk11"
----------------------------------------------------------------------------------------------------------------------------
you will get a code like this d5b8480fc37a4c1aa6f8a766a456dr6f copy it or type docker exec -u root -it 1596f3a90114 /bin/bash
------------------------------------------------------------------------------------------------------------------------------
cat /var/jenkins_home/secrets/initialAdminPassword you will get the same code copy it and exit
----------------------------------------------------------------------------------------------
go to your browers type localhost:8080 
----------------------------------------
copy and paste the the code d5b8480fc37a4c1aa6f8a766a456dr6f to the password space click on contiune 
-----------------------------------------------------------------------------------------------------
click on Install suggested plugins for jenkins
---------------------------------------------
Then Create First Admin User

Username

Password

Confirm password

Full name

click on save and continue 

Jenkins is ready!

Your Jenkins setup is complete.
***************************************************************************************************************************************
IN THIS PROJECT I USE Vagrantfile TO CREATE AN ubuntu/focal64, INSTALL DOCKER AND USE DOCKER TO CREAT AND RUN JENKINS ON LOCALHOST:8080
---------
5/10/2023


