# Akeyless Secret Sharing Demo 🚀  

This demo automates **secure secret storing and sharing** using **Akeyless, GitHub Actions, and Entra ID (Azure SSO).**  

### **🔹 How It Works**  
1️⃣ **Stores LDAP credentials** in Akeyless as a Secret under a per-user path.  
2️⃣ **Grants secure access** so users can retrieve their credentials from the Akeyless Console via **SSO with Azure Entra ID**.  
3️⃣ **Emails the requester** with metadata and an **SSO link to their secret**. 
4️⃣ **Automatically adds the user to the Akeyless SSO App in Entra ID**, if needed.  

### **🚀 Running the Workflow**  
1. Go to **GitHub Actions** → Select **"Provision & Share Secret"** → Click **"Run Workflow"**.  
2. Enter:
   - **Requester Email**  
   - **Akeyless Gateway URL**  
   - **LDAP Target Name**
   - **User Base DN for LDAP Searches**  
3. Click **Run**, then check Akeyless:  
   - **Stored Secret:** `/demo/shared_with_me/<email>/LMS_credential`
   - **SSO Access:** Ensure the user is added to Akeyless SSO in Entra ID.

### **🔑 Prerequisites**  
- **Akeyless account** with **LDAP Target & SSO configured**.
- **GitHub Variable (`vars.AKEYLESS_ACCESS_ID`)** with the Akeyless access-id to a JWT Auth Method for Github Actions (with appropriate RBAC permissions).
