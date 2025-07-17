# 📦 AWS Backup Plan for EC2 and RDS

## 📝 Project Title

**Automated Backup and Recovery Plan for EC2 and RDS Using AWS Backup**

---

## 📘 Introduction

In modern cloud infrastructure, ensuring data protection and recovery is a mission-critical task. This project demonstrates how to implement a centralized and automated backup solution for AWS EC2 and RDS using **AWS Backup**.

The project includes:
- Deploying EC2 and RDS resources
- Creating and configuring a Backup Vault and Backup Plan
- Assigning resources and triggering backup jobs
- Validating backup and recovery point creation

---

## 🎯 Objectives

- Launch an EC2 instance with a sample web server and data.
- Launch an RDS instance with a test database and sample table.
- Set up an AWS Backup Vault and Backup Plan.
- Assign both resources (EC2 and RDS) to the plan.
- Trigger and validate on-demand backups.
- Document the setup, backup jobs, and recovery points.

---

## ⚙️ Technology Stack

| Component       | Technology Used                 |
|-----------------|----------------------------------|
| Compute         | AWS EC2 (Amazon Linux 2)         |
| Database        | AWS RDS (MySQL 8.x)              |
| Web Server      | Apache HTTP Server               |
| Backup Service  | AWS Backup                       |
| CLI & Tools     | Amazon Linux 2, AWS Console, MySQL |
| Networking      | VPC, Security Groups             |

---


---

## ⚙ Implementation Steps

1. **Launch EC2 Instance**
   - Use Amazon Linux 2
   - Install Apache HTTP Server:
     ```bash
     sudo yum update -y
     sudo yum install httpd -y
     sudo systemctl start httpd
     sudo systemctl enable httpd
     echo "<h1>Backup Test Page</h1>" | sudo tee /var/www/html/index.html
     ```

2. **Launch RDS Instance**
   - MySQL engine
   - Create database and table:
     ```sql
     CREATE DATABASE backupdb;
     USE backupdb;
     CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(100),
       email VARCHAR(100)
     );
     INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');
     ```

3. **AWS Backup Setup**
   - Create Backup Vault (e.g., `project-backup-vault`)
   - Create Backup Plan (`ec2-rds-backup-plan`)
     - Frequency: Daily
     - Retention: 7 Days
   - Assign EC2 and RDS via Resource IDs or Tags

4. **Validation**
   - Trigger on-demand backup
   - Check backup jobs and recovery points under AWS Backup console

---

## ✅ Results

- EC2 page successfully deployed and publicly accessible
- RDS table created and populated with test data
- Backup plan active with daily retention policy
- Recovery points generated and stored in AWS Backup Vault

---

## 📸 Suggested Screenshots for Documentation

- EC2 Instance running with sample web page
- RDS database showing table with sample data
- AWS Backup Plan configuration
- Backup Jobs page showing success
- Recovery Points listed in Backup Vault

---

## 📝 Conclusion

This project successfully demonstrates how to configure a centralized backup solution using AWS Backup for both EC2 and RDS resources. By automating daily backups with a 7-day retention policy, we've implemented a reliable and resilient data protection strategy using native AWS services.

---

## 👤 Author

**Nikhil Mandage**  
Cloud & DevOps Intern  
Cravita Technologies
