# Akeyless Secret Sharing Demo 🚀  

This demo automates **secure secret storing and sharing** using **Akeyless, GitHub Actions, and Entra ID (Azure SSO).**  

### **🔹 How It Works**  
1️⃣ **Stores LDAP credentials** in Akeyless as a Secret under a per-user path.  
2️⃣ **Grants secure access** so users can retrieve their credentials from the Akeyless Console via **SSO with Azure Entra ID**.  
3️⃣ **Emails the requester** with metadata and an **SSO link to their secret**.  

### **🚀 Running the Workflow**  
1. Go to **GitHub Actions** → Select **"Provision & Share Secret"** → Click **"Run Workflow"**.  
2. The workflow automatically:
   - Fetches a **temporary LDAP credential** from Akeyless.  
   - Stores it securely in **Akeyless Vault** under `/demo/shared_with_me/<email>/LMS_credential`.  
   - Retrieves the **Akeyless Item ID** and constructs a secure link.  
   - Sends an **email notification to the requester** with a **direct link** to the stored credential in Akeyless.  
3. The requester can **log in via Azure Entra ID SSO** and access their secret securely.  

### **🔑 Prerequisites**  
- **Akeyless account** with **LDAP Target & SSO configured**.  
- **GitHub Variable (`vars.AKEYLESS_ACCESS_ID`)** with the Akeyless access-id to a JWT Auth Method for GitHub Actions (with appropriate RBAC permissions).  
- **Configured SMTP settings** for email notifications (e.g., **Gmail App Password** stored as GitHub Variables).  
