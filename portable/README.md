# Portable CloudFormation Labs

This folder contains CloudFormation templates that improve portability step-by-step.
The main improvement is avoiding hard-coded region-specific values (like AMI IDs).

---

## Files

### Stage 1

- `portable-stage1.yaml`
- `portable-stage1.json`

Goal: introduce a portable structure and remove hard-coded values where possible.

### Stage 2

- `portable-stage2.yaml`
- `portable-stage2.json`

Goal: improve portability and template reusability.

### Stage 3 (Latest AMI via SSM)

- `portable-stage3.yaml`
- `portable-stage3.json`

Goal: use AWS Systems Manager (SSM) public parameters to dynamically retrieve the
latest Amazon Linux 2 AMI, making the EC2 AMI selection portable across regions.

---

## Key idea used in Stage 3 (SSM AMI lookup)

The template uses this parameter type:

```yaml
Parameters:
  LatestAmiId:
    Type: "AWS::SSM::Parameter::Value<AWS::EC2::Image::Id>"
    Default: "/aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2"
```
