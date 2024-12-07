+----------------------------------+------------------------+----------+
| ![](vertopal_                    |                        |          |
| 4cf10180e78e457385f96b84523955a3 |                        |          |
| /media/image1.png){width="2.4in" |                        |          |
| height="0.5881944444444445in"}   |                        |          |
|                                  |                        |          |
| SCHOOL OF INFORMATION AND        |                        |          |
| TECHNOLOGY                       |                        |          |
+----------------------------------+------------------------+----------+
| NAME: Zschairail Balanza         | DATE PERFORMED:        | /50      |
|                                  | 14/11/24               |          |
+----------------------------------+------------------------+----------+
| Section: IDC2                    | DATE SUBMITTED:14/11/2 |          |
+----------------------------------+------------------------+----------+

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

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image2.png){width="7.027083333333334in"
height="0.7305555555555555in"}

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image3.png){width="7.027083333333334in"
height="1.51875in"}

Client:

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image4.png){width="7.027083333333334in"
height="0.8201388888888889in"}

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image5.png){width="7.027083333333334in"
height="1.3041666666666667in"}

2.  **Install Kerberos Server Packages on VM1 (Kerberos Server):**

    -   In VM1, install the Kerberos Key Distribution Center (KDC) and
        admin server:

*bash*

*sudo apt install krb5-kdc krb5-admin-server --y*

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image6.png){width="7.027083333333334in"
height="0.6722222222222223in"}

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image7.png){width="7.027083333333334in"
height="1.0951388888888889in"}

3.  **Install Kerberos Client Package on VM2 (Kerberos Client):**

    -   In VM2, install the Kerberos client software:

*bash*

*sudo apt install krb5-user -y*

-   During installation, when prompted, enter the Kerberos realm you
    plan to set up, e.g., MYLAB.LOCAL.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image8.png){width="7.027083333333334in"
height="1.1784722222222221in"}

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image9.png){width="7.027083333333334in"
height="0.8208333333333333in"}

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

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image10.png){width="5.592981189851269in"
height="1.6332895888013998in"}

2.  **Initialize the Kerberos Database:**

    -   Create the database for the Kerberos realm:

*bash*

*sudo krb5_newrealm*

-   You will be prompted to set a password for the Kerberos database.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image11.png){width="4.573555336832896in"
height="0.9688856080489939in"}

3.  **Start and Enable the Kerberos Services:**

    -   Start the KDC and admin server, and ensure they start
        automatically on boot:

*bash*

*sudo systemctl start krb5-kdc*

*sudo systemctl start krb5-admin-server*

*sudo systemctl enable krb5-kdc*

*sudo systemctl enable krb5-admin-server*

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image12.png){width="7.027083333333334in"
height="3.623611111111111in"}

**Step 3: Set Up a Kerberos User Principal**

1.  **Create a New User Principal:**

    -   Run the following command to create a test user in the Kerberos
        realm:

*bash*

*sudo kadmin.local -q \"addprinc testuser@MYLAB.LOCAL\"*

-   Set a password for testuser.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image13.png){width="7.027083333333334in"
height="0.46319444444444446in"}

2.  **Verify the User Principal:**

    -   To confirm the principal is created, list all principals:

*bash*

*sudo kadmin.local -q \"listprincs\"*

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image14.png){width="5.407004593175853in"
height="0.39588910761154855in"}

**Step 4: Configure the Kerberos Client (VM2)**

1.  **Edit the Kerberos Configuration File on VM2:**

    -   Open /etc/krb5.conf for editing on VM2:

*bash*

*sudo nano /etc/krb5.conf*

-   Set the default realm to MYLAB.LOCAL and point to the KDC and admin
    server on VM1. The configuration should match what you set on VM1.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image15.png){width="5.802892607174103in"
height="2.864983595800525in"}

**Step 5: Test Kerberos Authentication**

1.  **Request a Kerberos Ticket for the User on VM2:**

    -   In the terminal on VM2, request a ticket for testuser:

*bash*

*kinit testuser@MYLAB.LOCAL*

-   Enter the password you set for testuser.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image16.png){width="7.027083333333334in"
height="1.0083333333333333in"}

2.  **Verify the Ticket:**

    -   Check if the ticket was issued by listing active Kerberos
        tickets:

*bash*

*klist*

-   You should see details about the ticket, such as the principal and
    expiration time, confirming successful Kerberos authentication.

![](vertopal_4cf10180e78e457385f96b84523955a3/media/image17.png){width="7.027083333333334in"
height="1.0986111111111112in"}
