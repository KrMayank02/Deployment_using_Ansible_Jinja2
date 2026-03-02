# Deployment of Web Application Using Ansible and Jinja2 Template

**Objective:** To create an automation script to deploy a Web Application using Ansible and Jinja2 template.

**Real-time scenario:**

You have joined as a DevOps engineer in XYZ Pvt. Ltd. It is a platform where individuals can create their profile and start blogging on various topics. The
application is ready to be hosted on a server. You are tasked with implementing an Ansible script to deploy this application on a remote Nginx server.

**High-Level-Tasks:**

1. Create an inventory file to define the remote server(s)

2. Write a YAML playbook with tasks for installing Nginx, copying web application files, deploying the Nginx configuration, and enabling the site

3. Create a directory for templates and a Jinja2 template for the Nginx configuration

4. Define variables in the playbook for application details and Nginx configuration

5. Include tasks in the playbook for installing Nginx, copying application files, deploying Nginx configuration, and enabling the Nginx site

6. Execute the playbook to deploy the web application on the remote server

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Project Implementation Steps:**

**Step 1:** Write a YAML playbook with tasks for installing Nginx.

sudo su -

vim playbook.yml

-----------------------------------------------------------------------------------------------------------------------------------

<img width="950" height="419" alt="image" src="https://github.com/user-attachments/assets/4a3fd2f0-ccde-4721-85f6-fcb12785c0d3" />

-----------------------------------------------------------------------------------------------------------------------------------

Save and run the playbook

apt-get update

ansible-playbook playbook.yml

<img width="964" height="299" alt="image" src="https://github.com/user-attachments/assets/5f5fa386-b43f-4aa3-9cb8-42f126ab0e7c" />


-----------------------------------------------------------------------------------------------------------------------------------

**Step 2:** Update the nginx configuration using Jinja2 template

 cp /etc/nginx/sites-available/default .

 mv default default.j2 

 vim default.j2

 Update port 80 with a variable {{ http_port }} , Save the file as shown below:

 <img width="975" height="407" alt="image" src="https://github.com/user-attachments/assets/47aebda0-089e-4fd9-be18-f80dbfca9bfa" />

 -----------------------------------------------------------------------------------------------------------------------------------

 







