# Apache Playbook

This Ansible playbook is used to set up an Apache web server on a target host. It installs Apache, ensures the service is running, and deploys a static website.

## Playbook Details

### Tasks

1. **Install Apache httpd**  
   Installs the Apache web server package (`apache2`) on the target host using the `apt` module.

2. **Start Apache Service**  
   Ensures the Apache service is started and enabled to run on boot using the `service` module.

3. **Deploy Static Website**  
   Copies the `index.html` file from the local machine to the Apache web server's document root (`/var/www/html`) with appropriate ownership and permissions.

### File Structure

- `apache-playbook.yml`: The main playbook file.
- `index.html`: The static website file to be deployed.

### Requirements

- Ansible must be installed on the control node.
- The target host must have `apt` package manager (e.g., Ubuntu/Debian-based systems).
- SSH access to the target host with sufficient privileges to install packages and manage services.

### Usage

1. Ensure the `index.html` file is present in the same directory as the playbook.
2. Run the playbook using the following command:

   ```bash
   ansible-playbook -i <inventory_file> apache-playbook.yml