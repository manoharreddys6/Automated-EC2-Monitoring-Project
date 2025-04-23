# 🖥️ Automated EC2 Instance Monitoring using AWS CLI, SNS & Task Scheduler
This project is designed to automate the monitoring of Amazon EC2 instance statuses using AWS Command Line Interface (CLI) on a Windows machine. It simulates a real-world scenario where a website or application is hosted on EC2, and consistent health checks are crucial for maintaining uptime and availability.

The core idea behind the project is to fetch the status of all EC2 instances in a specific region (like ap-south-1 for Mumbai), log the status information to a file, and then notify the user daily through an email or AWS SNS (Simple Notification Service) alert. This creates a proactive monitoring system without requiring manual effort.

Key Features:
EC2 Instance Status Check: Uses AWS CLI to fetch InstanceId, InstanceState, SystemStatus, and InstanceStatus.

Logging: Outputs the status report into a .txt file daily for historical tracking.

Email Notifications (optional): Sends the status report via email using PowerShell.

AWS SNS Integration: Publishes the same report to an SNS topic, which can notify multiple subscribers instantly.

Task Scheduler Automation: The .bat script is scheduled to run daily using Windows Task Scheduler to ensure hands-free automation.

Why It's Important:
This setup is useful in any environment where EC2 instances are used to host production websites or critical applications. It ensures system administrators or cloud support engineers are aware of the status without logging into the AWS Console daily. It’s especially valuable for Cloud Technical Support roles, where proactive issue detection is a key responsibility.

Technologies Used:
AWS CLI

IAM (for secure user access)

SNS (for alerting)

PowerShell (for email scripting)

Windows Task Scheduler

This project also demonstrates a security best practice by avoiding the use of the AWS root account and instead creating an IAM user with fine-grained permissions for EC2 and SNS actions.

Overall, it's a real-time cloud automation solution, showcasing readiness for cloud support roles through hands-on AWS experience.



