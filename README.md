# Zero-Trust Architecture for Secure Cloud Resource Access

A Zero Trust access model for AWS cloud resources — replacing static, long-lived credentials with short-lived, role-based access and real-time monitoring.

## Overview

Traditional cloud access often relies on long-lived IAM keys, which are a common source of credential leaks and lateral-movement attacks. This project implements a Zero Trust model where every access request is authenticated and authorized individually — no implicit trust based on network location or standing credentials.

## Architecture

- **AWS IAM Roles + STS** — temporary, short-lived credentials issued per session instead of static access keys
- **IMDSv2** — enforced on EC2 instances to prevent SSRF-based credential theft from instance metadata
- **CloudTrail** — logs every API call and role assumption for full auditability
- **EventBridge + SNS** — event-driven pipeline that triggers real-time alerts on role changes and sensitive S3 access (e.g. `GetObject`)

## Tech Stack

`AWS IAM` `STS` `IMDSv2` `CloudTrail` `EventBridge` `SNS` `S3`

## What This Demonstrates

- Designing access control around identity and context rather than network perimeter
- Building an event-driven security monitoring pipeline on native AWS services
- Applying Zero Trust principles to a practical cloud resource access scenario
