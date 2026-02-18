### Essential Gloud Cloud infrastructure Core Services

### Service Accounts
Think of a Service Account as a **"Robot User."**
- **What it is:** It’s an identity used by an application or a Virtual Machine (VM), not a person.
- **Why use it:** If your application on a VM needs to read data from a Bucket, you don't want to type your own password into the code. Instead, you "attach" a Service Account to the VM.
- **The Benefit:** It has its own email-like ID (e.g., my-app@project-id.iam.gserviceaccount.com). If that app gets hacked or retired, you just revoke that specific account's permissions without affecting your own.

### Organization Restrictions
This is a ***"No Trespassing"*** sign for your company's devices.

- Even if an employee has a personal Gmail account, Organization Restrictions prevent them from using company-managed laptops to access any Google Cloud resources outside of your official company organization.
- It stops ***"Data Exfiltration"** (sending company data to a personal project).

### 2. Cloud Storage Classes (The "Cost vs. Speed" Scale)
| Storage Class | Min Duration | Best For... | Simple Logic |
| :--- | :--- | :--- | :--- |
| **Standard** | 0 days | Daily use, website images, "Hot" data. | Accessing many times a month. |
| **Nearline** | 30 days | Monthly backups, data you check once a month. | Accessing < once a month. |
| **Coldline** | 90 days | Disaster recovery, quarterly reports. | Accessing < once a quarter. |
| **Archive** | 365 days | Regulatory data (legal/tax) kept for years. | Accessing < once a year. |

> Autoclass: This is like "Smart Mode." If you don't want to guess, Autoclass moves your data between these classes automatically based on how often you actually touch the files.

### Advanced Storage Features
Access Control Lists (ACLs) vs. Signed URLs
- ***ACLs:** These are "Fine-Grained" permissions. While IAM usually gives access to a whole bucket, ACLs allow you to say "User A can see File 1, but not File 2." (Note: Google now recommends using IAM "Uniform" access for most things to keep it simple).
- **Signed URLs:** Think of this as a "Temporary Guest Pass." You generate a special link that lets anyone download a specific file for, say, 15 minutes—even if they don't have a Google account.

### Object Lifecycle Management & Locks
- **Object Lifecycle Management:** A set of "Rules." Example: "If a file is older than 365 days, move it to Archive" or "Delete all files in the 'temp' folder after 7 days."
- **Object Retention Lock:** The "Vault." Once locked, nobody (not even the owner) can delete the file until the timer is up. Great for legal compliance.
- **Soft Delete:** The "Safety Net." If you accidentally delete a file, it stays in a hidden state for a few days (usually 7 by default) so you can "undelete" it.

### Filestore (The "Shared Folder")
While Cloud Storage is for "Objects" (images, videos, backups), Filestore is for "Files" in a traditional sense.
- **What it is:** A fully managed NFS (Network File System).
- **The Use Case:** Imagine you have 10 different Virtual Machines that all need to read and write to the same shared folder at the same time (like a shared drive in an office).
- **Key Benefit:** It supports existing legacy apps that expect a real file system structure (/home/data/shared) rather than an API.
