# EC2 Instance Setup and CloudWatch Monitoring Demo


## Setup

1. Launch an EC2 instance with SSH and HTTP configuration.

2. SSH into the instance.
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/9b8a6040-57ba-40ca-ada3-eddf0d2d041f)


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
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/cbce0421-e38a-4275-b75d-75bdb4c32aa9)

## CloudWatch Monitoring Setup

1. Go to the AWS Management Console and navigate to CloudWatch.

2. Under Metrics, look for "EC2" and search for CPU Utilization.
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/ccfff636-22aa-44f5-a548-f358e3fc9486
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/9d6e7642-8fb9-402d-998d-f6f3665b148d)

4. Create an alarm for CPU Utilization:
   - Set the threshold to greater than or equal to 50%.
   - Configure actions to notify via SNS.
   - Create an SNS topic with your email address.
   - Accept the subscription from the email address provided.
   - Create the alarm.
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/5b33e34d-9583-4d65-bfb1-c06fdaf2bcb3)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/607955dd-b282-4452-8265-e9b1d9c47c1e)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/27a14b7c-fdd0-4d98-8506-dd23cc76f99a)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/075d56e5-dca8-4935-bfe5-f1af36b4ffcf)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/e70eb7f5-01f8-417b-989d-ebc87e951627)

## Testing

1. Log back into the EC2 instance.

2. Run the Python script:

    ```bash
    python3 spike_cpu.py
    ```
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/b91118b3-251f-4198-a7e6-8c4c1f2e680d)

3. Observe the CPU utilization reaching 50% or above.
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/6fece888-46e6-4d29-b12a-ce7e5fc745f0)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/d901ab3e-f1d6-47a8-8a9b-1da03add5233)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/42d5c266-3f3a-42be-b3ba-6c282e2d6050)

4. You will receive an alert notification on the email address you provided.
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/106e51ea-2f99-495f-b323-7f4eeed1adc7)
[image](https://github.com/aclockworkobi9/Cloudwatch_monitoring/assets/146419037/00237eea-d107-4a3a-ba11-21dc4bfb34c4)

## Cleanup

Remember to clean up the resources to avoid unnecessary costs:
- Terminate the EC2 instance.
- Delete any created alarms and SNS topics.


