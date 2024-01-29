# AssessableActivityWAD2023-24
Assessable activity Term 2

## Setting up EC2 Instance on AWS

In this guide, I'll walk you through the steps to create an EC2 instance on AWS. 

1. **Creating a Security Group:**
   - Create a security group named `default-web-sg` with three inbound rules.

2. **Configuring EC2 Instance:**
   - Launch an EC2 instance named `hostel-server-daw` with Ubuntu Server 22.04 AMI (64-bit).
   - Use the `t2.micro` instance type (free tier eligible).
   - Select the key pair "vockey" and choose the existing security group `default-web-sg`.
   - Launch the instance with default storage settings.

3. **SSH Access to EC2 Instance:**
   - Access the public IPv4 DNS of the EC2 instance via SSH.

4. **Installing Services:**
   - Run the following commands to install required services:
     ```bash
     sudo apt-get update
     sudo apt-get install mysql-server php libapache2-mod-php php-mysql
     ```

5. **Downloading and Unzipping Application:**
   - Download the second application using `wget`:
     ```bash
     wget -U "Firefox" "https://phpgurukul.com/?sdm_process_download=1&download_id=7210" -O file.zip
     ```
   - Unzip the file using:
     ```bash
     sudo apt-get install unzip
     unzip file.zip
     ```

6. **Setting Up Application:**
   - Change the folder name to 'hostel' and move it to `/var/www/html/hostelproject`.
   - Adjust folder permissions:
     ```bash
     sudo chown -R www-data /var/www/html/hostelproject/
     ```

7. **Database Setup:**
   - Enter MySQL and make necessary modifications.
   - Execute `hostel.sql` in MySQL.

8. **Configuring VirtualHost:**
   - Create a VirtualHost with the proper values for `ServerName` and `DocumentRoot`.

9. **Enabling and Testing:**
   - Edit the configuration file with the EC2 instance's public IPv4 DNS and the correct Document Root.
   - Enable the new file and disable the default one.
   - Access the application by entering the public IPv4 DNS in the browser, including `/hostel` for correct display.

10. **Elastic IP Setup:**
    - Create an Elastic IP address and associate it with the EC2 instance.
    - Verify the functionality with the Elastic IP.

This completes the setup I made.
