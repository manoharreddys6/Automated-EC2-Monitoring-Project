# Automated-EC2-Monitoring-Project
Automated EC2 monitoring project using AWS CLI, SNS, and Task Scheduler. Fetches daily EC2 status, logs to a file, and sends alerts via SNS or email. Ideal for cloud support roles to ensure uptime of hosted applications. Built on Windows with secure IAM access.


**.bat file :**

@echo off
cd /d "%~dp0"
echo Fetching EC2 Instance Status...

REM Save output to file
aws ec2 describe-instance-status --include-all-instances ^
--query "InstanceStatuses[*].{ID:InstanceId,State:InstanceState.Name,System:SystemStatus.Status,Instance:InstanceStatus.Status}" ^
--output table > status_output.txt

echo Sending EC2 Status Report via SNS...

REM Publish file content as SNS message
aws sns publish --topic-arn arn:aws:sns:ap-south-1:1832954136xx:EC2StatusAlerts ^
--subject "Daily EC2 Status Report" ^
--message file://status_output.txt

echo Done!
pause
