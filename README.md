# Documenting My Experience with Setting Up an NGINX Web Server

## Introduction
In this blog post, I document my journey of setting up an NGINX web server to host a static website with a custom HTML page. The task involved deploying a server, installing NGINX, configuring it to serve a custom message, and ensuring accessibility via a public IP address. Here's a breakdown of my process and reflections.

---

## Approach to Completing the Task

### Choosing the Cloud Platform
I selected **Microsoft Azure** for its seamless integration with tools I already use. I launched an **Ubuntu-based Azure Virtual Machine (VM)** to serve as the foundation for the web server.

### Installing NGINX
NGINX was chosen for its **speed, stability, and feature-rich ecosystem**. I installed it using the following commands:

```bash
sudo apt update
sudo apt install nginx
```

After installation, I started and enabled NGINX to run on boot:

```bash
sudo systemctl start nginx
sudo systemctl enable nginx
```

To verify the service status:

```bash
sudo systemctl status nginx
```

At this stage, visiting the server’s **public IP** in a browser displayed the default NGINX welcome page.

### Creating a Custom HTML Page
I replaced the default `index.html` file in `/var/www/html/` with a custom page. Here's the HTML code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DevOps Stage 0</title>
</head>
<body>
  <h1>Welcome to DevOps Stage 0 - Siphe Godloza / Psyfe</h1>
</body>
</html>
```

After saving the file, refreshing the browser confirmed that the **custom message was live** at `http://<server-ip>/`.

---

## Challenges Faced and Solutions

### Firewall Configuration
The **Azure VM’s Network Security Group (NSG)** initially blocked **HTTP traffic**. I resolved this by allowing inbound traffic on **port 80**.

### File Permission Issues
The default `index.html` was **owned by root**, causing permission errors. I updated ownership and permissions with:

```bash
sudo chown ubuntu:ubuntu /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html
```

### NGINX Configuration
I **double-checked the server block configuration** to ensure files were served from `/var/www/html/`. No changes were needed—the default setup worked perfectly.

---

## Learning and Professional Growth
This task deepened my understanding of:

- **Cloud Infrastructure**: Hands-on experience with **Azure VM deployment**.
- **Web Server Management**: Configuring **NGINX** and troubleshooting issues.
- **Security Best Practices**: Managing **firewall rules** and **file permissions**.

These skills align with my goal to specialize in **DevOps and Cloud Engineering**, where **infrastructure automation** and **server management** are critical. For those interested in this field, explore roles like **Cloud Engineers** or **DevOps Engineers** to dive deeper.

---

## Conclusion
Setting up **NGINX on Azure** taught me the importance of **attention to detail** in **server configuration, firewall management, and permissions**. It reinforced foundational **DevOps concepts** and highlighted the value of **troubleshooting** in real-world scenarios.

For aspiring engineers, **mastering these basics is crucial**. Whether you're deploying a **simple static site** or **scaling complex applications**, the principles remain the same—**plan carefully, test thoroughly, and iterate confidently**.

---

## References
- **DevOps Engineers**
- **Cloud Engineers**

