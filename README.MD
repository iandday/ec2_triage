# Automated EC2 Triage

Devloped to fulfill requirements of Champlain's Masters of Digital Forensic Science capstone course

## Features

* Tagging of instance with investigation related data
* Snapshot creation for all involved EBS volumes
* Execution of triage commands to document the instance's state at time of triage
* Aggregation of triage command output and pertitent log files in an S3 bucket for analysis

## Document Hierachy

The `triage.ssm.yml` document is the top level document and is called from the Systems Manager console, all remaining documents are called as needed based on detected operating system.


* `triage.ssm.yml`
  * `triage-linux.ssm.yaml`
    * `triage-linux-command.ssm.yaml`
  * `triage-windows.ssm.yaml`: Pending
    * `triage-windows-command.ssm.yaml`: Pending

## Setup

### Required Variables
* `caseNum`: Associated case number, to tag all involved assets with
* `bucket`: Bucket name to copy all relevant logs and command output
* `instanceID`: EC2 instance ID number to triage



