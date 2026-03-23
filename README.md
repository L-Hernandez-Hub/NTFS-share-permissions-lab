# NTFS + Share Permissions Lab

## Objective
Configure shared folders in a Windows Server environment and implement access control using Share and NTFS permissions. Validate access based on Active Directory group membership.

---

## Lab Environment

- Windows Server 2019 Virtual Machine  
- Active Directory Domain Services (AD DS)  
- Active Directory Users and Computers (ADUC)  
- Windows 11 Pro (Domain-joined client)

---

## Skills Demonstrated

- File share configuration  
- NTFS permission management  
- Active Directory group-based access control  
- Access validation and troubleshooting  
- Understanding Share vs NTFS permission interaction  

---

## Step-by-Step Configuration

### 1. Create Folder Structure

Created a centralized directory for departmental shares.

**Folders:**
- C:\Shares\HR  
- C:\Shares\IT  
- C:\Shares\Sales  

Screenshot 1: Folder structure  
![Folder Structure](1-folder-structure.png)

---

### 2. Configure Share Permissions (HR)

Shared the HR folder and assigned permissions to the HR security group.

Screenshot 2: Advanced Sharing enabled  
![HR Advanced Sharing](2-hr-advanced-sharing.png)

Screenshot 3: Share permissions (HR_Users group)  
![HR Share Permissions](3-hr-share-permissions.png)

**Configuration:**
- Share name: HR  
- Group: HR_Users  
- Permissions: Change, Read  

---

### 3. Configure NTFS Permissions (HR)

Configured file system permissions for the HR folder.

Screenshot 4: NTFS permissions (Security tab)  
![HR NTFS Permissions](4-hr-ntfs-permissions.png)

**Configuration:**
- Group: HR_Users  
- Permissions: Modify, Read & Execute, Write  

---

### 4. Configure IT and Sales Folders

Applied the same process to additional departments.

Screenshot 5: IT permissions  
![IT Permissions](5-it-permissions.png)

Screenshot 6: Sales permissions  
![Sales Permissions](6-sales-permissions.png)

---

### 5. Validate Access from Client Machine

Tested access using domain users.

Screenshot 7: Authorized access (HR user → HR folder)  
![HR Access Success](7-hr-access-success.png)

Screenshot 8: Access denied (HR user → IT/Sales folders)  
![Access Denied](8-access-denied.png)

---

## Key Takeaways

- Share permissions control access over the network, while NTFS permissions control access at the file system level  
- The most restrictive permission between Share and NTFS determines final access  
- Assigning permissions to security groups instead of individual users improves scalability and management  
- Group-based access control simplifies administration and aligns with real-world best practices  
- Proper permission configuration ensures users can only access resources relevant to their role