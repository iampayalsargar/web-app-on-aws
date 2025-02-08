🚀 Web Application Deployment on AWS EC2 with Load Balancer

This project demonstrates how to deploy a highly available web application on AWS using EC2, Elastic Load Balancer (ALB), and Auto Scaling.

🌟 Features

Hosted on AWS EC2

Load balancing using Application Load Balancer (ALB)

Auto Scaling for high availability

Apache Web Server configuration

📂 Project Structure

/var/www/html
├── index.html  # Main webpage
├── app/        # Web app files
├── scripts/    # Deployment scripts
├── README.md   # Project documentation

🛠 Setup Instructions

1️⃣ Launch an EC2 Instance

Choose Amazon Linux 2 as the AMI.

Select instance type (t2.micro for free tier).

Configure security group to allow HTTP (Port 80) and SSH (Port 22).

Attach an IAM Role with S3 and EC2 permissions (if required).

2️⃣ Install Apache Web Server

Run the following commands:

sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

3️⃣ Deploy Web Application Files

Upload your website files to /var/www/html/:

echo "<h1>Welcome to My Web Application</h1>" | sudo tee /var/www/html/index.html

4️⃣ Configure Load Balancer (ALB)

Go to AWS EC2 Dashboard → Load Balancers → Create Load Balancer.

Choose Application Load Balancer (ALB).

Add a Target Group and register your EC2 instance.

Set Health Check Path to /index.html.

Attach the load balancer to your Auto Scaling Group.

5️⃣ Set Up Auto Scaling

Create an Auto Scaling Group with min 2, max 5 instances.

Attach to the target group of ALB.

Define scaling policies based on CPU utilization.

📌 Deployment URL

🌍 Live Application: WebServer-ALB-779120408.us-east-1.elb.amazonaws.com

📜 License

This project is licensed under the MIT License.

📧 Contact

If you have any questions, reach out to me on LinkedIn.

