### AWS iam user

An **IAM User** represents a specific identity in AWS, typically tied to a person or an application, and it's used to interact directly with AWS services.

- **Permanent Identity**: An IAM user has a permanent identity within AWS and is associated with long-term credentials (such as **access keys** and **secret keys**).

- **Access Keys**: IAM users can have **access keys** (for programmatic access) and **passwords** (for console access).

- **Attached Policies**: IAM users can have **managed policies** (either AWS-managed or customer-managed) and **inline policies** directly attached to them. These policies define what actions the user is allowed to perform on AWS resources.

- **Credentials**: IAM users have **static credentials** (access keys or passwords). These credentials can be rotated or deleted but are generally fixed unless explicitly changed.

#### Example:

- User `alice` might have the IAM user ARN `arn:aws:iam::123456789012:user/alice`, and her credentials allow her to interact with specific AWS services based on attached policies.