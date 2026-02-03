# Portable CloudFormation Template – Stage 3

This lab demonstrates a **portable CloudFormation template** that provisions
AWS resources using dynamic values instead of hard-coded ones.

---

## File

- `portable-stage3.yaml`

---

## Resources Created

- **S3 Bucket**
- **EC2 Instance**

---

## Why this template is portable

### Dynamic AMI lookup

- The EC2 AMI is retrieved dynamically from **AWS Systems Manager (SSM)**.
- This allows the template to work across regions without modification.

```yaml
Parameters:
  LatestAmiId:
    Type: "AWS::SSM::Parameter::Value<AWS::EC2::Image::Id>"
```
