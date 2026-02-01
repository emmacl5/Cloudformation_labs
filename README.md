# CloudFormation Labs

This repository contains hands-on CloudFormation labs created to practice
AWS Infrastructure as Code (IaC) and GitHub workflows.

The goal of this repository is to understand how AWS resources can be
defined, versioned, and documented using CloudFormation and Git.

---

## Lab 1: Non-Portable CloudFormation Template

**File:** `nonportable.yaml`

This lab demonstrates a simple, intentionally non-portable CloudFormation
template.

### Resources Created

- **S3 Bucket**
- **EC2 Instance**

### Why this template is non-portable

- The S3 bucket name is hard-coded and must be globally unique.
- The AMI ID is hard-coded and only works in a specific AWS region.

---

## CloudFormation Concepts Practiced

- Writing CloudFormation templates in YAML
- Defining resources using the `Resources` section
- Understanding logical IDs, resource types, and properties
- Recognizing portability issues in templates

---

## How to Deploy

```bash
aws cloudformation deploy \
  --template-file nonportable.yaml \
  --stack-name nonportable-lab
```
