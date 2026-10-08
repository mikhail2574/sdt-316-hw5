# AWS Academy Cloud Foundations — Task 2

## 2.1 Shared Responsibility Model

A company stores customer invoices in Amazon S3. Its developer assumes AWS automatically protects every S3 bucket because AWS manages the underlying cloud infrastructure. During deployment, the developer disables S3 Block Public Access and adds a bucket policy allowing anonymous users to read objects. As a result, anyone with an object URL can download invoices containing customer names, addresses, and payment details. This creates a data breach, possible regulatory penalties, and loss of customer trust.

Under the Shared Responsibility Model, AWS secures the physical facilities, hardware, and underlying infrastructure, but the customer controls its data and bucket permissions. AWS does not automatically correct every unsafe access policy. The company should enforce S3 Block Public Access, use least-privilege bucket policies, and monitor configuration changes with AWS Config. Regular security reviews and automated checks could detect this misconfiguration before sensitive documents become publicly accessible.

## 2.2 Capital Expense vs. Operating Expense

Buying a physical server is a capital expense (CapEx) with an upfront purchase cost, while AWS typically charges for usage as an operating expense (OpEx). Because cloud consumption can grow unexpectedly, the budget alert helps detect rising costs. A purchased server does not accumulate additional per-hour compute charges simply because it stays running.

## 2.3 Regions and Availability Zones

An AWS Region contains multiple physically separated Availability Zones (AZs) to isolate failures. Deploying an application across AZs improves availability and resilience: if one AZ fails, healthy resources in another can continue serving users. This reduces single points of failure, though the application must be designed for failover.

## 2.4 IAM Users vs. Roles

IAM roles provide temporary, automatically expiring credentials and are preferred for applications and workloads. They avoid storing long-term access keys in code or configuration files. If a long-term IAM user key leaks, an attacker can keep using it until it is revoked. Compromised role credentials generally expire sooner, reducing the window of exposure.
