# EC2 Instance Setup and CloudWatch Monitoring Demo


## Setup

1. Launch an EC2 instance with SSH and HTTP configuration.

2. SSH into the instance.
![MicrosoftTeams-image (1)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/87d9973c-8497-435c-bd45-09fdc44ab5e0)



3. Check if Git is installed:

    ```bash
    git --version
    ```

4. If Git is not installed, install it:

    ```bash
    sudo apt update
    sudo apt install git
    ```

5. Check if Python is installed:

    ```bash
    python3 --version
    ```

6. If Python is not installed, install it:

    ```bash
    sudo apt update
    sudo apt install python3
    ```

7. Clone the repository:

    ```bash
    git clone https://github.com/aclockworkobi9/cloudwatch_cpu_spike.git
    ```
![MicrosoftTeams-image (2)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/ebab17fa-85f4-4ee8-8428-a2ae6abdf82b)


## CloudWatch Monitoring Setup

1. Go to the AWS Management Console and navigate to CloudWatch.

2. Under Metrics, look for "EC2" and search for CPU Utilization and you will see no utilization at that specific moment.
![MicrosoftTeams-image (3)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/4fc73067-438b-475e-b6cd-900dc9b9d953)
![MicrosoftTeams-image (4)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/0f1fa618-8490-4b2f-b938-d062a6e0124d)
![MicrosoftTeams-image (5)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/5581d38f-efbf-4baf-b850-ae68d5739f87)


3. Create an alarm for CPU Utilization:
   - Set the threshold to greater than or equal to 50%.
   - Configure actions to notify via SNS.
   - Create an SNS topic with your email address.
   - Accept the subscription from the email address provided.
   - Create the alarm with the message.
     
![MicrosoftTeams-image (6)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/b16f6c1f-a847-477f-8908-74cf338e2fab)
![MicrosoftTeams-image (7)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/d6e134ef-0532-4800-89c0-01afbf61cdce)
![MicrosoftTeams-image (8)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/01d3e8d6-c25c-4782-b6fe-c6f2fddbd0a5)
![MicrosoftTeams-image (9)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/0f46e3e0-391c-470b-8be2-b6f9d123eaa0)
![MicrosoftTeams-image (10)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/7dfa42d3-1e39-4aeb-943c-2116731c5a31)
![MicrosoftTeams-image (11)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/0c13619e-e504-458a-9fa5-e447bdbc2afe)



## Testing

1. Log back into the EC2 instance.

2. Run the Python script:

    ```bash
    python3 spike_cpu.py
    ```
![MicrosoftTeams-image (12)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/d70d92f5-2a1d-4335-b548-6a756853e9c3)


3. Observe the CPU utilization reaching 50% or above.
![MicrosoftTeams-image (13)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/6d9a1f34-1e0b-4e7d-87e9-68f563ed6c9b)
![MicrosoftTeams-image (14)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/0d586341-d624-4b92-9f5b-f50154d912db)
![MicrosoftTeams-image (15)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/14e48269-4c19-4523-a68c-f13c0a7ed059)


4. You will receive an alert notification on the email address you provided.
![MicrosoftTeams-image (16)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/9305b5da-11ce-4bd7-9f9a-83754c6c7b60)
![MicrosoftTeams-image (17)](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/cc0d8863-fa3a-4275-a746-8cdc7a51b3ec)


## Cleanup

Remember to clean up the resources to avoid unnecessary costs:
- Terminate the EC2 instance.
- Delete any created alarms and SNS topics.


