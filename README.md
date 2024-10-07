# DevOps-Final-Project

### **Step 1: Linux**

1. **What is Linux?**
   - Explain Linux as an open-source operating system widely used in DevOps for server management.

2. **Directory Structure:**
   - `/` - Root directory
   - `/bin` - Essential command binaries
   - `/etc` - Configuration files
   - `/home` - Home directories for users
   - `/var` - Variable files such as logs

3. **How to Install Packages:**
   - Use `apt-get` or `yum` to install packages:
     ```bash
     sudo apt-get install git vim jenkins nginx default-jdk nodejs
     ```
   - For Node.js latest version:
     ```bash
     sudo apt-get install nodejs npm
     ```

4. **How to Uninstall Packages:**
   ```bash
   sudo apt-get remove --purge git vim jenkins nginx default-jdk nodejs
   ```

5. **User Management:**
   - Create a user: `sudo adduser username`
   - Set password: `sudo passwd username`
   - Expire user password: `sudo chage -E 0 username`
   - Delete user & home directory: `sudo deluser --remove-home username`
   - Add user to sudo group: `sudo usermod -aG sudo username`

6. **SSH Configuration:**
   - SSH to another machine: `ssh user@ip_address`
   - Change SSH port from 22 to 8888:
     ```bash
     sudo nano /etc/ssh/sshd_config
     ```
     Change the line `Port 22` to `Port 8888` and restart SSH: `sudo systemctl restart sshd`

7. **Permission Management:**
   - Change file permission: `chmod`
   - Change ownership: `chown`

8. **Check Open Ports:**
   - Use `netstat -tuln` or `ss -tuln` to check open ports.

---

### **Step 2: Git**

1. **What is VCS (Version Control System)?**
   - A system that records changes to files over time. Git is the most widely used VCS.

2. **What is Git?**
   - Git is a distributed VCS used to track changes in code and collaborate with teams.

3. **Git Commands:**
   - **Clone a repository:** `git clone <repo_url>`
   - **Pull latest changes:** `git pull`
   - **Commit changes:** `git commit -m "message"`
   - **Checkout to another branch:** `git checkout <branch>`
   - **Push changes:** `git push`

4. **Difference between Git and GitHub/GitLab/Bitbucket:**
   - Git is a tool; GitHub, GitLab, and Bitbucket are hosting services for Git repositories.

---

### **Step 3: Docker**

1. **Docker Concepts:**
   - **Docker:** A platform to create, deploy, and run applications in containers.
   - **Image:** A lightweight, standalone, executable package.
   - **Container:** A running instance of an image.
   - **Volume:** A mechanism to store data outside of containers.

2. **Basic Docker Commands:**
   - Start Ubuntu container: 
     ```bash
     docker run -it ubuntu
     ```
   - Install JDK, Jenkins, Git, Nginx inside the container:
     ```bash
     apt-get install -y jdk jenkins git nginx
     ```

3. **Create Docker Image from a Running Container:**
   ```bash
   docker commit <container_id> my_custom_image
   ```

4. **Start Container from Image with Port Mapping:**
   ```bash
   docker run -d -p 8080:8080 my_custom_image
   ```

5. **Dockerfile Instructions:**
   - **FROM:** Defines the base image.
   - **RUN:** Executes commands in the container.
   - **WORKDIR:** Sets the working directory inside the container.

6. **Differences:**
   - **COPY vs ADD:** `ADD` has additional features (like unpacking .tar files) while `COPY` only copies files.
   - **CMD vs ENTRYPOINT:** `CMD` provides default arguments to ENTRYPOINT, while `ENTRYPOINT` defines the executable.

---

### **Step 4: Docker Compose**

1. **What is Docker Compose?**
   - A tool for defining and running multi-container Docker applications. It uses a YAML file to configure services.

2. **Features of Docker Compose:**
   - Single configuration file to manage multiple containers.
   - Easy to scale services up or down.

---

### **Step 5: CI/CD**

1. **What is CI/CD?**
   - Continuous Integration (CI) and Continuous Deployment/Delivery (CD) automate code integration and deployment processes.

2. **CI/CD Tools:**
   - Jenkins, GitLab CI, CircleCI, TravisCI.

3. **Jenkins:**
   - A popular CI/CD tool used to automate builds and deployments.

4. **Jenkins Root Path:**
   - Pipelines and configurations are stored in `/var/lib/jenkins`.

---

### **Step 6: Cloud**

1. **What are Clouds?**
   - Cloud platforms provide resources like computing and storage. Examples: AWS, Google Cloud, Microsoft Azure, IBM Cloud.

2. **AWS Concepts:**
   - **EC2:** Virtual server instances.
   - **Security Group:** A virtual firewall.
   - **Keypair:** Used for secure SSH access.
   - **Instance Type:** Defines the hardware (CPU, memory) of EC2.
   - **IAM:** Identity and Access Management for permissions.
   - **S3 Bucket:** Storage for objects.

---

### **Step 7: Configuration Management Tools**

1. **What are Configuration Management Tools?**
   - Tools that automate the management of infrastructure, e.g., Ansible, Chef, Puppet.

2. **Ansible:**
   - A tool for configuration management, it works over SSH.

3. **Inventory File:**
   - A file that defines the hosts and groups for Ansible automation.

---

### **Step 8: Terraform**

1. **What is Infrastructure as Code (IaaC)?**
   - Managing infrastructure through code instead of manual processes.

2. **Terraform:**
   - A popular IaaC tool to define and provision resources.

3. **Terraform Concepts:**
   - **Resources:** The components (e.g., EC2, S3) managed by Terraform.
   - **Providers:** API providers like AWS, Azure, etc.

---

### **Step 9: Networking**

1. **Networking Basics:**
   - **IP Addressing:** Identifies devices on a network.
   - **Public vs Private IP:** Public IP is accessible from the internet, while private IP is limited to internal networks.
   - **Ports:** Logical endpoints for communication.

2. **Testing Connectivity:**
   - Use `ping` or `telnet` to check network connections.

3. **TCP and UDP:**
   - TCP is connection-oriented, while UDP is faster and connectionless.
   - 
