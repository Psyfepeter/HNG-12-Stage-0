# Documenting My Experience with Setting Up NGINX Web Server

In this blog post, I will be documenting my journey of setting up an NGINX web server to host a simple static website with a custom HTML page. The task required me to deploy a server, install NGINX, configure the web server to serve a custom message, and ensure that the website is accessible via a public IP address without ports, all while reflecting on my learning process.

## Approach to Completing the Task

To begin with, I had to choose a cloud platform to host my server. I opted for *Microsoft Azure* because I found it easier to integrate with the tools I had already been using. I launched a simple Azure Virtual Machine (VM) running Ubuntu, which served as the foundation for the web server setup.

The first step was installing NGINX. This is a common web server used for its speed, stability, and rich feature set. I executed the following commands to install NGINX on my Ubuntu server:
 https://hng.tech/hire/azure-devops-engineers
  https://hng.tech/hire/cloud-engineers

```bash
sudo apt update
sudo apt install nginx

After installation, I started the NGINX service and enabled it to run on boot:

sudo systemctl start nginx
sudo systemctl enable nginx

I then checked the status of the NGINX server to ensure it was running without any issues:

sudo systemctl status nginx

At this point, I was able to access the default NGINX page by visiting my server’s public IP address in a browser. The next step was creating a custom HTML page with the message: “Welcome to DevOps Stage 0 - [Siphe Godloza ]/[Psyfe]”.

To do this, I navigated to the default directory for NGINX’s HTML files, which was located at /var/www/html/, and replaced the default index.html file with my custom HTML file:

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DevOps Stage 0</title>
</head>
<body>
  <h1>Welcome to DevOps Stage 0 - Siphe Godloza/Psyfe</h1>
</body>
</html>

Once I saved the file, I ensured that NGINX was serving the correct page by refreshing the browser and checking the custom message on the server’s public IP address. The site was accessible at http://<your-server-ip>/, confirming that the task was complete.

Challenges Faced and Solutions

The task seemed straightforward, but a few challenges arose during the process:
	1.	Firewall Configuration: Initially, I could not access the site from my browser, as the security group attached to the Azure VM did not allow HTTP traffic. To resolve this, I updated the Network Security Group (NSG) to allow incoming traffic on port 80 (HTTP).
	2.	Permission Issues: When trying to modify the index.html file, I faced some permission errors because the file was owned by the root user. To overcome this, I changed the ownership of the file to the ubuntu user and ensured the correct permissions were set using:

sudo chown ubuntu:ubuntu /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html


	3.	Nginx Configuration: For a moment, I wasn’t sure whether NGINX was correctly configured to serve my custom page, but after checking the default server block configuration, I realized everything was already set up to serve files from /var/www/html/.

Learning and Professional Growth

This task was a valuable learning experience. Not only did it reinforce my understanding of how to configure and deploy a web server, but it also introduced me to the concepts of cloud-based infrastructure. It gave me practical experience working with Microsoft Azure, a cloud platform that is essential for DevOps and cloud engineers.

Additionally, configuring the NGINX web server, troubleshooting common issues like firewall settings and file permissions, and ensuring accessibility through a public IP address are all vital skills in the field of site reliability engineering. This experience ties directly into my long-term professional goals of becoming a proficient DevOps or cloud engineer. Understanding server deployment, web server configuration, and handling security settings will allow me to effectively manage infrastructure and automate tasks, which are key aspects of both DevOps and Cloud Engineering.

Conclusion

In conclusion, this task has deepened my understanding of web server configuration, cloud hosting, and troubleshooting. It allowed me to demonstrate problem-solving skills while developing hands-on knowledge of deploying NGINX and managing cloud instances. For those interested in DevOps or cloud infrastructure roles, gaining experience with these foundational tasks is crucial. For further career development in this space, you can explore resources on platforms like Cloud Engineers or DevOps Engineers to learn more about the intricacies of cloud environments and automation.
	•	Cloud Engineers
	•	DevOps Engineers
