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

**Step 3:** Update the playbook with Jina2 template tasks

vim playbook.yml

Enter the code snippet in playbook as shown in below screenshot:

<img width="975" height="517" alt="image" src="https://github.com/user-attachments/assets/cfe5fba3-3654-4d71-9500-c3a98af8c79f" />


Save the playbook and run it.

ansible-playbook playbook.yml


<img width="975" height="367" alt="image" src="https://github.com/user-attachments/assets/f03a0293-3546-4998-86e9-1904ba1e1268" />

------------------------------------------------------------------------------------------------------------------------------------

**Step 4:** Create an HTML code and deploy it on nginx sever

vim index.html,  enter the block of code as shown in below screenshot:

-Save the file.

<img width="975" height="205" alt="image" src="https://github.com/user-attachments/assets/54a6d299-03d8-478f-8f97-3d3d92c7b2fc" />

Update the playbook with the new tasks as shown in below screenshot

vim playbook.yml

<img width="823" height="511" alt="image" src="https://github.com/user-attachments/assets/3eb66b76-7068-4844-bc3c-97d1e660bd3a" />

Save the file and execute the playbook.

ansible-playbook playbook.yml

<img width="975" height="402" alt="image" src="https://github.com/user-attachments/assets/6b8dcfa9-ac42-4712-8998-c53ec5a1562b" />


Now, Copy the public ip of node/host machine.

Paste the URL on the Browser to access the application.

Public-ip: 8282 

http://184.72.90.82:8282/     //Enter this URL on the browser as shown in below screenshot:

---------------------------------------------------------------------------------------------------------------------------------------------

<img width="954" height="487" alt="image" src="https://github.com/user-attachments/assets/ee0eeeff-58f1-402d-970c-53f9d4f082af" />

----------------------------------------------------------------------------------------------------------------------------------------------

**- The Web Application is getting loaded successfully on the browser, hence Project got executed successfully.**

**- The Project demonstrate the deployment of a Web Application using Ansible and Jinja2 template on Nginx server.**

