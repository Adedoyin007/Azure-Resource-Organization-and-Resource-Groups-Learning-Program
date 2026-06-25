# Azure-Resource-Organization-and-Resource-Groups-Learning-Program
Azure Resource Organization and Resource Groups Learning Program

Azure Resource Organization, Tagging & RBAC Lab

📌 Project Overview

This project demonstrates how Microsoft Azure resources are organized and managed using:

* Naming conventions
* Resource group structuring
* Tagging strategy
* Role-Based Access Control (RBAC)

The environment simulates Development, Testing, and Production workloads.

⸻

🏷️ Naming Convention

All resources follow a structured naming format:

<environment>-<application>-<resourceType>-<region>

✅ Examples from Deployment

* dev-webapp-rg-eastus
* test-webapp-rg-eastus
* prod-api-rg-eastus

🔍 Example Breakdown

dev-webapp-rg-eastus

* dev → Development environment
* webapp → Application
* rg → Resource group
* eastus → Region

⸻

📁 Resource Group Structure

The following resource groups were created:

* dev-webapp-rg-eastus
* test-webapp-rg-eastus
* prod-api-rg-eastus
* NetworkWatcherRG (Azure default)
* asiwaju-cloud-lab (general purpose)

✔️ Design Benefits

* Environment isolation
* Easier management and deletion
* Reduced risk of impacting production

⸻

🏷️ Tagging Strategy (Actual Implementation)

Tags were applied at the resource group level.

🔹 Observed Tags

dev-webapp-rg-eastus

owners = dev-webapp-rg-eastus

prod-api-rg-eastus

production = team A

⸻

🔹 Analysis of Tagging

* Tags are inconsistent in structure
    * One uses owners
    * Another uses production
* Values are also inconsistent:
    * Resource name used as value
    * Team name used as value

⸻

🔹 What This Demonstrates

* Basic understanding of Azure tagging
* Ability to assign metadata to resource groups
* Initial attempt at categorization

⸻

🔹 Recommended Improvement (Best Practice)

Use consistent keys across all resources:

environment = dev / test / prod
owner = teamA
project = azure-lab

⸻

🔐 Role-Based Access Control (RBAC)

RBAC was configured at the resource group level.

🔹 prod-api-rg-eastus

* Owner (2 assignments – subscription level)
* Contributor (1 assignment – resource group level)
* Role Based Access Control Administrator (1 assignment – resource group level)

⸻

🔹 dev-webapp-rg-eastus

* Owner (2 assignments – subscription level)
* Role Based Access Control Administrator (1 assignment – resource group level)

⸻

🔹 Key Observations

* All roles are assigned to a single user (lab account)
* No separate users, groups, or teams configured
* Permissions are not segmented between environments

⸻

🔹 Role Meaning

* Owner → Full control, including access management
* Contributor → Can manage resources but not access
* RBAC Administrator → Can manage access only

⸻

🔹 Evaluation

This setup:

✔ Works correctly for a lab
✔ Demonstrates understanding of RBAC roles

However:

❌ Does not simulate real multi-team access
❌ Lacks separation between dev and production users

⸻

🔄 Resource Lifecycle Management

Lifecycle testing included:

* Creating resource groups
* Deploying resources
* Deleting resource groups

Result

* Deleting a resource group removes all contained resources
* Confirms efficient cleanup and cost control

⸻

📸 Screenshots Included

* Resource group list
* RBAC configuration (dev & prod)
* Tagging configuration

⸻

📂 Repository Structure

azure-rbac-lab/
│
├── README.md
├── screenshots/
│   ├── resource-groups.png
│   ├── dev-rbac.png
│   ├── prod-rbac.png
│   ├── dev-tags.png
│   └── prod-tags.png

⸻

✅ Conclusion

This lab demonstrates:

* Consistent Azure naming conventions
* Environment-based resource organization
* Basic tagging implementation
* Functional RBAC configuration

While the setup is valid for learning, improvements in tag consistency and RBAC separation would better reflect a real-world production environmen
