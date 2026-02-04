## 🔧 Common `gcloud` Commands and Their Purpose

## 🔧 Common `gcloud` Commands and Their Purpose

| Command                                                        | Purpose                                                      |
|----------------------------------------------------------------|--------------------------------------------------------------|
| `gcloud auth list`                                             | Shows which account is currently active                      |
| `gcloud config list`                                           | Displays your current project, region, and zone              |
| `gcloud config set project [ID]`                               | Switches your focus to a specific project                    |
| `gcloud info`                                                  | Gives a big-picture summary of your current setup            |
| `gcloud compute instances list`                                | To list all VM details                                       |
| `gcloud storage buckets create gs://[bucketname]`              | To create new bucket                                         |
| `gcloud compute regions list`                                  | To list all available regions                                |
| `gcloud projects list`                                         | To list all the projects                                     |
| `gcloud storage buckets create gs://[bucketname]`              | To list all VM details                                       |
| `gcloud config get-value project`                              | Use this to verify where your resources will be created.     |
| `gcloud config set project [PROJECT_ID]`                       | Updates your active configuration to point to a specific project. This is the most common way to switch between projects. |
| `gcloud config configurations create [NAME]` | Creates a new, empty configuration profile. Useful when working across multiple companies or environments (e.g., `work-prod` vs `personal-dev`) and switching between them quickly. |
