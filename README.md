

## **Ansible Role Project**

```markdown
# Simple Web App Deployment using Ansible and Nginx

This project demonstrates how to deploy a simple web application using **Ansible** and **Nginx**. The project includes:
- Ansible roles to install and configure Nginx.
- Deployment of a static HTML file (`index.html`) to the web server.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Prerequisites](#prerequisites)
3. [Project Structure](#project-structure)
4. [How to Use](#how-to-use)
5. [Contributing](#contributing)
6. [License](#license)

---

## Project Overview

This project automates the deployment of a simple web application using:
- **Nginx**: A high-performance web server.
- **Ansible**: A powerful automation tool for configuration management and deployment.

The project includes:
- Ansible roles to install and configure Nginx.
- Deployment of a static HTML file (`index.html`) to the web server.

---

## Prerequisites

Before using this project, ensure you have the following installed:

1. **Ansible**: Install Ansible on your control machine.
   ```bash
   sudo apt update
   sudo apt install ansible -y
   ```

2. **SSH Access**: Ensure you have SSH access to the target servers.

3. **Inventory File**: Update the `dev-inventory` file with your server details.

---

## Project Structure

The project has the following structure:

```
simple-web-app-deploy/
  roles/
    nginx/
      tasks/
        main.yml
      handlers/
        main.yml
    deploy/
      tasks/
        main.yml
      files/
        index.html
  playbook.yml
  dev-inventory
  README.md
```

### Key Files:
- **`roles/nginx/`**: Role to install and configure Nginx.
- **`roles/deploy/`**: Role to deploy the `index.html` file.
- **`playbook.yml`**: Main playbook to execute the roles.
- **`dev-inventory`**: Inventory file containing server details.
- **`index.html`**: Static HTML file for the web application.

---

## How to Use

Follow these steps to deploy the web application:

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/your-username/simple-web-app-deploy.git
cd simple-web-app-deploy
```

### 2. Update the Inventory File
Edit the `dev-inventory` file and add your server details:
```ini
[servers]
dev_1 ansible_host=52.23.197.166

[servers:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/.ssh/ansible-roles-key.pem
```

### 3. Run the Playbook
Execute the playbook to deploy the web application:
```bash
ansible-playbook -i dev-inventory playbook.yml
```

### 4. Verify the Deployment
1. Check if Nginx is running:
   ```bash
   systemctl status nginx
   ```

2. Access the web application in your browser:
   ```
   http://<your-server-ip>
   ```

---

## Contributing

Contributions are welcome! If you'd like to contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bugfix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add your commit message here"
   ```
4. Push your changes to the branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request and describe your changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
```
- [Ansible Documentation](https://docs.ansible.com/)
- [Nginx Documentation](https://nginx.org/en/docs/)
```

