![image](https://github.com/user-attachments/assets/0e35f0fa-3389-47eb-973b-5d326d43a25e)

# SYSADM1 -- Kerberos Lab Activity: A step-by-step Guide

**Objective:**

Set up a basic Kerberos authentication system to understand how Kerberos
manages secure logins through ticket-based access.

**Setup Requirements:**

-   Two VMs in Oracle VM, both running a Linux distribution like Ubuntu
    or CentOS.

-   VM1: Kerberos Server

-   VM2: Kerberos Client

**Step 1: Initial Setup and Package Installation**

1.  **Update Packages on Both VMs:**

    -   Open a terminal on each VM and run:

*bash*

*sudo apt update && sudo apt upgrade --y*

Server:

![image](https://github.com/user-attachments/assets/1b3a7052-7ead-457d-9a29-2fdbf7c11ec6)


Client:

![image](https://github.com/user-attachments/assets/dc9e337b-c179-4e93-9324-884da21c33a6)


2.  **Install Kerberos Server Packages on VM1 (Kerberos Server):**

    -   In VM1, install the Kerberos Key Distribution Center (KDC) and
        admin server:

*bash*

*sudo apt install krb5-kdc krb5-admin-server --y*

![image](https://github.com/user-attachments/assets/6f2c5ab5-4d1a-4088-aa9d-41e9e0a51998)


3.  **Install Kerberos Client Package on VM2 (Kerberos Client):**

    -   In VM2, install the Kerberos client software:

*bash*

*sudo apt install krb5-user -y*

-   During installation, when prompted, enter the Kerberos realm you
    plan to set up, e.g., MYLAB.LOCAL.

![image](https://github.com/user-attachments/assets/5a07c2f8-5579-425a-8d21-741201314271)


**Step 2: Configure the Kerberos Server (VM1)**

1.  **Edit the Kerberos Configuration File:**

    -   Open /etc/krb5.conf for editing:

*bash*

*sudo nano /etc/krb5.conf*

-   Set the realm as MYLAB.LOCAL. You should also specify the KDC and
    admin server as VM1's hostname or IP address:

ini

\[libdefaults\]

default_realm = MYLAB.LOCAL

\[realms\]

MYLAB.LOCAL = {

kdc = \<VM1_IP_or_hostname\>

admin_server = \<VM1_IP_or_hostname\>

}

-   Save and close the file (Ctrl+X, then Y, and Enter to confirm).

![image](https://github.com/user-attachments/assets/b2ce848f-23fc-4b7b-a6f5-d8e2b026a5fb)


2.  **Initialize the Kerberos Database:**

    -   Create the database for the Kerberos realm:

*bash*

*sudo krb5_newrealm*

-   You will be prompted to set a password for the Kerberos database.

![image](https://github.com/user-attachments/assets/e8980266-c658-4c09-ad4f-af71ec78e59c)


3.  **Start and Enable the Kerberos Services:**

    -   Start the KDC and admin server, and ensure they start
        automatically on boot:

*bash*

*sudo systemctl start krb5-kdc*

*sudo systemctl start krb5-admin-server*

*sudo systemctl enable krb5-kdc*

*sudo systemctl enable krb5-admin-server*

![image](https://github.com/user-attachments/assets/0b173791-feed-44b4-b622-a336ffd7ea7f)


**Step 3: Set Up a Kerberos User Principal**

1.  **Create a New User Principal:**

    -   Run the following command to create a test user in the Kerberos
        realm:

*bash*

*sudo kadmin.local -q \"addprinc testuser@MYLAB.LOCAL\"*

-   Set a password for testuser.

![image](https://github.com/user-attachments/assets/5c18ae98-f5b1-4d22-840f-7f9bf1c0aeed)


2.  **Verify the User Principal:**

    -   To confirm the principal is created, list all principals:

*bash*

*sudo kadmin.local -q \"listprincs\"*

![image](https://github.com/user-attachments/assets/4dc30ac4-1f72-4cca-89b2-9fee4d360d2c)


**Step 4: Configure the Kerberos Client (VM2)**

1.  **Edit the Kerberos Configuration File on VM2:**

    -   Open /etc/krb5.conf for editing on VM2:

*bash*

*sudo nano /etc/krb5.conf*

-   Set the default realm to MYLAB.LOCAL and point to the KDC and admin
    server on VM1. The configuration should match what you set on VM1.

![image](https://github.com/user-attachments/assets/19c45d4f-13df-41d4-a345-185e03e8a68f)


**Step 5: Test Kerberos Authentication**

1.  **Request a Kerberos Ticket for the User on VM2:**

    -   In the terminal on VM2, request a ticket for testuser:

*bash*

*kinit testuser@MYLAB.LOCAL*

-   Enter the password you set for testuser.

![image](https://github.com/user-attachments/assets/e8ac9ccb-4e23-42a4-ad3c-ee545f958a5f)


2.  **Verify the Ticket:**

    -   Check if the ticket was issued by listing active Kerberos
        tickets:

*bash*

*klist*

-   You should see details about the ticket, such as the principal and
    expiration time, confirming successful Kerberos authentication.

![image](https://github.com/user-attachments/assets/ff6fd9ed-fcd4-49fa-8a13-5ee04e6dc41e)

