# EC2 Instance Setup and CloudWatch Monitoring Demo


## Setup

1. Launch an EC2 instance with SSH and HTTP configuration.

2. SSH into the instance.

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

## CloudWatch Monitoring Setup

1. Go to the AWS Management Console and navigate to CloudWatch.

2. Under Metrics, look for "EC2" and search for CPU Utilization.

3. Create an alarm for CPU Utilization:
   - Set the threshold to greater than or equal to 50%.
   - Configure actions to notify via SNS.
   - Create an SNS topic with your email address.
   - Accept the subscription from the email address provided.
   - Create the alarm.

## Testing

1. Log back into the EC2 instance.

2. Run the Python script:

    ```bash
    python3 file.py
    ```

3. Observe the CPU utilization reaching 50% or above.

4. You will receive an alert notification on the email address you provided.

## Cleanup

Remember to clean up the resources to avoid unnecessary costs:
- Terminate the EC2 instance.
- Delete any created alarms and SNS topics.


