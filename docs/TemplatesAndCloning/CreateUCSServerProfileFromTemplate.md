# Task 4: Create UCS Server Profile from Template

Select the three dots on the right of you newly create UCS Server Profile Template and select **Derive**.

![Create UCS Server Profile From Template 1](./CreateUCSProfileFromTemplate1.png "Create UCS Server Profile From Template 1")

Do not assign it to a server and select **Assign Later**.

![Create UCS Server Profile From Template 2](./CreateUCSProfileFromTemplate2.png "Create UCS Server Profile From Template 2")

The **Number of Profiles** to derive should be “**1**” and click **Next**.

Rename it to: **SRVxx-ServerProfile**, where **x is your POD number** and the **Organization** is **X-Series-Configuration**.

![Create UCS Server Profile From Template 3](./CreateUCSProfileFromTemplate3.png "Create UCS Server Profile From Template 3")

Click **Next**.

You see now the summary.

![Create UCS Server Profile From Template 4](./CreateUCSProfileFromTemplate4.png "Create UCS Server Profile From Template 4")

Click on **Derive**

Go to **Profiles** (Left) and select **UCS Server Profiles**.

Look at the newly create UCS Server Profile.

![Create UCS Server Profile From Template 5](./CreateUCSProfileFromTemplate5.png "Create UCS Server Profile From Template 5")

You will see **SRVxx-ServerProfile** at the **Profiles / UCS Server Profiles**.

NOTE:

**We won’t assign the Server Profile because we will use Intersight Automation to do that!**