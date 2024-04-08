# Important Information

## Virtual Machine Duration and Uptime

1. The environment will be active for **30 days/720 hours** from the time of registration.

1. The remaining time for the environment can be viewed from the top right corner of the environment page.

   ![Remaining Uptime](./images/remaining-time.png)

1. Virtual machine uptime is the maximum amount of time that a virtual machine can be used. You can view the **Remaining Uptime** for the virtual machine by selecting the **Resources** tab.

   ![remaining time](./images/vm-uptime.png)
   
1. The allowed uptime of the virtual machine is **5 hours**. It is recommended to deallocate the virtual machine when not in use. 

1. Once the virtual machine's uptime is completed, you will no longer be able to access the virtual machine to perform the lab. 

   ![Remaining Uptime](./images/uptime.png)

1. If you're unable to complete your testing within the provided virtual machine uptime, reach out to our support team at [labs-support@spektrasystems.com](labs-support@spektrasystems.com). They are available 24/7 to assist you in extending the uptime time of the virtual machine.

## Managing your Virtual Machine

1. To **Start**  the Virtual Machine, click on **Resources** tab from environment details page and then click on the **Start** button. The Virtual Machine will take approximately a minute to start. Feel free to click on the **Refresh** button from the **Resources** tab to view the latest status of the Virtual Machine.

   ![VM Start](./images/start-vm.png)

1. To **Deallocate/Stop** the Virtual Machine, click on **Resources** tab from environment details page and then click on the **Stop** button.

   ![VM Stop](./images/stop-vm.png)

1. In the event that the notification **VM Access Session is Closed** arrives. Next, **Refresh** the page; If the notice still same the check under the **Resource** tab the Virtual Machine is running or stop state. 

   ![VM Stop](./images/notice.png)

## Virtual Machine Idle Stop Feature

1. The virtual machine is set up with a custom feature called Idle Stop. This custom package will check the virtual machine's idleness every **15 minutes**. If the virtual machine is left idle for over 15 minutes, a pop-up window will appear, prompting you to respond.

   > **Note**: Based on your requirement, feel free to select either `Cancel` or `Shutdown`. 

   ![VM Popup](./images/auto-sheenshot.png)
 
1. If you do not take action within 10 minutes, the virtual machine will **shutdown** automatically.

   > **Note**: This feature is enabled in virtual machines to optimize the usage of virtual machines.

   ![VM Warning](./images/auto-warning.png)
   
1. If you need to **Start** the Virtual Machine, click on **Resources** tab from environment details page and then click on the **Start** button.

   ![VM Start](./images/start-vm1.png)

## Notification

1. If the virtual machine is left idle for over 15 minutes a warning pop-up window will appear in a virtual machine, prompting you to respond.

   ![VM Popup](./images/auto-sheenshot1.png)

1. If you do not take action within 10 minutes, the virtual machine will pop up with the Lab environment to be stopped and the virtual machine start **Deallocate/Stop**.

   ![VM Warning](./images/auto-warning1.png)

## Help 

1. If you encounter any issues while copying the issue, please click on the **Help** tab on the environment details page for tips and tricks. If the problem persists, reach out to our support team at [labs-support@spektrasystems.com](labs-support@spektrasystems.com).

   ![VM Warning](./images/help.png)
