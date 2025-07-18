# Secure Healthcare Data Analytics Platform on Google Cloud Platform (GCP)

## Project Overview

This project demonstrates the design and implementation of a secure healthcare analytics platform on Google Cloud Platform using BigQuery, Cloud KMS, IAM, and Data Catalog metadata management. It focuses on ensuring data confidentiality, fine-grained access control, and data governance best practices in the absence of an organization-level setup.

## Objectives

- Upload batch healthcare data securely to BigQuery with Customer-Managed Encryption Keys (CMEK) from Cloud KMS.
- Implement fine-grained IAM roles to restrict dataset, table, and view access by user accounts.
- Simulate column-level security by creating secure BigQuery views exposing only non-sensitive data.
- Enhance data governance through labels, descriptions, and manual metadata management.
- Utilize Cloud Audit Logs for data access monitoring and compliance tracking.
- Explore and demonstrate limitations and workarounds when Data Catalog auto-tagging and policy tags are unavailable without an organization.

## Architecture

      +------------------+          +----------------+          +---------------------+
      |  Healthcare Data |          |    Cloud KMS   |          |      BigQuery       |
      |    (Batch CSV)   |   --->   |   CMEK Keys    |   --->   |  Dataset & Tables   |
      +------------------+          +----------------+          +---------------------+
                                             |
                                             | (Encryption)
                                             v
                     +-----------------------------------------+
                     |    Fine-Grained IAM and Secure Views    |
                     +-----------------------------------------+
                                             |
                                             v
                       +-----------------------------------+
                       |     Data Governance & Metadata    |
                       |   - Labels and Descriptions       |
                       |   - Manual Tagging                |
                       +-----------------------------------+



