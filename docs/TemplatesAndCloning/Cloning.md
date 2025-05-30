# Task 1: Cloning

Let’s start with creating a clone of the **LAB-RESOURCE** UCS Server Profile Template.
Go to **Configure -> Templates** on the left and select the **UCS Server Profile Templates** at the top.
Click **Three dots** on the right of LAB-Resources and select **Clone**.

![Cloning 1](./Cloning1.png "Cloning 1")

The destination Organization is X-Series-Configuration
Select “Create new clones for all policies and pools inside of the destination organization.”

![Cloning 2](./Cloning2.png "Cloning 2")

Click Next

Suffix Name for Cloned Policies and Pools should be **-SRVx**, where **x is your pod number**.

The clone name can be SRVx-ServerProfileTemplate, where **x is your pod number**.
Set Tags to SRV:SRVx, **where x is your pod number**.