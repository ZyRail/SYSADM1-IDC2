T

+----------------------------------+------------------------+----------+
| ![](vertopal_                    |                        |          |
| 2396f79df5cb446486e4bec39de8d286 |                        |          |
| /media/image1.png){width="2.4in" |                        |          |
| height="0.5881944444444445in"}   |                        |          |
|                                  |                        |          |
| SCHOOL OF INFORMATION AND        |                        |          |
| TECHNOLOGY                       |                        |          |
+==================================+========================+==========+
| NAME: Zschairail Balanza         | DATE PERFORMED:        |          |
|                                  | 12/09/2024             |          |
+----------------------------------+------------------------+----------+
| Section: idc2                    | DATE SUBMITTED:        |          |
|                                  | 12/09/2024             |          |
+----------------------------------+------------------------+----------+

1.  # SYSADM1 -- Managing Services in Linux

    # Requirement: 

-   A virtual machine running Linux

![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image9.png){width="4.135416666666667in"
height="1.8020833333333333in"}

Complete this lab as follows:

1.  Use the service --status-all command to list all active and inactive
    > services.

> List down active and inactive services in the table below. Provide
> five (5) services for each column.

  -----------------------------------------------------------------------
  **Active**                             **Inactive**
  -------------------------------------- --------------------------------
  Alsa-utils                             Bluetooth

  Anacron                                Console-setup.sh

  Apport                                 Grup-common

  Cron                                   Keyboard-setup.sh

  cups                                   rsync
  -----------------------------------------------------------------------

> SS:![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image3.png){width="3.1354166666666665in"
> height="2.4131944444444446in"}

2.  Start the Bluetooth service using the systemctl command.

> Ex. sudo systemctl start httpd
>
> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image4.png){width="4.3687040682414695in"
> height="1.1898851706036746in"}

3.  Check the status of the Bluetooth service. What is its status?

-   The Bluetooth service status is enabled

> SS:
>
> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image2.png){width="6.035994094488189in"
> height="1.411321084864392in"}

1.  Check the status of the cups services. Since when was it running?

-   It has been running since September 9, 2024 at 09:09:37

> SS:
>
> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image10.png){width="5.898898731408574in"
> height="2.4927055993000873in"}

1.  Stop cups services.

> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image5.png){width="6.162922134733158in"
> height="0.50124343832021in"}

2.  Verify if the service was stopped.

> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image8.png){width="6.075033902012248in"
> height="1.975181539807524in"}

3.  Restart the cups services

> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image7.png){width="6.532015529308836in"
> height="0.20398403324584427in"}

4.  Verify if the service was restarted.

> ![](vertopal_2396f79df5cb446486e4bec39de8d286/media/image6.png){width="5.9464173228346455in"
> height="2.8929943132108487in"}
