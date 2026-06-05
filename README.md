# aws-ebs-gp2-to-gp3-automation
Automatically detect newly created EBS volumes of type GP2 and convert them to GP3 using AWS Lambda and CloudWatch/EventBridge.

# The Project Architecture
User Creates EBS Volume (GP2)
           │
           ▼
 AWS EventBridge Rule
 (EBS CreateVolume Event)
           │
           ▼
      AWS Lambda
           │
           ▼
Check Volume Type
           │
    GP2 ? Yes
           │
           ▼
 Modify Volume
 GP2 → GP3
           │
           ▼
 CloudWatch Logs
